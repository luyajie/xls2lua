# xls2lua
Convert xls to lua script for game res  
(将xls数据文件转化为lua脚本，作为游戏资源使用)
use [python xlrd](https://pypi.python.org/pypi/xlrd)

# What (是什么)
This is a script to convert xls to lua.</ br>
If you use lua language , the data write in lua is the best thing for you to code.</ br>
So this script will help you convert xls to lua , so you can do your job more easily.</ br>
(如果你在使用Lua语言，将数据写进Lua文件是最方便的做法。这个脚本将帮助你将数据xls文件转化为lua文件，这样你就可以更好的工作了。)</ br>

### example（例子xls表格）
example_building.xls  
<table>
    <tr>
        <td>id</td>
        <td>name</td>
        <td>use_money</td>
        <td>use_food</td>
        <td>is_init</td>
        <td>defense</td>
        <td>args1</td>
        <td>args2</td>
        <td>args3</td>
        <td>args4</td>
    </tr>
    <tr>
        <td>i</td>
        <td>s</td>
        <td>i</td>
        <td>f</td>
        <td>b</td>
        <td>i</td>
        <td>ai</td>
        <td>af</td>
        <td>as</td>
        <td>ab</td>
    </tr>
    <tr>
        <td>1</td>
        <td>house</td>
        <td>1000</td>
        <td>2.33</td>
        <td>TRUE</td>
        <td>100</td>
        <td>1,2,3</td>
        <td>1.23,2,3.23</td>
        <td>sdf,23e,s</td>
        <td>true,false,true</td>
    </tr>
    <tr>
        <td>2</td>
        <td>house2</td>
        <td>123</td>
        <td>336.2</td>
        <td>TRUE</td>
        <td></td>
        <td>1,2,3</td>
        <td>1,2.3445,3</td>
        <td>你好,你在哪</td>
        <td>true,false</td>
    </tr>
    <tr>
        <td>3</td>
        <td></td>
        <td>456</td>
        <td>222.33665</td>
        <td>FALSE</td>
        <td>130</td>
        <td>3,2,5,,</td>
        <td>3,2,2.5,,</td>
        <td>我在这里啊,你在那,呢</td>
        <td>false,true</td>
    </tr>
    <tr>
        <td>4</td>
        <td>farm</td>
        <td>100</td>
        <td>220</td>
        <td>FALSE</td>
        <td>200</td>
        <td>2,3,</td>
        <td>200.3,3,234.23,</td>
        <td>df,ssd,dd,dd</td>
        <td></td>
    </tr>
    <tr>
        <td>5</td>
        <td>house5</td>
        <td></td>
        <td>22.1</td>
        <td></td>
        <td>234 3,6,6,,,7</td>
        <td>3,6.3,6,,,7</td>
        <td>ss,d,d,d</td>
        <td>true,true</td>
    </tr>
    <tr>
        <td>6</td>
        <td>horse3</td>
        <td>200</td>
        <td></td>
        <td>FALSE</td>
        <td>333</td>
        <td></td>
        <td></td>
        <td>2e,w,e,we</td>
        <td>false,false,false,false</td>
    </tr>
</table>

### Excute Example (举例执行命令)
./xls2lua.py example_building.xls ./data/

### NOTICE:(注意点)
> The sheet name must start with "output_" , the lua file name will be the name behind "output_".
> (sheet名以"output_"开头的才会被识别转换，否则将被忽略)
> The **first row** must be **title**.  
> (第1行必须是关键字名)
> The **second row** must be **type**
> (第2行必须为类型)
> The **type must be i , f , s , b , ai , af , as , ab.
> (类型有：i,f,s,b,ai,af,as,ab这几种)
> i mean int , f mean float , s mean string , b mean bool , ai mean array int , af mean array float , as mean array string , ab mean array bool.
> (i表示int，f表示float,s表示string,b表示bool,ai表示int数组,af表示float数组,as表示string数组,ab表示bool数组)
> The **first column** must be int , so the type in first column must be i.
> (第1列必须为int类型的唯一关键字)

### LUA SCRIPT (生成后的Lua文件示例)
```lua
-- this file is generated by program!
-- don't change it manaully.
-- source file: example_building.xls
-- created at: Thu Mar 26 02:53:52 2015

local data = {}

data[1] = { id = 1,  name = "house",  use_money = 1000,  use_food = 2.33,  is_init = true,  defense = 100,  aadd = {1,2,3},  aadddss = {1.23,2,3.23},  ddff = {"sdf","23e","s"},  ffdd = {true,false,true}}
data[2] = { id = 2,  name = "house2",  use_money = 123,  use_food = 336.2,  is_init = true,  defense = 0,  aadd = {1,2,3},  aadddss = {1,2.3445,3},  ddff = {"你好","你在哪"},  ffdd = {true,false}}
data[3] = { id = 3,  name = "",  use_money = 456,  use_food = 222.33665,  is_init = false,  defense = 130,  aadd = {3,2,5},  aadddss = {3,2,2.5},  ddff = {"我在这里啊","你在那","呢"},  ffdd = {false,true}}
data[4] = { id = 4,  name = "farm",  use_money = 100,  use_food = 220.0,  is_init = false,  defense = 200,  aadd = {2,3},  aadddss = {200.3,3,234.23},  ddff = {"df","ssd","dd","dd"},  ffdd = {}}
data[5] = { id = 5,  name = "house5",  use_money = 0,  use_food = 22.1,  is_init = false,  defense = 234,  aadd = {3,6,6,7},  aadddss = {3,6.3,6,7},  ddff = {"ss","d","d","d"},  ffdd = {true,true}}
data[6] = { id = 6,  name = "horse3",  use_money = 200,  use_food = 0,  is_init = false,  defense = 333,  aadd = {},  aadddss = {},  ddff = {"2e","w","e","we"},  ffdd = {false,false,false,false}}

return data

```

### HOW TO USE LUA SCRIPT (如何使用生成的lua数据)
```lua
local building = require "building"

print(building[1].name)
```
The console will print "house"
