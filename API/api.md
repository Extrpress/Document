## Extpress接口规范

#### 页面入口

**URL**|**描述**|**参数**|**模板**|
---|---|----|----
index|首页|token|index
sign|登录| |sign
mail|寄件| |mail
expresse|快递信息|

##异步接口

以页面为单位，描述每个页面需要的接口
****

###**首页**

**URL:`/index/`**
Method:GET
描述：首页

接收数据类型

**数据类型**|**数据名**|
---|---|----
string:token|token（base64）

单条数据模板:
````
{
    "token":"dhfHKJHGI87632864GGUIGUI"
}
````

返回数据类型

**数据类型**|**数据名**|
---|---|----

****
**URL:`/sign/`**
Method:POST
Authentication: 登录/注册
描述：登录页，接收serialize的form数据，解析出用户名，密码，返回状态码和token。

登录：
接收数据类型

**数据类型**|**数据名**|
---|---|----
string:username|用户名（base64）
string:password|密码（base64）

返回数据类型

**数据类型**|**数据名**|
---|---|----
string:token|token（base64）


返回数据模板:
````
{
    "token":"dhfHKJHGI87632864GGUIGUI"
}
````
注册：
接收数据类型

**数据类型**|**数据名**|
---|---|----
string:username|用户名（base64）
string:password|密码（base64）
int:id_number|省份证号码

返回数据类型

**数据类型**|**数据名**|
---|---|----
boolen:status|状态
string:token|token（base64）


返回数据模板:
````
{
    "status":success,
    "token":"dhfHKJHGI87632864GGUIGUI"
}
````

**URL:`/mail/`**
Method:POST
描述:寄件

接收数据类型

**数据类型**|**数据名**|
---|---|----
string:origin|起点
string:destination|终点
int:weight|重量
string:more|备注
***

返回数据类型

**数据类型**|**数据名**|
---|---|----
string:num|运单号
string:location|快递目前地点

***

{
    "num":"yxz0000000001"
}
