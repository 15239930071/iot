# CreateRule {#reference_zby_wrz_wdb .reference}

调用该接口对指定Topic新建一个规则。

## 请求参数 {#section_hfg_ysy_xdb .section}

**说明：** 如需启动规则，需包含ProductKey、ShortTopic、Select三个参数的信息。

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：CreateRule。|
|Name|String|是|规则名称。支持使用中英文字符、数字和下划线（\_），长度应为4~30位（一个中文字符算2位）。|
|ProductKey|String|否|应用该规则的产品Key。|
|ShortTopic|String|否| 应用该规则的具体Topic，格式为：`${deviceName}/ topicShortName`。其中，`${deviceName}`指具体设备的名称，`topicShortName`是该设备的自定义类目。

 您可以调用QueryDevice接口，查看产品下的所有设备。返回结果中包含所有的DeviceName。

 您可以调用QueryProductTopic接口，查看产品下的所有Topic类。返回结果中包含所有的TopicShortName。

 |
|Select|String|否| 要执行的SQL Select语句。具体内容参照SQL表达式。

 **说明：** 此处传入的是Select下的内容。例如，如果Selcet语句为`Select a,b,c`，则此处传入`a,b,c`。

 |
|RuleDesc|String|否|规则的描述信息。|
|DataType|String|否| 规则使用的数据格式，取值：

 JSON：JSON数据。

 BINARY：二进制数据。

 如果不传入该参数，则默认使用JSON格式。

 |
|Where|String|否| 规则的触发条件。具体内容参照SQL表达式。

 **说明：** 此处传入的是Where中的内容。例如，如果Where语句为`Where a>10`，则此处传入`a>10`。

 |

## 返回参数 {#section_hqw_wbz_xdb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|阿里云为该请求生成的唯一标识符。|
|Success|Boolean|表示是否调用成功。ture表示调用成功，false表示调用失败。|
|ErrorMessage|String|调用失败时，返回的出错信息。|
|RuleId|Long| 调用成功时，规则引擎为该规则生成的规则ID，作为其标识符。

 **说明：** 请妥善保管该信息。在调用和规则相关的接口时，您可能需要提供对应的规则ID。

 |

## 示例 {#section_bvf_kcz_xdb .section}

**请求示例**

```
https://iot.cn-shanghai.aliyuncs.com/?Action=CreateRule
&Name=iot_test1
&ProductKey=al*********
&ShortTopic=open_api_dev/get
&Select=a,b,c
&RuleDesc=rule test
&DataType=JSON
&Where=a>10
&公共请求参数
```

**返回示例**

```
{
    "RequestId": "E4C0FF92-2A86-41DB-92D3-73B60310D25E",
    "RuleId":1000,
    "Success": true
}
```

