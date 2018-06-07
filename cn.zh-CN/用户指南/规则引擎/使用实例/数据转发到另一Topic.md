# 数据转发到另一Topic {#task_yvk_2c5_vdb .task}

您可以将依据SQL规则处理完的数据，设置转发到另一个Topic中，实现M2M或者更多其他场景。

在设置转发之前，您需要参考[设置规则引擎](cn.zh-CN/用户指南/规则引擎/设置规则引擎.md#)编写SQL完成对数据的处理。

本文将教您如何设置数据从Topic1中依照规则引擎设置转发到Topic2内：

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7543/2531_zh-CN.png)

1.   单击**数据转发**一栏的**添加操作**。出现添加操作页面。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/7543/2628_zh-CN.png) 
2.   按照页面提示，设置参数。 
    -   选择操作：此处选择**发布到另一个Topic**。
    -   Topic：选择您需要把数据转发到哪一个Topic中。此处选择产品后，还需补充完整该Topic。您可以使用`${}`表达式引用上下文值，如填`${dn}/get`表示从消息中选中devicename，该Topic的后缀为get。

