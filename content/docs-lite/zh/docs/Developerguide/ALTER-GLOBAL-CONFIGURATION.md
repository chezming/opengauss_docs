# ALTER GLOBAL CONFIGURATION<a name="ZH-CN_TOPIC_0000001252227949"></a>

## 功能描述<a name="zh-cn_topic_0283136791_zh-cn_topic_0237122191_zh-cn_topic_0059779163_s812131d8918641df9772c998b753f87e"></a>

新增、修改系统表gs\_global\_config，增加key-value值。

## 注意事项<a name="zh-cn_topic_0283136791_zh-cn_topic_0237122191_zh-cn_topic_0059779163_se3c9c9141f1b44ff9807883ea294625d"></a>

仅支持数据库初始用户运行此命令。

不支持创建修改关键字为weak\_password。

## 语法格式<a name="zh-cn_topic_0283136791_zh-cn_topic_0237122191_zh-cn_topic_0059779163_s8d26aecdc3a24323a64f4df9f4df53f3"></a>

```
ALTER GLOBAL CONFIGURATION with(参数名称=参数值，参数名称=参数值...);
```

## 参数说明<a name="zh-cn_topic_0283136791_zh-cn_topic_0237122191_zh-cn_topic_0059779163_s96f32bd65e9e46f4bf15eb3c1663af3a"></a>

参数名称和参数值都是text类型。
