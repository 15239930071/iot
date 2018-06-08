# UpdateRule {#reference_szx_zjd_xdb .reference}

调用该接口修改指定的规则。

## 请求参数 {#section_yrn_rx1_ydb .section}

|名称|类型|是否必需|描述|
|:-|:-|:---|:-|
|Action|String|是|要执行的操作，取值：UpdateRule。|
|RuleId|Long|是|要修改的规则ID。|
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
|Where|String|否| 规则的触发条件。具体内容参照SQL表达式。

 **说明：** 此处传入的是Where中的内容。例如，如果Where语句为`Where a>10`，则此处传入`a>10`。

 |

## 返回参数 {#section_qrf_gy1_ydb .section}

|名称|类型|描述|
|:-|:-|:-|
|RequestId|String|阿里云为该请求生成的唯一标识符。|
|Success|Boolean|表示是否调用成功。ture表示调用成功，false表示调用失败。|
|ErrorMessage|String|调用失败时，返回的出错信息。|

## 示例 {#section_p4w_ky1_ydb .section}

**请求示例**

```
https://iot.cn-shanghai.aliyuncs.com/?Action=UpdateRule
&RuleId=1000
&Name=test_2
&ProductKey=al*********
&ShortTopic=+/get
&Select=a,b,c
&RuleDesc=test
&Where=a>10
&公共请求参数
```

**返回示例**

```
{
    "RequestId":"9A2F243E-17FE-4846-BAB5-D02A25155AC4",
    "Success":true
}
```

