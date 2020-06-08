## Impala数据信息



### 目录
  - [一、诸葛IO数据字典](#一诸葛IO数据字典)
  - [二、分类整理表名](#二分类整理表名)
  - [三、建表语句](#三建表语句)  
  - [四、所有分区表分区信息](#四所有分区表分区信息)
  - [五、所有表名列表](#五所有表名列表)  

### 一、诸葛IO数据字典



DW_基础层：

| b_user_appId（用户表） |            |          |      |        |        |      |
| ---------------------- | ---------- | -------- | ---- | ------ | ------ | ---- |
| 英文字段               | 中文字段   | 字段类型 | 主键 | 分区键 | 表类型 | 备注 |
| device_id              | 设备id     | BIGINT   | Y    |        |        |      |
| zg_id                  | 诸葛id     | BIGINT   | Y    |        |        |      |
| user_id                | 注册用户id | BIGINT   |      |        |        |      |
| begin_date             | 新增时间   | BIGINT   |      |        |        |      |
| platform               | 平台       | SMALLINT |      |        |        |      |



| b_user_property_appId（用户属性表） |                    |          |      |        |        |      |
| ----------------------------------- | ------------------ | -------- | ---- | ------ | ------ | ---- |
| 英文字段                            | 中文字段           | 字段类型 | 主键 | 分区键 | 表类型 | 备注 |
| zg_id                               | 诸葛id             | BIGINT   | Y    | Y      |        |      |
| property_id                         | 用户属性id         | INT      | Y    |        |        |      |
| user_id                             | 注册用户id         | BIGINT   |      |        |        |      |
| property_name                       | 用户属性字段名     | STRING   |      |        |        |      |
| property_data_type                  | 用户属性gp数据类型 | STRING   |      |        |        |      |
| property_value                      | 用户属性值         | STRING   |      |        |        |      |
| platform                            | 平台               | SMALLINT |      |        |        |      |
| last_update_date                    | 最后更新时间       | BIGINT   |      |        |        |      |



| b_device_appId（设备表） |                              |          |      |        |        |      |
| ------------------------ | ---------------------------- | -------- | ---- | ------ | ------ | ---- |
| 英文字段                 | 中文字段                     | 字段类型 | 主键 | 分区键 | 表类型 | 备注 |
| device_id                | 设备Id                       | BIGINT   | Y    | Y      |        |      |
| device_md5               | md5                          | STRING   |      |        |        |      |
| platform                 | 平台                         | SMALLINT |      |        |        |      |
| device_type              | null                         | STRING   |      |        |        |      |
| l                        | 水平像素                     | INT      |      |        |        |      |
| h                        | 垂直像素                     | INT      |      |        |        |      |
| device_brand             | 设备商标                     | STRING   |      |        |        |      |
| device_model             | 设备型号                     | STRING   |      |        |        |      |
| resolution               | 分辨率                       | STRING   |      |        |        |      |
| phone                    | 电话                         | STRING   |      |        |        |      |
| imei                     | 移动设备标识，由15位数字组成 | STRING   |      |        |        |      |
| mac                      | mac地址                      | STRING   |      |        |        |      |
| is_prison_break          | 是否越狱                     | SMALLINT |      |        |        |      |
| is_crack                 | 是否破解                     | SMALLINT |      |        |        |      |
| language                 | 语言                         | STRING   |      |        |        |      |
| timezone                 | 时区                         | STRING   |      |        |        |      |
| attr1                    | 备用字段                     | STRING   |      |        |        |      |
| attr2                    | 备用字段                     | STRING   |      |        |        |      |
| attr3                    | 备用字段                     | STRING   |      |        |        |      |
| attr4                    | 备用字段                     | STRING   |      |        |        |      |
| attr5                    | 备用字段                     | STRING   |      |        |        |      |
| last_update_date         | 最后更新时间                 | BIGINT   |      |        |        |      |



| b_user_event_all_appId（事件总表） |                                       |          |      |        |        |                          |
| ---------------------------------- | ------------------------------------- | -------- | ---- | ------ | ------ | ------------------------ |
| 英文字段                           | 中文字段                              | 字段类型 | 主键 | 分区键 | 表类型 | 备注                     |
| zg_id                              | 诸葛id                                | BIGINT   | Y    | Y      |        |                          |
| session_id                         | 会话id                                | BIGINT   | Y    |        |        |                          |
| uuid                               | 区分同一时刻触发同一事件              | STRING   | Y    |        |        |                          |
| event_id                           | 事件id                                | BIGINT   | Y    |        |        |                          |
| begin_date                         | 开始时间                              | BIGINT   | Y    |        |        |                          |
| begin_time_id                      | 前两位小时 第三位是0   后面三位毫秒数 | INT      | Y    |        |        |                          |
| device_id                          | 设备id                                | BIGINT   |      |        |        |                          |
| user_id                            | 注册用户id                            | BIGINT   |      |        |        |                          |
| event_name                         | 事件名                                | STRING   |      |        |        |                          |
| begin_day_id                       | 日期                                  | INT      |      |        |        |                          |
| platform                           | 平台                                  | SMALLINT |      |        |        |                          |
| network                            | 网络                                  | SMALLINT |      |        |        |                          |
| mccmnc                             | 运营商                                | INT      |      |        |        |                          |
| useragent                          | 用户代理                              | STRING   |      |        |        |                          |
| website                            | 来源网站                              | STRING   |      |        |        |                          |
| current_url                        | 当前url                               | STRING   |      |        |        |                          |
| referrer_url                       | 来源url                               | STRING   |      |        |        |                          |
| channel                            | 渠道                                  | STRING   |      |        |        |                          |
| app_version                        | 版本                                  | STRING   |      |        |        |                          |
| ip                                 | 用户ip的数字格式                      | BIGINT   |      |        |        |                          |
| ip_str                             | 用户ip的正常格式                      | STRING   |      |        |        |                          |
| country                            | 国家                                  | STRING   |      |        |        |                          |
| area                               | 地区                                  | STRING   |      |        |        |                          |
| city                               | 城市                                  | STRING   |      |        |        |                          |
| os                                 | 操作系统                              | STRING   |      |        |        |                          |
| ov                                 | 操作系统版本                          | INT      |      |        |        |                          |
| bs                                 | 浏览器                                | STRING   |      |        |        |                          |
| bv                                 | 浏览器版本                            | INT      |      |        |        |                          |
| utm_source                         | 广告来源                              | STRING   |      |        |        |                          |
| utm_medium                         | 广告媒介                              | STRING   |      |        |        |                          |
| utm_campaign                       | 广告名称                              | STRING   |      |        |        |                          |
| utm_content                        | 广告内容                              | STRING   |      |        |        |                          |
| utm_term                           | 广告关键词                            | STRING   |      |        |        |                          |
| duration                           | 持续的时间                            | BIGINT   |      |        |        |                          |
| UTC_date                           | UTC时间                               | BIGINT   |      |        |        |                          |
| attr1                              | 备用字段                              | STRING   |      |        |        |                          |
| attr2                              | 备用字段                              | STRING   |      |        |        |                          |
| attr3                              | 备用字段                              | STRING   |      |        |        |                          |
| attr4                              | 备用字段                              | STRING   |      |        |        |                          |
| attr5                              | 备用字段                              | STRING   |      |        |        |                          |
| yw                                 | 年周                                  | int      |      | Y      |        | 由自定义yearweek函数生成 |



| b_user_event_attr_appId（事属性表） |                                       |          |      |        |        |      |
| ----------------------------------- | ------------------------------------- | -------- | ---- | ------ | ------ | ---- |
| 英文字段                            | 中文字段                              | 字段类型 | 主键 | 分区键 | 表类型 | 备注 |
| zg_id                               | 诸葛id                                | BIGINT   | Y    | Y      |        |      |
| session_id                          | 会话id                                | BIGINT   | Y    |        |        |      |
| uuid                                | 区分同一时刻触发同一事件              | STRING   | Y    |        |        |      |
| event_id                            | 事件id                                | BIGINT   | Y    |        |        |      |
| begin_date                          | 开始时间                              | BIGINT   | Y    |        |        |      |
| begin_time_id                       | 前两位小时 第三位是0   后面三位毫秒数 | INT      | Y    |        |        |      |
| device_id                           | 设备id                                | BIGINT   |      |        |        |      |
| user_id                             | 注册用户id                            | BIGINT   |      |        |        |      |
| event_name                          | 事件名                                | STRING   |      |        |        |      |
| begin_day_id                        | 日期                                  | INT      |      |        |        |      |
| platform                            | 平台                                  | SMALLINT |      |        |        |      |
| network                             | 网络                                  | SMALLINT |      |        |        |      |
| mccmnc                              | 运营商                                | INT      |      |        |        |      |
| useragent                           | 用户代理                              | STRING   |      |        |        |      |
| website                             | 来源网站                              | STRING   |      |        |        |      |
| current_url                         | 当前url                               | STRING   |      |        |        |      |
| referrer_url                        | 来源url                               | STRING   |      |        |        |      |
| channel                             | 渠道                                  | STRING   |      |        |        |      |
| app_version                         | 版本                                  | STRING   |      |        |        |      |
| ip                                  | 用户ip的数字格式                      | BIGINT   |      |        |        |      |
| ip_str                              | 用户ip的正常格式                      | STRING   |      |        |        |      |
| country                             | 国家                                  | STRING   |      |        |        |      |
| area                                | 地区                                  | STRING   |      |        |        |      |
| city                                | 城市                                  | STRING   |      |        |        |      |
| os                                  | 操作系统                              | STRING   |      |        |        |      |
| ov                                  | 操作系统版本                          | INT      |      |        |        |      |
| bs                                  | 浏览器                                | STRING   |      |        |        |      |
| bv                                  | 浏览器版本                            | INT      |      |        |        |      |
| utm_source                          | 广告来源                              | STRING   |      |        |        |      |
| utm_medium                          | 广告媒介                              | STRING   |      |        |        |      |
| utm_campaign                        | 广告名称                              | STRING   |      |        |        |      |
| utm_content                         | 广告内容                              | STRING   |      |        |        |      |
| utm_term                            | 广告关键词                            | STRING   |      |        |        |      |
| duration                            | 持续的时间                            | BIGINT   |      |        |        |      |
| utc_date                            | UTC时间                               | BIGINT   |      |        |        |      |
| attr1                               | 备用字段                              | STRING   |      |        |        |      |
| attr2                               | 备用字段                              | STRING   |      |        |        |      |
| attr3                               | 备用字段                              | STRING   |      |        |        |      |
| attr4                               | 备用字段                              | STRING   |      |        |        |      |
| attr5                               | 备用字段                              | STRING   |      |        |        |      |
| cus1                                | 事件属性1                             | STRING   |      |        |        |      |
| cus2                                |                                       | STRING   |      |        |        |      |
| cus3                                |                                       | STRING   |      |        |        |      |
| cus4                                |                                       | STRING   |      |        |        |      |
| cus5                                |                                       | STRING   |      |        |        |      |
| cus6                                |                                       | STRING   |      |        |        |      |
| cus7                                |                                       | STRING   |      |        |        |      |
| cus8                                |                                       | STRING   |      |        |        |      |
| cus9                                |                                       | STRING   |      |        |        |      |
| cus10                               |                                       | STRING   |      |        |        |      |
| cus11                               |                                       | STRING   |      |        |        |      |
| cus12                               |                                       | STRING   |      |        |        |      |
| cus13                               |                                       | STRING   |      |        |        |      |
| cus14                               |                                       | STRING   |      |        |        |      |
| cus15                               |                                       | STRING   |      |        |        |      |
| cus16                               |                                       | STRING   |      |        |        |      |
| cus17                               |                                       | STRING   |      |        |        |      |
| cus18                               |                                       | STRING   |      |        |        |      |
| cus19                               |                                       | STRING   |      |        |        |      |
| cus20                               |                                       | STRING   |      |        |        |      |
| cus21                               |                                       | STRING   |      |        |        |      |
| cus22                               |                                       | STRING   |      |        |        |      |
| cus23                               |                                       | STRING   |      |        |        |      |
| cus24                               |                                       | STRING   |      |        |        |      |
| cus25                               |                                       | STRING   |      |        |        |      |
| cus26                               |                                       | STRING   |      |        |        |      |
| cus27                               |                                       | STRING   |      |        |        |      |
| cus28                               |                                       | STRING   |      |        |        |      |
| cus29                               |                                       | STRING   |      |        |        |      |
| cus30                               |                                       | STRING   |      |        |        |      |
| cus31                               |                                       | STRING   |      |        |        |      |
| cus32                               |                                       | STRING   |      |        |        |      |
| cus33                               |                                       | STRING   |      |        |        |      |
| cus34                               |                                       | STRING   |      |        |        |      |
| cus35                               |                                       | STRING   |      |        |        |      |
| cus36                               |                                       | STRING   |      |        |        |      |
| cus37                               |                                       | STRING   |      |        |        |      |
| cus38                               |                                       | STRING   |      |        |        |      |
| cus39                               |                                       | STRING   |      |        |        |      |
| cus40                               |                                       | STRING   |      |        |        |      |
| cus41                               |                                       | STRING   |      |        |        |      |
| cus42                               |                                       | STRING   |      |        |        |      |
| cus43                               |                                       | STRING   |      |        |        |      |
| cus44                               |                                       | STRING   |      |        |        |      |
| cus45                               |                                       | STRING   |      |        |        |      |
| cus46                               |                                       | STRING   |      |        |        |      |
| cus47                               |                                       | STRING   |      |        |        |      |
| cus48                               |                                       | STRING   |      |        |        |      |
| cus49                               |                                       | STRING   |      |        |        |      |
| cus50                               |                                       | STRING   |      |        |        |      |
| cus51                               |                                       | STRING   |      |        |        |      |
| cus52                               |                                       | STRING   |      |        |        |      |
| cus53                               |                                       | STRING   |      |        |        |      |
| cus54                               |                                       | STRING   |      |        |        |      |
| cus55                               |                                       | STRING   |      |        |        |      |
| cus56                               |                                       | STRING   |      |        |        |      |
| cus57                               |                                       | STRING   |      |        |        |      |
| cus58                               |                                       | STRING   |      |        |        |      |
| cus59                               |                                       | STRING   |      |        |        |      |
| cus60                               |                                       | STRING   |      |        |        |      |
| cus61                               |                                       | STRING   |      |        |        |      |
| cus62                               |                                       | STRING   |      |        |        |      |
| cus63                               |                                       | STRING   |      |        |        |      |
| cus64                               |                                       | STRING   |      |        |        |      |
| cus65                               |                                       | STRING   |      |        |        |      |
| cus66                               |                                       | STRING   |      |        |        |      |
| cus67                               |                                       | STRING   |      |        |        |      |
| cus68                               |                                       | STRING   |      |        |        |      |
| cus69                               |                                       | STRING   |      |        |        |      |
| cus70                               |                                       | STRING   |      |        |        |      |
| cus71                               |                                       | STRING   |      |        |        |      |
| cus72                               |                                       | STRING   |      |        |        |      |
| cus73                               |                                       | STRING   |      |        |        |      |
| cus74                               |                                       | STRING   |      |        |        |      |
| cus75                               |                                       | STRING   |      |        |        |      |
| cus76                               |                                       | STRING   |      |        |        |      |
| cus77                               |                                       | STRING   |      |        |        |      |
| cus78                               |                                       | STRING   |      |        |        |      |
| cus79                               |                                       | STRING   |      |        |        |      |
| cus80                               |                                       | STRING   |      |        |        |      |
| cus81                               |                                       | STRING   |      |        |        |      |
| cus82                               |                                       | STRING   |      |        |        |      |
| cus83                               |                                       | STRING   |      |        |        |      |
| cus84                               |                                       | STRING   |      |        |        |      |
| cus85                               |                                       | STRING   |      |        |        |      |
| cus86                               |                                       | STRING   |      |        |        |      |
| cus87                               |                                       | STRING   |      |        |        |      |
| cus88                               |                                       | STRING   |      |        |        |      |
| cus89                               |                                       | STRING   |      |        |        |      |
| cus90                               |                                       | STRING   |      |        |        |      |
| cus91                               |                                       | STRING   |      |        |        |      |
| cus92                               |                                       | STRING   |      |        |        |      |
| cus93                               |                                       | STRING   |      |        |        |      |
| cus94                               |                                       | STRING   |      |        |        |      |
| cus95                               |                                       | STRING   |      |        |        |      |
| cus96                               |                                       | STRING   |      |        |        |      |
| cus97                               |                                       | STRING   |      |        |        |      |
| cus98                               |                                       | STRING   |      |        |        |      |
| cus99                               |                                       | STRING   |      |        |        |      |
| cus100                              |                                       | STRING   |      |        |        |      |
| type1                               | 事件属性1类型                         | STRING   |      |        |        |      |
| type2                               |                                       | STRING   |      |        |        |      |
| type3                               |                                       | STRING   |      |        |        |      |
| type4                               |                                       | STRING   |      |        |        |      |
| type5                               |                                       | STRING   |      |        |        |      |
| type6                               |                                       | STRING   |      |        |        |      |
| type7                               |                                       | STRING   |      |        |        |      |
| type8                               |                                       | STRING   |      |        |        |      |
| type9                               |                                       | STRING   |      |        |        |      |
| type10                              |                                       | STRING   |      |        |        |      |
| type11                              |                                       | STRING   |      |        |        |      |
| type12                              |                                       | STRING   |      |        |        |      |
| type13                              |                                       | STRING   |      |        |        |      |
| type14                              |                                       | STRING   |      |        |        |      |
| type15                              |                                       | STRING   |      |        |        |      |
| type16                              |                                       | STRING   |      |        |        |      |
| type17                              |                                       | STRING   |      |        |        |      |
| type18                              |                                       | STRING   |      |        |        |      |
| type19                              |                                       | STRING   |      |        |        |      |
| type20                              |                                       | STRING   |      |        |        |      |
| type21                              |                                       | STRING   |      |        |        |      |
| type22                              |                                       | STRING   |      |        |        |      |
| type23                              |                                       | STRING   |      |        |        |      |
| type24                              |                                       | STRING   |      |        |        |      |
| type25                              |                                       | STRING   |      |        |        |      |
| type26                              |                                       | STRING   |      |        |        |      |
| type27                              |                                       | STRING   |      |        |        |      |
| type28                              |                                       | STRING   |      |        |        |      |
| type29                              |                                       | STRING   |      |        |        |      |
| type30                              |                                       | STRING   |      |        |        |      |
| type31                              |                                       | STRING   |      |        |        |      |
| type32                              |                                       | STRING   |      |        |        |      |
| type33                              |                                       | STRING   |      |        |        |      |
| type34                              |                                       | STRING   |      |        |        |      |
| type35                              |                                       | STRING   |      |        |        |      |
| type36                              |                                       | STRING   |      |        |        |      |
| type37                              |                                       | STRING   |      |        |        |      |
| type38                              |                                       | STRING   |      |        |        |      |
| type39                              |                                       | STRING   |      |        |        |      |
| type40                              |                                       | STRING   |      |        |        |      |
| type41                              |                                       | STRING   |      |        |        |      |
| type42                              |                                       | STRING   |      |        |        |      |
| type43                              |                                       | STRING   |      |        |        |      |
| type44                              |                                       | STRING   |      |        |        |      |
| type45                              |                                       | STRING   |      |        |        |      |
| type46                              |                                       | STRING   |      |        |        |      |
| type47                              |                                       | STRING   |      |        |        |      |
| type48                              |                                       | STRING   |      |        |        |      |
| type49                              |                                       | STRING   |      |        |        |      |
| type50                              |                                       | STRING   |      |        |        |      |
| type51                              |                                       | STRING   |      |        |        |      |
| type52                              |                                       | STRING   |      |        |        |      |
| type53                              |                                       | STRING   |      |        |        |      |
| type54                              |                                       | STRING   |      |        |        |      |
| type55                              |                                       | STRING   |      |        |        |      |
| type56                              |                                       | STRING   |      |        |        |      |
| type57                              |                                       | STRING   |      |        |        |      |
| type58                              |                                       | STRING   |      |        |        |      |
| type59                              |                                       | STRING   |      |        |        |      |
| type60                              |                                       | STRING   |      |        |        |      |
| type61                              |                                       | STRING   |      |        |        |      |
| type62                              |                                       | STRING   |      |        |        |      |
| type63                              |                                       | STRING   |      |        |        |      |
| type64                              |                                       | STRING   |      |        |        |      |
| type65                              |                                       | STRING   |      |        |        |      |
| type66                              |                                       | STRING   |      |        |        |      |
| type67                              |                                       | STRING   |      |        |        |      |
| type68                              |                                       | STRING   |      |        |        |      |
| type69                              |                                       | STRING   |      |        |        |      |
| type70                              |                                       | STRING   |      |        |        |      |
| type71                              |                                       | STRING   |      |        |        |      |
| type72                              |                                       | STRING   |      |        |        |      |
| type73                              |                                       | STRING   |      |        |        |      |
| type74                              |                                       | STRING   |      |        |        |      |
| type75                              |                                       | STRING   |      |        |        |      |
| type76                              |                                       | STRING   |      |        |        |      |
| type77                              |                                       | STRING   |      |        |        |      |
| type78                              |                                       | STRING   |      |        |        |      |
| type79                              |                                       | STRING   |      |        |        |      |
| type80                              |                                       | STRING   |      |        |        |      |
| type81                              |                                       | STRING   |      |        |        |      |
| type82                              |                                       | STRING   |      |        |        |      |
| type83                              |                                       | STRING   |      |        |        |      |
| type84                              |                                       | STRING   |      |        |        |      |
| type85                              |                                       | STRING   |      |        |        |      |
| type86                              |                                       | STRING   |      |        |        |      |
| type87                              |                                       | STRING   |      |        |        |      |
| type88                              |                                       | STRING   |      |        |        |      |
| type89                              |                                       | STRING   |      |        |        |      |
| type90                              |                                       | STRING   |      |        |        |      |
| type91                              |                                       | STRING   |      |        |        |      |
| type92                              |                                       | STRING   |      |        |        |      |
| type93                              |                                       | STRING   |      |        |        |      |
| type94                              |                                       | STRING   |      |        |        |      |
| type95                              |                                       | STRING   |      |        |        |      |
| type96                              |                                       | STRING   |      |        |        |      |
| type97                              |                                       | STRING   |      |        |        |      |
| type98                              |                                       | STRING   |      |        |        |      |
| type99                              |                                       | STRING   |      |        |        |      |
| type100                             |                                       | STRING   |      |        |        |      |
| yw                                  | 年周                                  | int      |      | Y      |        |      |



### 二、分类整理表名

```mysql
apple_models

b_device_(2-25)          //（2-25）代表该表有2-25 的后缀  例：b_device_2    ... 	b_device_25     下同

b_user_(2-25)

b_user_delete_(2-25)

b_user_event_all_(2-25)				---视图

b_user_event_attr_(2-25)			---视图

b_user_has_event_(2-25)

b_user_no_use_annoy_(2-25)

b_user_property_(2-25)

backup_b_user_event_all_11_20190420

backup_b_user_event_all_6_20190420

backup_b_user_event_all_a_(2-23)_20200318

backup_b_user_event_all_b_(2-23)_20200318

backup_b_user_event_attr_a_(2-23)_20200318

backup_b_user_event_attr_b_(2-23)_20200318

backup_device_(2-23)_20200318

backup_user_(2-23)_20200318

backup_user_property_(2-23)_20200318

category										---视图

etl_log

etl_mkt_event_(2-23、25)

etl_steps

f_user_detail_(1-25)

f_user_detail_sum_(1-25)

f_user_join_(1-25)

filter_data_1_1_1

funnel_data_1_1_1

funnel_data_step_1_1_1

group_data_1_1_1

hdfs_b_user_event_all_(2-25)

hdfs_b_user_event_attr_(2-25)

kudu_b_user_event_all_a_(2-25)

kudu_b_user_event_all_b_(2-25)

kudu_b_user_event_attr_a_(2-23、25)

kudu_b_user_event_attr_b_(2-23、25)

kudu_sem_kpi

kudu_sem_meta

kudu_sem_query_word_kpi

mccmnc

model								---视图

network

order_data_1_1_1

order_data_1_1_3

platform

retention_data_1_1_1

retention_data_1_1_3

retention_data_step_1_1_1

retention_data_step_1_1_3

t_user_active_(1-25)

t_user_detail_(1-25)

t_user_detail_sum_(1-25)

t_user_duration_(1-25)

t_user_join_(1-25)

v2_filter_data_5_20200605_18989
v2_filter_data_5_20200605_18990
v2_filter_data_5_20200605_18991
v2_filter_data_5_20200605_18992
v2_filter_data_5_20200605_18994
v2_filter_data_5_20200605_18995
v2_filter_data_5_20200605_18996
v2_filter_data_5_20200605_18997

v2_funnel_data_6_20200605_18999
v2_funnel_data_step_6_20200605_18999

v2_group_data_5_20200605_18988
v2_group_data_5_20200605_18993

v2_group_data_6_20200605_18998
v2_group_data_6_20200605_19000

v2_retention_data_20_20200605_19001
v2_retention_data_step_20_20200605_19001


```



### 三、建表语句

```mysql
+-----------------------------------------------------------------------+
| result                                                                |
+-----------------------------------------------------------------------+
| CREATE TABLE zhugeio.apple_models (                                   |
|   identifier STRING,                                                  |
|   generation STRING                                                   |
| )                                                                     |
| STORED AS TEXTFILE                                                    |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/apple_models' |
|                                                                       |
+-----------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                                                  |
+---------------------------------------------------------------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.b_device_2 (                                                                                                                       |
|   device_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                     |
|   device_md5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                        |
|   platform SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                        |
|   device_type STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                       |
|   l INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                                    |
|   h INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                                    |
|   device_brand STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                      |
|   device_model STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                      |
|   resolution STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                        |
|   phone STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                             |
|   imei STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                              |
|   mac STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                               |
|   is_prison_break SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                 |
|   is_crack SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                        |
|   language STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                          |
|   timezone STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                          |
|   attr1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                             |
|   attr2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                             |
|   attr3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                             |
|   attr4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                             |
|   attr5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                             |
|   last_update_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                  |
|   PRIMARY KEY (device_id)                                                                                                                               |
| )                                                                                                                                                       |
| PARTITION BY HASH (device_id) PARTITIONS 2                                                                                                              |
| STORED AS KUDU                                                                                                                                          |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051', 'numRows'='1410197') |
+---------------------------------------------------------------------------------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                                                  |
+---------------------------------------------------------------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.b_user_2 (                                                                                                                         |
|   device_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                     |
|   zg_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                         |
|   user_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                           |
|   begin_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                        |
|   platform SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                        |
|   PRIMARY KEY (device_id, zg_id)                                                                                                                        |
| )                                                                                                                                                       |
| PARTITION BY HASH (zg_id) PARTITIONS 2                                                                                                                  |
| STORED AS KUDU                                                                                                                                          |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051', 'numRows'='1423499') |
+---------------------------------------------------------------------------------------------------------------------------------------------------------+
+--------------------------------------------------------------------------+
| result                                                                   |
+--------------------------------------------------------------------------+
| CREATE TABLE zhugeio.b_user_delete_2 (                                   |
|   device_id BIGINT,                                                      |
|   zg_id_annoy BIGINT,                                                    |
|   zg_id_identify BIGINT                                                  |
| )                                                                        |
| STORED AS TEXTFILE                                                       |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/b_user_delete_2' |
|                                                                          |
+--------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                                                            |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CREATE VIEW zhugeio.b_user_event_all_2 AS                                                                                                                         |
| SELECT * FROM zhugeio.kudu_b_user_event_all_a_2 UNION ALL SELECT * FROM zhugeio.kudu_b_user_event_all_b_2 UNION ALL SELECT * FROM zhugeio.hdfs_b_user_event_all_2 |
+-------------------------------------------------------------------------------------------------------------------------------------------------------------------+
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                                                               |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CREATE VIEW zhugeio.b_user_event_attr_2 AS                                                                                                                           |
| SELECT * FROM zhugeio.kudu_b_user_event_attr_a_2 UNION ALL SELECT * FROM zhugeio.kudu_b_user_event_attr_b_2 UNION ALL SELECT * FROM zhugeio.hdfs_b_user_event_attr_2 |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------+
+--------------------------------------------------------------------------------------------------+
| result                                                                                           |
+--------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.b_user_has_event_2 (                                                        |
|   device_id BIGINT,                                                                              |
|   zg_id BIGINT                                                                                   |
| )                                                                                                |
| STORED AS TEXTFILE                                                                               |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/b_user_has_event_2'                      |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='50192', 'totalSize'='719104') |
+--------------------------------------------------------------------------------------------------+
+----------------------------------------------------------------------------------------------+
| result                                                                                       |
+----------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.b_user_no_use_annoy_2 (                                                 |
|   device_id BIGINT,                                                                          |
|   zg_id_annoy BIGINT,                                                                        |
|   zg_id_identify BIGINT                                                                      |
| )                                                                                            |
| STORED AS TEXTFILE                                                                           |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/b_user_no_use_annoy_2'               |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='163', 'totalSize'='3456') |
+----------------------------------------------------------------------------------------------+
+----------------------------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                                                   |
+----------------------------------------------------------------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.b_user_property_2 (                                                                                                                 |
|   zg_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                          |
|   property_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                       |
|   user_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                            |
|   property_name STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                      |
|   property_data_type STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                 |
|   property_value STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                     |
|   platform SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                         |
|   last_update_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                                                                   |
|   PRIMARY KEY (zg_id, property_id)                                                                                                                       |
| )                                                                                                                                                        |
| PARTITION BY HASH (zg_id) PARTITIONS 2                                                                                                                   |
| STORED AS KUDU                                                                                                                                           |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051', 'numRows'='40757990') |
+----------------------------------------------------------------------------------------------------------------------------------------------------------+
+--------------------------------------------------------------------------------------------------+
| result                                                                                           |
+--------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_b_user_event_all_11_20190420 (                                       |
|   zg_id BIGINT,                                                                                  |
|   session_id BIGINT,                                                                             |
|   uuid STRING,                                                                                   |
|   event_id BIGINT,                                                                               |
|   begin_date BIGINT,                                                                             |
|   begin_time_id INT,                                                                             |
|   device_id BIGINT,                                                                              |
|   user_id BIGINT,                                                                                |
|   event_name STRING,                                                                             |
|   begin_day_id INT,                                                                              |
|   platform SMALLINT,                                                                             |
|   network SMALLINT,                                                                              |
|   mccmnc INT,                                                                                    |
|   useragent STRING,                                                                              |
|   website STRING,                                                                                |
|   current_url STRING,                                                                            |
|   referrer_url STRING,                                                                           |
|   channel STRING,                                                                                |
|   app_version STRING,                                                                            |
|   ip BIGINT,                                                                                     |
|   ip_str STRING,                                                                                 |
|   country STRING,                                                                                |
|   area STRING,                                                                                   |
|   city STRING,                                                                                   |
|   os STRING,                                                                                     |
|   ov INT,                                                                                        |
|   bs STRING,                                                                                     |
|   bv INT,                                                                                        |
|   utm_source STRING,                                                                             |
|   utm_medium STRING,                                                                             |
|   utm_campaign STRING,                                                                           |
|   utm_content STRING,                                                                            |
|   utm_term STRING,                                                                               |
|   duration BIGINT,                                                                               |
|   utc_date BIGINT,                                                                               |
|   attr1 STRING,                                                                                  |
|   attr2 STRING,                                                                                  |
|   attr3 STRING,                                                                                  |
|   attr4 STRING,                                                                                  |
|   attr5 STRING                                                                                   |
| )                                                                                                |
| PARTITIONED BY (                                                                                 |
|   yw INT                                                                                         |
| )                                                                                                |
| STORED AS PARQUET                                                                                |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_b_user_event_all_11_20190420'     |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='-1', 'totalSize'='897683767') |
+--------------------------------------------------------------------------------------------------+
+----------------------------------------------------------------------------------------------------+
| result                                                                                             |
+----------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_b_user_event_all_6_20190420 (                                          |
|   zg_id BIGINT,                                                                                    |
|   session_id BIGINT,                                                                               |
|   uuid STRING,                                                                                     |
|   event_id BIGINT,                                                                                 |
|   begin_date BIGINT,                                                                               |
|   begin_time_id INT,                                                                               |
|   device_id BIGINT,                                                                                |
|   user_id BIGINT,                                                                                  |
|   event_name STRING,                                                                               |
|   begin_day_id INT,                                                                                |
|   platform SMALLINT,                                                                               |
|   network SMALLINT,                                                                                |
|   mccmnc INT,                                                                                      |
|   useragent STRING,                                                                                |
|   website STRING,                                                                                  |
|   current_url STRING,                                                                              |
|   referrer_url STRING,                                                                             |
|   channel STRING,                                                                                  |
|   app_version STRING,                                                                              |
|   ip BIGINT,                                                                                       |
|   ip_str STRING,                                                                                   |
|   country STRING,                                                                                  |
|   area STRING,                                                                                     |
|   city STRING,                                                                                     |
|   os STRING,                                                                                       |
|   ov INT,                                                                                          |
|   bs STRING,                                                                                       |
|   bv INT,                                                                                          |
|   utm_source STRING,                                                                               |
|   utm_medium STRING,                                                                               |
|   utm_campaign STRING,                                                                             |
|   utm_content STRING,                                                                              |
|   utm_term STRING,                                                                                 |
|   duration BIGINT,                                                                                 |
|   utc_date BIGINT,                                                                                 |
|   attr1 STRING,                                                                                    |
|   attr2 STRING,                                                                                    |
|   attr3 STRING,                                                                                    |
|   attr4 STRING,                                                                                    |
|   attr5 STRING                                                                                     |
| )                                                                                                  |
| PARTITIONED BY (                                                                                   |
|   yw INT                                                                                           |
| )                                                                                                  |
| STORED AS PARQUET                                                                                  |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_b_user_event_all_6_20190420'        |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='-1', 'totalSize'='27956269322') |
+----------------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------------+
| result                                                                                          |
+-------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_b_user_event_all_a_2_20200318 (                                     |
|   zg_id BIGINT,                                                                                 |
|   session_id BIGINT,                                                                            |
|   uuid STRING,                                                                                  |
|   event_id BIGINT,                                                                              |
|   begin_date BIGINT,                                                                            |
|   begin_time_id INT,                                                                            |
|   device_id BIGINT,                                                                             |
|   user_id BIGINT,                                                                               |
|   event_name STRING,                                                                            |
|   begin_day_id INT,                                                                             |
|   platform SMALLINT,                                                                            |
|   network SMALLINT,                                                                             |
|   mccmnc INT,                                                                                   |
|   useragent STRING,                                                                             |
|   website STRING,                                                                               |
|   current_url STRING,                                                                           |
|   referrer_url STRING,                                                                          |
|   channel STRING,                                                                               |
|   app_version STRING,                                                                           |
|   ip BIGINT,                                                                                    |
|   ip_str STRING,                                                                                |
|   country STRING,                                                                               |
|   area STRING,                                                                                  |
|   city STRING,                                                                                  |
|   os STRING,                                                                                    |
|   ov INT,                                                                                       |
|   bs STRING,                                                                                    |
|   bv INT,                                                                                       |
|   utm_source STRING,                                                                            |
|   utm_medium STRING,                                                                            |
|   utm_campaign STRING,                                                                          |
|   utm_content STRING,                                                                           |
|   utm_term STRING,                                                                              |
|   duration BIGINT,                                                                              |
|   utc_date BIGINT,                                                                              |
|   attr1 STRING,                                                                                 |
|   attr2 STRING,                                                                                 |
|   attr3 STRING,                                                                                 |
|   attr4 STRING,                                                                                 |
|   attr5 STRING                                                                                  |
| )                                                                                               |
| PARTITIONED BY (                                                                                |
|   yw INT                                                                                        |
| )                                                                                               |
| STORED AS PARQUET                                                                               |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_b_user_event_all_a_2_20200318'   |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='-1', 'totalSize'='60256891') |
+-------------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------------+
| result                                                                                          |
+-------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_b_user_event_all_b_2_20200318 (                                     |
|   zg_id BIGINT,                                                                                 |
|   session_id BIGINT,                                                                            |
|   uuid STRING,                                                                                  |
|   event_id BIGINT,                                                                              |
|   begin_date BIGINT,                                                                            |
|   begin_time_id INT,                                                                            |
|   device_id BIGINT,                                                                             |
|   user_id BIGINT,                                                                               |
|   event_name STRING,                                                                            |
|   begin_day_id INT,                                                                             |
|   platform SMALLINT,                                                                            |
|   network SMALLINT,                                                                             |
|   mccmnc INT,                                                                                   |
|   useragent STRING,                                                                             |
|   website STRING,                                                                               |
|   current_url STRING,                                                                           |
|   referrer_url STRING,                                                                          |
|   channel STRING,                                                                               |
|   app_version STRING,                                                                           |
|   ip BIGINT,                                                                                    |
|   ip_str STRING,                                                                                |
|   country STRING,                                                                               |
|   area STRING,                                                                                  |
|   city STRING,                                                                                  |
|   os STRING,                                                                                    |
|   ov INT,                                                                                       |
|   bs STRING,                                                                                    |
|   bv INT,                                                                                       |
|   utm_source STRING,                                                                            |
|   utm_medium STRING,                                                                            |
|   utm_campaign STRING,                                                                          |
|   utm_content STRING,                                                                           |
|   utm_term STRING,                                                                              |
|   duration BIGINT,                                                                              |
|   utc_date BIGINT,                                                                              |
|   attr1 STRING,                                                                                 |
|   attr2 STRING,                                                                                 |
|   attr3 STRING,                                                                                 |
|   attr4 STRING,                                                                                 |
|   attr5 STRING                                                                                  |
| )                                                                                               |
| PARTITIONED BY (                                                                                |
|   yw INT                                                                                        |
| )                                                                                               |
| STORED AS PARQUET                                                                               |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_b_user_event_all_b_2_20200318'   |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='-1', 'totalSize'='60256891') |
+-------------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------------+
| result                                                                                         |
+------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_b_user_event_attr_a_2_20200318 (                                   |
|   zg_id BIGINT,                                                                                |
|   session_id BIGINT,                                                                           |
|   uuid STRING,                                                                                 |
|   event_id BIGINT,                                                                             |
|   begin_date BIGINT,                                                                           |
|   begin_time_id INT,                                                                           |
|   device_id BIGINT,                                                                            |
|   user_id BIGINT,                                                                              |
|   event_name STRING,                                                                           |
|   begin_day_id INT,                                                                            |
|   platform SMALLINT,                                                                           |
|   network SMALLINT,                                                                            |
|   mccmnc INT,                                                                                  |
|   useragent STRING,                                                                            |
|   website STRING,                                                                              |
|   current_url STRING,                                                                          |
|   referrer_url STRING,                                                                         |
|   channel STRING,                                                                              |
|   app_version STRING,                                                                          |
|   ip BIGINT,                                                                                   |
|   ip_str STRING,                                                                               |
|   country STRING,                                                                              |
|   area STRING,                                                                                 |
|   city STRING,                                                                                 |
|   os STRING,                                                                                   |
|   ov INT,                                                                                      |
|   bs STRING,                                                                                   |
|   bv INT,                                                                                      |
|   utm_source STRING,                                                                           |
|   utm_medium STRING,                                                                           |
|   utm_campaign STRING,                                                                         |
|   utm_content STRING,                                                                          |
|   utm_term STRING,                                                                             |
|   duration BIGINT,                                                                             |
|   utc_date BIGINT,                                                                             |
|   attr1 STRING,                                                                                |
|   attr2 STRING,                                                                                |
|   attr3 STRING,                                                                                |
|   attr4 STRING,                                                                                |
|   attr5 STRING,                                                                                |
|   cus1 STRING,                                                                                 |
|   cus2 STRING,                                                                                 |
|   cus3 STRING,                                                                                 |
|   cus4 STRING,                                                                                 |
|   cus5 STRING,                                                                                 |
|   cus6 STRING,                                                                                 |
|   cus7 STRING,                                                                                 |
|   cus8 STRING,                                                                                 |
|   cus9 STRING,                                                                                 |
|   cus10 STRING,                                                                                |
|   cus11 STRING,                                                                                |
|   cus12 STRING,                                                                                |
|   cus13 STRING,                                                                                |
|   cus14 STRING,                                                                                |
|   cus15 STRING,                                                                                |
|   cus16 STRING,                                                                                |
|   cus17 STRING,                                                                                |
|   cus18 STRING,                                                                                |
|   cus19 STRING,                                                                                |
|   cus20 STRING,                                                                                |
|   cus21 STRING,                                                                                |
|   cus22 STRING,                                                                                |
|   cus23 STRING,                                                                                |
|   cus24 STRING,                                                                                |
|   cus25 STRING,                                                                                |
|   cus26 STRING,                                                                                |
|   cus27 STRING,                                                                                |
|   cus28 STRING,                                                                                |
|   cus29 STRING,                                                                                |
|   cus30 STRING,                                                                                |
|   cus31 STRING,                                                                                |
|   cus32 STRING,                                                                                |
|   cus33 STRING,                                                                                |
|   cus34 STRING,                                                                                |
|   cus35 STRING,                                                                                |
|   cus36 STRING,                                                                                |
|   cus37 STRING,                                                                                |
|   cus38 STRING,                                                                                |
|   cus39 STRING,                                                                                |
|   cus40 STRING,                                                                                |
|   cus41 STRING,                                                                                |
|   cus42 STRING,                                                                                |
|   cus43 STRING,                                                                                |
|   cus44 STRING,                                                                                |
|   cus45 STRING,                                                                                |
|   cus46 STRING,                                                                                |
|   cus47 STRING,                                                                                |
|   cus48 STRING,                                                                                |
|   cus49 STRING,                                                                                |
|   cus50 STRING,                                                                                |
|   cus51 STRING,                                                                                |
|   cus52 STRING,                                                                                |
|   cus53 STRING,                                                                                |
|   cus54 STRING,                                                                                |
|   cus55 STRING,                                                                                |
|   cus56 STRING,                                                                                |
|   cus57 STRING,                                                                                |
|   cus58 STRING,                                                                                |
|   cus59 STRING,                                                                                |
|   cus60 STRING,                                                                                |
|   cus61 STRING,                                                                                |
|   cus62 STRING,                                                                                |
|   cus63 STRING,                                                                                |
|   cus64 STRING,                                                                                |
|   cus65 STRING,                                                                                |
|   cus66 STRING,                                                                                |
|   cus67 STRING,                                                                                |
|   cus68 STRING,                                                                                |
|   cus69 STRING,                                                                                |
|   cus70 STRING,                                                                                |
|   cus71 STRING,                                                                                |
|   cus72 STRING,                                                                                |
|   cus73 STRING,                                                                                |
|   cus74 STRING,                                                                                |
|   cus75 STRING,                                                                                |
|   cus76 STRING,                                                                                |
|   cus77 STRING,                                                                                |
|   cus78 STRING,                                                                                |
|   cus79 STRING,                                                                                |
|   cus80 STRING,                                                                                |
|   cus81 STRING,                                                                                |
|   cus82 STRING,                                                                                |
|   cus83 STRING,                                                                                |
|   cus84 STRING,                                                                                |
|   cus85 STRING,                                                                                |
|   cus86 STRING,                                                                                |
|   cus87 STRING,                                                                                |
|   cus88 STRING,                                                                                |
|   cus89 STRING,                                                                                |
|   cus90 STRING,                                                                                |
|   cus91 STRING,                                                                                |
|   cus92 STRING,                                                                                |
|   cus93 STRING,                                                                                |
|   cus94 STRING,                                                                                |
|   cus95 STRING,                                                                                |
|   cus96 STRING,                                                                                |
|   cus97 STRING,                                                                                |
|   cus98 STRING,                                                                                |
|   cus99 STRING,                                                                                |
|   cus100 STRING,                                                                               |
|   type1 STRING,                                                                                |
|   type2 STRING,                                                                                |
|   type3 STRING,                                                                                |
|   type4 STRING,                                                                                |
|   type5 STRING,                                                                                |
|   type6 STRING,                                                                                |
|   type7 STRING,                                                                                |
|   type8 STRING,                                                                                |
|   type9 STRING,                                                                                |
|   type10 STRING,                                                                               |
|   type11 STRING,                                                                               |
|   type12 STRING,                                                                               |
|   type13 STRING,                                                                               |
|   type14 STRING,                                                                               |
|   type15 STRING,                                                                               |
|   type16 STRING,                                                                               |
|   type17 STRING,                                                                               |
|   type18 STRING,                                                                               |
|   type19 STRING,                                                                               |
|   type20 STRING,                                                                               |
|   type21 STRING,                                                                               |
|   type22 STRING,                                                                               |
|   type23 STRING,                                                                               |
|   type24 STRING,                                                                               |
|   type25 STRING,                                                                               |
|   type26 STRING,                                                                               |
|   type27 STRING,                                                                               |
|   type28 STRING,                                                                               |
|   type29 STRING,                                                                               |
|   type30 STRING,                                                                               |
|   type31 STRING,                                                                               |
|   type32 STRING,                                                                               |
|   type33 STRING,                                                                               |
|   type34 STRING,                                                                               |
|   type35 STRING,                                                                               |
|   type36 STRING,                                                                               |
|   type37 STRING,                                                                               |
|   type38 STRING,                                                                               |
|   type39 STRING,                                                                               |
|   type40 STRING,                                                                               |
|   type41 STRING,                                                                               |
|   type42 STRING,                                                                               |
|   type43 STRING,                                                                               |
|   type44 STRING,                                                                               |
|   type45 STRING,                                                                               |
|   type46 STRING,                                                                               |
|   type47 STRING,                                                                               |
|   type48 STRING,                                                                               |
|   type49 STRING,                                                                               |
|   type50 STRING,                                                                               |
|   type51 STRING,                                                                               |
|   type52 STRING,                                                                               |
|   type53 STRING,                                                                               |
|   type54 STRING,                                                                               |
|   type55 STRING,                                                                               |
|   type56 STRING,                                                                               |
|   type57 STRING,                                                                               |
|   type58 STRING,                                                                               |
|   type59 STRING,                                                                               |
|   type60 STRING,                                                                               |
|   type61 STRING,                                                                               |
|   type62 STRING,                                                                               |
|   type63 STRING,                                                                               |
|   type64 STRING,                                                                               |
|   type65 STRING,                                                                               |
|   type66 STRING,                                                                               |
|   type67 STRING,                                                                               |
|   type68 STRING,                                                                               |
|   type69 STRING,                                                                               |
|   type70 STRING,                                                                               |
|   type71 STRING,                                                                               |
|   type72 STRING,                                                                               |
|   type73 STRING,                                                                               |
|   type74 STRING,                                                                               |
|   type75 STRING,                                                                               |
|   type76 STRING,                                                                               |
|   type77 STRING,                                                                               |
|   type78 STRING,                                                                               |
|   type79 STRING,                                                                               |
|   type80 STRING,                                                                               |
|   type81 STRING,                                                                               |
|   type82 STRING,                                                                               |
|   type83 STRING,                                                                               |
|   type84 STRING,                                                                               |
|   type85 STRING,                                                                               |
|   type86 STRING,                                                                               |
|   type87 STRING,                                                                               |
|   type88 STRING,                                                                               |
|   type89 STRING,                                                                               |
|   type90 STRING,                                                                               |
|   type91 STRING,                                                                               |
|   type92 STRING,                                                                               |
|   type93 STRING,                                                                               |
|   type94 STRING,                                                                               |
|   type95 STRING,                                                                               |
|   type96 STRING,                                                                               |
|   type97 STRING,                                                                               |
|   type98 STRING,                                                                               |
|   type99 STRING,                                                                               |
|   type100 STRING                                                                               |
| )                                                                                              |
| PARTITIONED BY (                                                                               |
|   eid BIGINT,                                                                                  |
|   yw INT                                                                                       |
| )                                                                                              |
| STORED AS PARQUET                                                                              |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_b_user_event_attr_a_2_20200318' |
| TBLPROPERTIES ('numRows'='-1')                                                                 |
+------------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------------+
| result                                                                                         |
+------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_b_user_event_attr_b_2_20200318 (                                   |
|   zg_id BIGINT,                                                                                |
|   session_id BIGINT,                                                                           |
|   uuid STRING,                                                                                 |
|   event_id BIGINT,                                                                             |
|   begin_date BIGINT,                                                                           |
|   begin_time_id INT,                                                                           |
|   device_id BIGINT,                                                                            |
|   user_id BIGINT,                                                                              |
|   event_name STRING,                                                                           |
|   begin_day_id INT,                                                                            |
|   platform SMALLINT,                                                                           |
|   network SMALLINT,                                                                            |
|   mccmnc INT,                                                                                  |
|   useragent STRING,                                                                            |
|   website STRING,                                                                              |
|   current_url STRING,                                                                          |
|   referrer_url STRING,                                                                         |
|   channel STRING,                                                                              |
|   app_version STRING,                                                                          |
|   ip BIGINT,                                                                                   |
|   ip_str STRING,                                                                               |
|   country STRING,                                                                              |
|   area STRING,                                                                                 |
|   city STRING,                                                                                 |
|   os STRING,                                                                                   |
|   ov INT,                                                                                      |
|   bs STRING,                                                                                   |
|   bv INT,                                                                                      |
|   utm_source STRING,                                                                           |
|   utm_medium STRING,                                                                           |
|   utm_campaign STRING,                                                                         |
|   utm_content STRING,                                                                          |
|   utm_term STRING,                                                                             |
|   duration BIGINT,                                                                             |
|   utc_date BIGINT,                                                                             |
|   attr1 STRING,                                                                                |
|   attr2 STRING,                                                                                |
|   attr3 STRING,                                                                                |
|   attr4 STRING,                                                                                |
|   attr5 STRING,                                                                                |
|   cus1 STRING,                                                                                 |
|   cus2 STRING,                                                                                 |
|   cus3 STRING,                                                                                 |
|   cus4 STRING,                                                                                 |
|   cus5 STRING,                                                                                 |
|   cus6 STRING,                                                                                 |
|   cus7 STRING,                                                                                 |
|   cus8 STRING,                                                                                 |
|   cus9 STRING,                                                                                 |
|   cus10 STRING,                                                                                |
|   cus11 STRING,                                                                                |
|   cus12 STRING,                                                                                |
|   cus13 STRING,                                                                                |
|   cus14 STRING,                                                                                |
|   cus15 STRING,                                                                                |
|   cus16 STRING,                                                                                |
|   cus17 STRING,                                                                                |
|   cus18 STRING,                                                                                |
|   cus19 STRING,                                                                                |
|   cus20 STRING,                                                                                |
|   cus21 STRING,                                                                                |
|   cus22 STRING,                                                                                |
|   cus23 STRING,                                                                                |
|   cus24 STRING,                                                                                |
|   cus25 STRING,                                                                                |
|   cus26 STRING,                                                                                |
|   cus27 STRING,                                                                                |
|   cus28 STRING,                                                                                |
|   cus29 STRING,                                                                                |
|   cus30 STRING,                                                                                |
|   cus31 STRING,                                                                                |
|   cus32 STRING,                                                                                |
|   cus33 STRING,                                                                                |
|   cus34 STRING,                                                                                |
|   cus35 STRING,                                                                                |
|   cus36 STRING,                                                                                |
|   cus37 STRING,                                                                                |
|   cus38 STRING,                                                                                |
|   cus39 STRING,                                                                                |
|   cus40 STRING,                                                                                |
|   cus41 STRING,                                                                                |
|   cus42 STRING,                                                                                |
|   cus43 STRING,                                                                                |
|   cus44 STRING,                                                                                |
|   cus45 STRING,                                                                                |
|   cus46 STRING,                                                                                |
|   cus47 STRING,                                                                                |
|   cus48 STRING,                                                                                |
|   cus49 STRING,                                                                                |
|   cus50 STRING,                                                                                |
|   cus51 STRING,                                                                                |
|   cus52 STRING,                                                                                |
|   cus53 STRING,                                                                                |
|   cus54 STRING,                                                                                |
|   cus55 STRING,                                                                                |
|   cus56 STRING,                                                                                |
|   cus57 STRING,                                                                                |
|   cus58 STRING,                                                                                |
|   cus59 STRING,                                                                                |
|   cus60 STRING,                                                                                |
|   cus61 STRING,                                                                                |
|   cus62 STRING,                                                                                |
|   cus63 STRING,                                                                                |
|   cus64 STRING,                                                                                |
|   cus65 STRING,                                                                                |
|   cus66 STRING,                                                                                |
|   cus67 STRING,                                                                                |
|   cus68 STRING,                                                                                |
|   cus69 STRING,                                                                                |
|   cus70 STRING,                                                                                |
|   cus71 STRING,                                                                                |
|   cus72 STRING,                                                                                |
|   cus73 STRING,                                                                                |
|   cus74 STRING,                                                                                |
|   cus75 STRING,                                                                                |
|   cus76 STRING,                                                                                |
|   cus77 STRING,                                                                                |
|   cus78 STRING,                                                                                |
|   cus79 STRING,                                                                                |
|   cus80 STRING,                                                                                |
|   cus81 STRING,                                                                                |
|   cus82 STRING,                                                                                |
|   cus83 STRING,                                                                                |
|   cus84 STRING,                                                                                |
|   cus85 STRING,                                                                                |
|   cus86 STRING,                                                                                |
|   cus87 STRING,                                                                                |
|   cus88 STRING,                                                                                |
|   cus89 STRING,                                                                                |
|   cus90 STRING,                                                                                |
|   cus91 STRING,                                                                                |
|   cus92 STRING,                                                                                |
|   cus93 STRING,                                                                                |
|   cus94 STRING,                                                                                |
|   cus95 STRING,                                                                                |
|   cus96 STRING,                                                                                |
|   cus97 STRING,                                                                                |
|   cus98 STRING,                                                                                |
|   cus99 STRING,                                                                                |
|   cus100 STRING,                                                                               |
|   type1 STRING,                                                                                |
|   type2 STRING,                                                                                |
|   type3 STRING,                                                                                |
|   type4 STRING,                                                                                |
|   type5 STRING,                                                                                |
|   type6 STRING,                                                                                |
|   type7 STRING,                                                                                |
|   type8 STRING,                                                                                |
|   type9 STRING,                                                                                |
|   type10 STRING,                                                                               |
|   type11 STRING,                                                                               |
|   type12 STRING,                                                                               |
|   type13 STRING,                                                                               |
|   type14 STRING,                                                                               |
|   type15 STRING,                                                                               |
|   type16 STRING,                                                                               |
|   type17 STRING,                                                                               |
|   type18 STRING,                                                                               |
|   type19 STRING,                                                                               |
|   type20 STRING,                                                                               |
|   type21 STRING,                                                                               |
|   type22 STRING,                                                                               |
|   type23 STRING,                                                                               |
|   type24 STRING,                                                                               |
|   type25 STRING,                                                                               |
|   type26 STRING,                                                                               |
|   type27 STRING,                                                                               |
|   type28 STRING,                                                                               |
|   type29 STRING,                                                                               |
|   type30 STRING,                                                                               |
|   type31 STRING,                                                                               |
|   type32 STRING,                                                                               |
|   type33 STRING,                                                                               |
|   type34 STRING,                                                                               |
|   type35 STRING,                                                                               |
|   type36 STRING,                                                                               |
|   type37 STRING,                                                                               |
|   type38 STRING,                                                                               |
|   type39 STRING,                                                                               |
|   type40 STRING,                                                                               |
|   type41 STRING,                                                                               |
|   type42 STRING,                                                                               |
|   type43 STRING,                                                                               |
|   type44 STRING,                                                                               |
|   type45 STRING,                                                                               |
|   type46 STRING,                                                                               |
|   type47 STRING,                                                                               |
|   type48 STRING,                                                                               |
|   type49 STRING,                                                                               |
|   type50 STRING,                                                                               |
|   type51 STRING,                                                                               |
|   type52 STRING,                                                                               |
|   type53 STRING,                                                                               |
|   type54 STRING,                                                                               |
|   type55 STRING,                                                                               |
|   type56 STRING,                                                                               |
|   type57 STRING,                                                                               |
|   type58 STRING,                                                                               |
|   type59 STRING,                                                                               |
|   type60 STRING,                                                                               |
|   type61 STRING,                                                                               |
|   type62 STRING,                                                                               |
|   type63 STRING,                                                                               |
|   type64 STRING,                                                                               |
|   type65 STRING,                                                                               |
|   type66 STRING,                                                                               |
|   type67 STRING,                                                                               |
|   type68 STRING,                                                                               |
|   type69 STRING,                                                                               |
|   type70 STRING,                                                                               |
|   type71 STRING,                                                                               |
|   type72 STRING,                                                                               |
|   type73 STRING,                                                                               |
|   type74 STRING,                                                                               |
|   type75 STRING,                                                                               |
|   type76 STRING,                                                                               |
|   type77 STRING,                                                                               |
|   type78 STRING,                                                                               |
|   type79 STRING,                                                                               |
|   type80 STRING,                                                                               |
|   type81 STRING,                                                                               |
|   type82 STRING,                                                                               |
|   type83 STRING,                                                                               |
|   type84 STRING,                                                                               |
|   type85 STRING,                                                                               |
|   type86 STRING,                                                                               |
|   type87 STRING,                                                                               |
|   type88 STRING,                                                                               |
|   type89 STRING,                                                                               |
|   type90 STRING,                                                                               |
|   type91 STRING,                                                                               |
|   type92 STRING,                                                                               |
|   type93 STRING,                                                                               |
|   type94 STRING,                                                                               |
|   type95 STRING,                                                                               |
|   type96 STRING,                                                                               |
|   type97 STRING,                                                                               |
|   type98 STRING,                                                                               |
|   type99 STRING,                                                                               |
|   type100 STRING                                                                               |
| )                                                                                              |
| PARTITIONED BY (                                                                               |
|   eid BIGINT,                                                                                  |
|   yw INT                                                                                       |
| )                                                                                              |
| STORED AS PARQUET                                                                              |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_b_user_event_attr_b_2_20200318' |
| TBLPROPERTIES ('numRows'='-1')                                                                 |
+------------------------------------------------------------------------------------------------+
+-----------------------------------------------------------------------------------+
| result                                                                            |
+-----------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_device_2_20200318 (                                   |
|   device_id BIGINT,                                                               |
|   device_md5 STRING,                                                              |
|   platform SMALLINT,                                                              |
|   device_type STRING,                                                             |
|   l INT,                                                                          |
|   h INT,                                                                          |
|   device_brand STRING,                                                            |
|   device_model STRING,                                                            |
|   resolution STRING,                                                              |
|   phone STRING,                                                                   |
|   imei STRING,                                                                    |
|   mac STRING,                                                                     |
|   is_prison_break SMALLINT,                                                       |
|   is_crack SMALLINT,                                                              |
|   language STRING,                                                                |
|   timezone STRING,                                                                |
|   attr1 STRING,                                                                   |
|   attr2 STRING,                                                                   |
|   attr3 STRING,                                                                   |
|   attr4 STRING,                                                                   |
|   attr5 STRING,                                                                   |
|   last_update_date BIGINT                                                         |
| )                                                                                 |
| STORED AS PARQUET                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_device_2_20200318' |
|                                                                                   |
+-----------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------+
| result                                                                          |
+---------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_user_2_20200318 (                                   |
|   device_id BIGINT,                                                             |
|   zg_id BIGINT,                                                                 |
|   user_id BIGINT,                                                               |
|   begin_date BIGINT,                                                            |
|   platform SMALLINT                                                             |
| )                                                                               |
| STORED AS PARQUET                                                               |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_user_2_20200318' |
|                                                                                 |
+---------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.backup_user_property_2_20200318 (                                   |
|   zg_id BIGINT,                                                                          |
|   property_id INT,                                                                       |
|   user_id BIGINT,                                                                        |
|   property_name STRING,                                                                  |
|   property_data_type STRING,                                                             |
|   property_value STRING,                                                                 |
|   platform SMALLINT,                                                                     |
|   last_update_date BIGINT                                                                |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/backup_user_property_2_20200318' |
|                                                                                          |
+------------------------------------------------------------------------------------------+
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                                                                                             |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CREATE VIEW zhugeio.category AS                                                                                                                                                                    |
| SELECT count(event_name), zg_id FROM zhugeio.b_user_event_all_11 WHERE event_name = 'teacher_statReport_pageview' AND begin_day_id BETWEEN 20191223 AND 20200331 GROUP BY zg_id ORDER BY zg_id ASC |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------+
| result                                                                                    |
+-------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.etl_log (                                                            |
|   app_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   day_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   etl_name STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   begin_date STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   cluster_name STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   db_name STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   flag INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                   |
|   end_date STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   error_msg STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   PRIMARY KEY (app_id, day_id, etl_name, begin_date)                                      |
| )                                                                                         |
| PARTITION BY HASH (app_id) PARTITIONS 3                                                   |
| STORED AS KUDU                                                                            |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051') |
+-------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------+
| result                                                                                    |
+-------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.etl_mkt_event_2 (                                                    |
|   event_id BIGINT                                                                         |
| )                                                                                         |
| STORED AS PARQUET                                                                         |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/etl_mkt_event_2'                  |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='1', 'totalSize'='340') |
+-------------------------------------------------------------------------------------------+
+--------------------------------------------------------------------+
| result                                                             |
+--------------------------------------------------------------------+
| CREATE TABLE zhugeio.etl_steps (                                   |
|   flag INT,                                                        |
|   etl_name STRING                                                  |
| )                                                                  |
| STORED AS TEXTFILE                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/etl_steps' |
|                                                                    |
+--------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------+
| result                                                                                            |
+---------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.f_user_detail_2 (                                                            |
|   zg_id BIGINT,                                                                                   |
|   first_visit_time BIGINT,                                                                        |
|   last_visit_time BIGINT,                                                                         |
|   first_version STRING,                                                                           |
|   first_channel STRING,                                                                           |
|   current_app_version STRING,                                                                     |
|   current_app_channel STRING,                                                                     |
|   first_website STRING,                                                                           |
|   utm_source STRING,                                                                              |
|   utm_medium STRING,                                                                              |
|   utm_campaign STRING,                                                                            |
|   utm_content STRING,                                                                             |
|   utm_term STRING,                                                                                |
|   first_referrer_url STRING,                                                                      |
|   current_country STRING,                                                                         |
|   current_area STRING,                                                                            |
|   current_city STRING,                                                                            |
|   current_mccmnc INT,                                                                             |
|   current_bs STRING,                                                                              |
|   current_bv INT,                                                                                 |
|   current_os STRING,                                                                              |
|   current_ov INT,                                                                                 |
|   current_l INT,                                                                                  |
|   current_h INT,                                                                                  |
|   current_device_brand STRING,                                                                    |
|   current_device_model STRING,                                                                    |
|   is_registered INT,                                                                              |
|   attr1 STRING,                                                                                   |
|   attr2 STRING,                                                                                   |
|   attr3 STRING,                                                                                   |
|   attr4 STRING,                                                                                   |
|   attr5 STRING                                                                                    |
| )                                                                                                 |
| STORED AS PARQUET                                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/f_user_detail_2'                          |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='39423', 'totalSize'='1064099') |
+---------------------------------------------------------------------------------------------------+
+--------------------------------------------------------------------------------------------------+
| result                                                                                           |
+--------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.f_user_detail_sum_2 (                                                       |
|   zg_id BIGINT,                                                                                  |
|   visit_times INT,                                                                               |
|   duration BIGINT,                                                                               |
|   attr1 STRING,                                                                                  |
|   attr2 STRING,                                                                                  |
|   attr3 STRING,                                                                                  |
|   attr4 STRING,                                                                                  |
|   attr5 STRING                                                                                   |
| )                                                                                                |
| STORED AS PARQUET                                                                                |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/f_user_detail_sum_2'                     |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='39424', 'totalSize'='263438') |
+--------------------------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------+
| result                                                                                            |
+---------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.f_user_join_2 (                                                              |
|   zg_id BIGINT,                                                                                   |
|   device_id BIGINT,                                                                               |
|   begin_date BIGINT,                                                                              |
|   begin_day_id INT,                                                                               |
|   uuid STRING,                                                                                    |
|   yearweek INT,                                                                                   |
|   yearmonth INT,                                                                                  |
|   platform INT                                                                                    |
| )                                                                                                 |
| STORED AS PARQUET                                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/f_user_join_2'                            |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='39422', 'totalSize'='2083672') |
+---------------------------------------------------------------------------------------------------+
+----------------------------------------------------------------------------+
| result                                                                     |
+----------------------------------------------------------------------------+
| CREATE TABLE zhugeio.filter_data_1_1_1 (                                   |
|   uuid STRING                                                              |
| )                                                                          |
| STORED AS PARQUET                                                          |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/filter_data_1_1_1' |
|                                                                            |
+----------------------------------------------------------------------------+
+----------------------------------------------------------------------------+
| result                                                                     |
+----------------------------------------------------------------------------+
| CREATE TABLE zhugeio.funnel_data_1_1_1 (                                   |
|   session_id BIGINT,                                                       |
|   zg_id BIGINT,                                                            |
|   begin_date BIGINT,                                                       |
|   begin_day_id INT,                                                        |
|   step SMALLINT                                                            |
| )                                                                          |
| STORED AS PARQUET                                                          |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/funnel_data_1_1_1' |
|                                                                            |
+----------------------------------------------------------------------------+
+---------------------------------------------------------------------------------+
| result                                                                          |
+---------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.funnel_data_step_1_1_1 (                                   |
|   begin_day_id INT,                                                             |
|   session_id BIGINT,                                                            |
|   zg_id BIGINT,                                                                 |
|   begin_date BIGINT,                                                            |
|   step SMALLINT,                                                                |
|   first_day_id BIGINT                                                           |
| )                                                                               |
| STORED AS PARQUET                                                               |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/funnel_data_step_1_1_1' |
|                                                                                 |
+---------------------------------------------------------------------------------+
+---------------------------------------------------------------------------+
| result                                                                    |
+---------------------------------------------------------------------------+
| CREATE TABLE zhugeio.group_data_1_1_1 (                                   |
|   zg_id BIGINT                                                            |
| )                                                                         |
| STORED AS PARQUET                                                         |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/group_data_1_1_1' |
|                                                                           |
+---------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                              |
+-------------------------------------------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.hdfs_b_user_event_all_2 (                                                                                      |
|   zg_id BIGINT,                                                                                                                     |
|   session_id BIGINT,                                                                                                                |
|   uuid STRING,                                                                                                                      |
|   event_id BIGINT,                                                                                                                  |
|   begin_date BIGINT,                                                                                                                |
|   begin_time_id INT,                                                                                                                |
|   device_id BIGINT,                                                                                                                 |
|   user_id BIGINT,                                                                                                                   |
|   event_name STRING,                                                                                                                |
|   begin_day_id INT,                                                                                                                 |
|   platform SMALLINT,                                                                                                                |
|   network SMALLINT,                                                                                                                 |
|   mccmnc INT,                                                                                                                       |
|   useragent STRING,                                                                                                                 |
|   website STRING,                                                                                                                   |
|   current_url STRING,                                                                                                               |
|   referrer_url STRING,                                                                                                              |
|   channel STRING,                                                                                                                   |
|   app_version STRING,                                                                                                               |
|   ip BIGINT,                                                                                                                        |
|   ip_str STRING,                                                                                                                    |
|   country STRING,                                                                                                                   |
|   area STRING,                                                                                                                      |
|   city STRING,                                                                                                                      |
|   os STRING,                                                                                                                        |
|   ov INT,                                                                                                                           |
|   bs STRING,                                                                                                                        |
|   bv INT,                                                                                                                           |
|   utm_source STRING,                                                                                                                |
|   utm_medium STRING,                                                                                                                |
|   utm_campaign STRING,                                                                                                              |
|   utm_content STRING,                                                                                                               |
|   utm_term STRING,                                                                                                                  |
|   duration BIGINT,                                                                                                                  |
|   utc_date BIGINT,                                                                                                                  |
|   attr1 STRING,                                                                                                                     |
|   attr2 STRING,                                                                                                                     |
|   attr3 STRING,                                                                                                                     |
|   attr4 STRING,                                                                                                                     |
|   attr5 STRING                                                                                                                      |
| )                                                                                                                                   |
| PARTITIONED BY (                                                                                                                    |
|   yw INT                                                                                                                            |
| )                                                                                                                                   |
| STORED AS PARQUET                                                                                                                   |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/hdfs_b_user_event_all_2'                                                    |
| TBLPROPERTIES ('DO_NOT_UPDATE_STATS'='true', 'STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='2688341', 'totalSize'='144257127') |
+-------------------------------------------------------------------------------------------------------------------------------------+
+-----------------------------------------------------------------------------------+
| result                                                                            |
+-----------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.hdfs_b_user_event_attr_2 (                                   |
|   zg_id BIGINT,                                                                   |
|   session_id BIGINT,                                                              |
|   uuid STRING,                                                                    |
|   event_id BIGINT,                                                                |
|   begin_date BIGINT,                                                              |
|   begin_time_id INT,                                                              |
|   device_id BIGINT,                                                               |
|   user_id BIGINT,                                                                 |
|   event_name STRING,                                                              |
|   begin_day_id INT,                                                               |
|   platform SMALLINT,                                                              |
|   network SMALLINT,                                                               |
|   mccmnc INT,                                                                     |
|   useragent STRING,                                                               |
|   website STRING,                                                                 |
|   current_url STRING,                                                             |
|   referrer_url STRING,                                                            |
|   channel STRING,                                                                 |
|   app_version STRING,                                                             |
|   ip BIGINT,                                                                      |
|   ip_str STRING,                                                                  |
|   country STRING,                                                                 |
|   area STRING,                                                                    |
|   city STRING,                                                                    |
|   os STRING,                                                                      |
|   ov INT,                                                                         |
|   bs STRING,                                                                      |
|   bv INT,                                                                         |
|   utm_source STRING,                                                              |
|   utm_medium STRING,                                                              |
|   utm_campaign STRING,                                                            |
|   utm_content STRING,                                                             |
|   utm_term STRING,                                                                |
|   duration BIGINT,                                                                |
|   utc_date BIGINT,                                                                |
|   attr1 STRING,                                                                   |
|   attr2 STRING,                                                                   |
|   attr3 STRING,                                                                   |
|   attr4 STRING,                                                                   |
|   attr5 STRING,                                                                   |
|   cus1 STRING,                                                                    |
|   cus2 STRING,                                                                    |
|   cus3 STRING,                                                                    |
|   cus4 STRING,                                                                    |
|   cus5 STRING,                                                                    |
|   cus6 STRING,                                                                    |
|   cus7 STRING,                                                                    |
|   cus8 STRING,                                                                    |
|   cus9 STRING,                                                                    |
|   cus10 STRING,                                                                   |
|   cus11 STRING,                                                                   |
|   cus12 STRING,                                                                   |
|   cus13 STRING,                                                                   |
|   cus14 STRING,                                                                   |
|   cus15 STRING,                                                                   |
|   cus16 STRING,                                                                   |
|   cus17 STRING,                                                                   |
|   cus18 STRING,                                                                   |
|   cus19 STRING,                                                                   |
|   cus20 STRING,                                                                   |
|   cus21 STRING,                                                                   |
|   cus22 STRING,                                                                   |
|   cus23 STRING,                                                                   |
|   cus24 STRING,                                                                   |
|   cus25 STRING,                                                                   |
|   cus26 STRING,                                                                   |
|   cus27 STRING,                                                                   |
|   cus28 STRING,                                                                   |
|   cus29 STRING,                                                                   |
|   cus30 STRING,                                                                   |
|   cus31 STRING,                                                                   |
|   cus32 STRING,                                                                   |
|   cus33 STRING,                                                                   |
|   cus34 STRING,                                                                   |
|   cus35 STRING,                                                                   |
|   cus36 STRING,                                                                   |
|   cus37 STRING,                                                                   |
|   cus38 STRING,                                                                   |
|   cus39 STRING,                                                                   |
|   cus40 STRING,                                                                   |
|   cus41 STRING,                                                                   |
|   cus42 STRING,                                                                   |
|   cus43 STRING,                                                                   |
|   cus44 STRING,                                                                   |
|   cus45 STRING,                                                                   |
|   cus46 STRING,                                                                   |
|   cus47 STRING,                                                                   |
|   cus48 STRING,                                                                   |
|   cus49 STRING,                                                                   |
|   cus50 STRING,                                                                   |
|   cus51 STRING,                                                                   |
|   cus52 STRING,                                                                   |
|   cus53 STRING,                                                                   |
|   cus54 STRING,                                                                   |
|   cus55 STRING,                                                                   |
|   cus56 STRING,                                                                   |
|   cus57 STRING,                                                                   |
|   cus58 STRING,                                                                   |
|   cus59 STRING,                                                                   |
|   cus60 STRING,                                                                   |
|   cus61 STRING,                                                                   |
|   cus62 STRING,                                                                   |
|   cus63 STRING,                                                                   |
|   cus64 STRING,                                                                   |
|   cus65 STRING,                                                                   |
|   cus66 STRING,                                                                   |
|   cus67 STRING,                                                                   |
|   cus68 STRING,                                                                   |
|   cus69 STRING,                                                                   |
|   cus70 STRING,                                                                   |
|   cus71 STRING,                                                                   |
|   cus72 STRING,                                                                   |
|   cus73 STRING,                                                                   |
|   cus74 STRING,                                                                   |
|   cus75 STRING,                                                                   |
|   cus76 STRING,                                                                   |
|   cus77 STRING,                                                                   |
|   cus78 STRING,                                                                   |
|   cus79 STRING,                                                                   |
|   cus80 STRING,                                                                   |
|   cus81 STRING,                                                                   |
|   cus82 STRING,                                                                   |
|   cus83 STRING,                                                                   |
|   cus84 STRING,                                                                   |
|   cus85 STRING,                                                                   |
|   cus86 STRING,                                                                   |
|   cus87 STRING,                                                                   |
|   cus88 STRING,                                                                   |
|   cus89 STRING,                                                                   |
|   cus90 STRING,                                                                   |
|   cus91 STRING,                                                                   |
|   cus92 STRING,                                                                   |
|   cus93 STRING,                                                                   |
|   cus94 STRING,                                                                   |
|   cus95 STRING,                                                                   |
|   cus96 STRING,                                                                   |
|   cus97 STRING,                                                                   |
|   cus98 STRING,                                                                   |
|   cus99 STRING,                                                                   |
|   cus100 STRING,                                                                  |
|   type1 STRING,                                                                   |
|   type2 STRING,                                                                   |
|   type3 STRING,                                                                   |
|   type4 STRING,                                                                   |
|   type5 STRING,                                                                   |
|   type6 STRING,                                                                   |
|   type7 STRING,                                                                   |
|   type8 STRING,                                                                   |
|   type9 STRING,                                                                   |
|   type10 STRING,                                                                  |
|   type11 STRING,                                                                  |
|   type12 STRING,                                                                  |
|   type13 STRING,                                                                  |
|   type14 STRING,                                                                  |
|   type15 STRING,                                                                  |
|   type16 STRING,                                                                  |
|   type17 STRING,                                                                  |
|   type18 STRING,                                                                  |
|   type19 STRING,                                                                  |
|   type20 STRING,                                                                  |
|   type21 STRING,                                                                  |
|   type22 STRING,                                                                  |
|   type23 STRING,                                                                  |
|   type24 STRING,                                                                  |
|   type25 STRING,                                                                  |
|   type26 STRING,                                                                  |
|   type27 STRING,                                                                  |
|   type28 STRING,                                                                  |
|   type29 STRING,                                                                  |
|   type30 STRING,                                                                  |
|   type31 STRING,                                                                  |
|   type32 STRING,                                                                  |
|   type33 STRING,                                                                  |
|   type34 STRING,                                                                  |
|   type35 STRING,                                                                  |
|   type36 STRING,                                                                  |
|   type37 STRING,                                                                  |
|   type38 STRING,                                                                  |
|   type39 STRING,                                                                  |
|   type40 STRING,                                                                  |
|   type41 STRING,                                                                  |
|   type42 STRING,                                                                  |
|   type43 STRING,                                                                  |
|   type44 STRING,                                                                  |
|   type45 STRING,                                                                  |
|   type46 STRING,                                                                  |
|   type47 STRING,                                                                  |
|   type48 STRING,                                                                  |
|   type49 STRING,                                                                  |
|   type50 STRING,                                                                  |
|   type51 STRING,                                                                  |
|   type52 STRING,                                                                  |
|   type53 STRING,                                                                  |
|   type54 STRING,                                                                  |
|   type55 STRING,                                                                  |
|   type56 STRING,                                                                  |
|   type57 STRING,                                                                  |
|   type58 STRING,                                                                  |
|   type59 STRING,                                                                  |
|   type60 STRING,                                                                  |
|   type61 STRING,                                                                  |
|   type62 STRING,                                                                  |
|   type63 STRING,                                                                  |
|   type64 STRING,                                                                  |
|   type65 STRING,                                                                  |
|   type66 STRING,                                                                  |
|   type67 STRING,                                                                  |
|   type68 STRING,                                                                  |
|   type69 STRING,                                                                  |
|   type70 STRING,                                                                  |
|   type71 STRING,                                                                  |
|   type72 STRING,                                                                  |
|   type73 STRING,                                                                  |
|   type74 STRING,                                                                  |
|   type75 STRING,                                                                  |
|   type76 STRING,                                                                  |
|   type77 STRING,                                                                  |
|   type78 STRING,                                                                  |
|   type79 STRING,                                                                  |
|   type80 STRING,                                                                  |
|   type81 STRING,                                                                  |
|   type82 STRING,                                                                  |
|   type83 STRING,                                                                  |
|   type84 STRING,                                                                  |
|   type85 STRING,                                                                  |
|   type86 STRING,                                                                  |
|   type87 STRING,                                                                  |
|   type88 STRING,                                                                  |
|   type89 STRING,                                                                  |
|   type90 STRING,                                                                  |
|   type91 STRING,                                                                  |
|   type92 STRING,                                                                  |
|   type93 STRING,                                                                  |
|   type94 STRING,                                                                  |
|   type95 STRING,                                                                  |
|   type96 STRING,                                                                  |
|   type97 STRING,                                                                  |
|   type98 STRING,                                                                  |
|   type99 STRING,                                                                  |
|   type100 STRING                                                                  |
| )                                                                                 |
| PARTITIONED BY (                                                                  |
|   eid BIGINT,                                                                     |
|   yw INT                                                                          |
| )                                                                                 |
| STORED AS PARQUET                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/hdfs_b_user_event_attr_2' |
|                                                                                   |
+-----------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------+
| result                                                                                    |
+-------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.kudu_b_user_event_all_a_2 (                                          |
|   zg_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   session_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   uuid STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   event_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   begin_date BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   begin_time_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   device_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   user_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   event_name STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   begin_day_id INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   platform SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   network SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   mccmnc INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   useragent STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   website STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   current_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   referrer_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   channel STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   app_version STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   ip BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ip_str STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   country STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   area STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   city STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   os STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ov INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   bs STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   bv INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   utm_source STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_medium STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_campaign STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   utm_content STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   utm_term STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   duration BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   utc_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   attr1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   yw INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   PRIMARY KEY (zg_id, session_id, uuid, event_id, begin_date, begin_time_id)              |
| )                                                                                         |
| PARTITION BY HASH (zg_id) PARTITIONS 2                                                    |
| STORED AS KUDU                                                                            |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051') |
+-------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------+
| result                                                                                    |
+-------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.kudu_b_user_event_all_b_2 (                                          |
|   zg_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   session_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   uuid STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   event_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   begin_date BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   begin_time_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   device_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   user_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   event_name STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   begin_day_id INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   platform SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   network SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   mccmnc INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   useragent STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   website STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   current_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   referrer_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   channel STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   app_version STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   ip BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ip_str STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   country STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   area STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   city STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   os STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ov INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   bs STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   bv INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   utm_source STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_medium STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_campaign STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   utm_content STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   utm_term STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   duration BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   utc_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   attr1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   yw INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   PRIMARY KEY (zg_id, session_id, uuid, event_id, begin_date, begin_time_id)              |
| )                                                                                         |
| PARTITION BY HASH (zg_id) PARTITIONS 2                                                    |
| STORED AS KUDU                                                                            |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051') |
+-------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------+
| result                                                                                    |
+-------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.kudu_b_user_event_attr_a_2 (                                         |
|   zg_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   session_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   uuid STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   event_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   begin_date BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   begin_time_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   device_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   user_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   event_name STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   begin_day_id INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   platform SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   network SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   mccmnc INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   useragent STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   website STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   current_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   referrer_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   channel STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   app_version STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   ip BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ip_str STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   country STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   area STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   city STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   os STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ov INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   bs STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   bv INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   utm_source STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_medium STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_campaign STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   utm_content STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   utm_term STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   duration BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   utc_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   attr1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus6 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus7 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus8 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus9 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus10 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus11 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus12 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus13 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus14 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus15 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus16 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus17 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus18 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus19 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus20 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus21 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus22 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus23 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus24 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus25 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus26 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus27 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus28 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus29 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus30 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus31 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus32 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus33 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus34 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus35 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus36 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus37 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus38 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus39 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus40 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus41 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus42 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus43 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus44 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus45 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus46 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus47 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus48 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus49 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus50 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus51 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus52 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus53 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus54 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus55 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus56 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus57 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus58 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus59 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus60 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus61 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus62 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus63 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus64 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus65 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus66 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus67 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus68 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus69 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus70 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus71 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus72 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus73 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus74 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus75 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus76 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus77 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus78 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus79 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus80 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus81 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus82 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus83 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus84 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus85 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus86 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus87 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus88 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus89 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus90 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus91 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus92 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus93 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus94 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus95 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus96 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus97 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus98 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus99 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus100 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type6 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type7 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type8 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type9 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type10 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type11 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type12 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type13 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type14 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type15 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type16 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type17 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type18 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type19 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type20 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type21 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type22 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type23 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type24 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type25 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type26 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type27 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type28 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type29 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type30 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type31 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type32 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type33 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type34 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type35 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type36 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type37 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type38 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type39 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type40 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type41 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type42 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type43 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type44 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type45 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type46 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type47 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type48 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type49 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type50 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type51 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type52 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type53 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type54 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type55 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type56 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type57 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type58 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type59 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type60 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type61 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type62 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type63 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type64 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type65 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type66 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type67 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type68 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type69 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type70 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type71 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type72 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type73 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type74 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type75 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type76 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type77 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type78 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type79 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type80 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type81 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type82 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type83 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type84 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type85 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type86 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type87 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type88 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type89 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type90 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type91 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type92 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type93 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type94 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type95 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type96 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type97 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type98 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type99 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type100 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   eid BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   yw INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   PRIMARY KEY (zg_id, session_id, uuid, event_id, begin_date, begin_time_id)              |
| )                                                                                         |
| PARTITION BY HASH (zg_id) PARTITIONS 2                                                    |
| STORED AS KUDU                                                                            |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051') |
+-------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------+
| result                                                                                    |
+-------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.kudu_b_user_event_attr_b_2 (                                         |
|   zg_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   session_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   uuid STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   event_id BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   begin_date BIGINT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   begin_time_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   device_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   user_id BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   event_name STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   begin_day_id INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   platform SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   network SMALLINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   mccmnc INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   useragent STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,           |
|   website STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   current_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   referrer_url STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   channel STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   app_version STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   ip BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ip_str STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   country STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   area STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   city STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   os STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   ov INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   bs STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   bv INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   utm_source STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_medium STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_campaign STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,        |
|   utm_content STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   utm_term STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   duration BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   utc_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   attr1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   attr5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus6 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus7 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus8 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus9 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   cus10 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus11 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus12 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus13 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus14 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus15 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus16 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus17 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus18 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus19 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus20 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus21 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus22 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus23 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus24 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus25 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus26 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus27 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus28 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus29 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus30 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus31 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus32 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus33 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus34 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus35 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus36 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus37 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus38 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus39 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus40 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus41 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus42 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus43 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus44 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus45 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus46 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus47 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus48 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus49 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus50 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus51 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus52 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus53 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus54 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus55 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus56 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus57 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus58 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus59 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus60 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus61 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus62 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus63 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus64 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus65 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus66 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus67 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus68 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus69 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus70 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus71 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus72 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus73 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus74 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus75 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus76 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus77 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus78 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus79 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus80 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus81 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus82 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus83 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus84 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus85 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus86 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus87 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus88 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus89 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus90 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus91 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus92 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus93 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus94 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus95 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus96 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus97 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus98 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus99 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   cus100 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type1 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type2 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type3 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type4 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type5 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type6 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type7 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type8 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type9 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,               |
|   type10 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type11 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type12 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type13 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type14 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type15 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type16 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type17 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type18 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type19 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type20 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type21 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type22 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type23 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type24 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type25 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type26 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type27 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type28 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type29 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type30 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type31 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type32 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type33 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type34 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type35 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type36 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type37 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type38 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type39 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type40 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type41 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type42 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type43 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type44 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type45 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type46 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type47 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type48 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type49 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type50 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type51 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type52 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type53 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type54 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type55 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type56 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type57 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type58 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type59 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type60 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type61 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type62 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type63 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type64 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type65 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type66 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type67 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type68 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type69 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type70 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type71 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type72 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type73 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type74 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type75 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type76 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type77 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type78 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type79 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type80 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type81 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type82 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type83 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type84 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type85 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type86 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type87 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type88 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type89 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type90 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type91 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type92 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type93 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type94 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type95 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type96 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type97 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type98 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type99 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,              |
|   type100 STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   eid BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   yw INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   PRIMARY KEY (zg_id, session_id, uuid, event_id, begin_date, begin_time_id)              |
| )                                                                                         |
| PARTITION BY HASH (zg_id) PARTITIONS 2                                                    |
| STORED AS KUDU                                                                            |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051') |
+-------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------------------+
| result                                                                                                |
+-------------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.kudu_sem_kpi (                                                                   |
|   day_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   campaign_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   adgroup_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   keyword_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   creative_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   company_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   device_type_int INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   begin_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                      |
|   utm_medium STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                      |
|   utm_source STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                      |
|   sem_account STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   campaign STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                        |
|   adgroup STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   keyword STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   creative STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                        |
|   impression INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   ctr STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                             |
|   click INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                              |
|   cost STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                            |
|   target_domain STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                   |
|   city STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                            |
|   device_type STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   keyword_rank STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                    |
|   PRIMARY KEY (day_id, campaign_id, adgroup_id, keyword_id, creative_id, company_id, device_type_int) |
| )                                                                                                     |
| PARTITION BY HASH (day_id) PARTITIONS 2                                                               |
| STORED AS KUDU                                                                                        |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051')             |
+-------------------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------+
| result                                                                                    |
+-------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.kudu_sem_meta (                                                      |
|   company_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   campaign_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,     |
|   adgroup_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   keyword_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,      |
|   creative_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,     |
|   utm_medium STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   utm_source STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,          |
|   sem_account STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,         |
|   campaign STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   adgroup STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   keyword STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,             |
|   creative STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,            |
|   PRIMARY KEY (company_id, campaign_id, adgroup_id, keyword_id, creative_id)              |
| )                                                                                         |
| PARTITION BY HASH (campaign_id) PARTITIONS 2                                              |
| STORED AS KUDU                                                                            |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051') |
+-------------------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------------------------------+
| result                                                                                                |
+-------------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.kudu_sem_query_word_kpi (                                                        |
|   day_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   campaign_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   adgroup_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   keyword_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                  |
|   creative_id STRING NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                 |
|   company_id INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   device_type_int INT NOT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                |
|   begin_date BIGINT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                      |
|   utm_medium STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                      |
|   utm_source STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                      |
|   sem_account STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   campaign STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                        |
|   adgroup STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   keyword STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   creative STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                        |
|   impression INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                         |
|   ctr STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                             |
|   click INT NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                              |
|   cost STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                            |
|   target_domain STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                   |
|   city STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                            |
|   device_type STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                     |
|   query_word STRING NULL ENCODING AUTO_ENCODING COMPRESSION DEFAULT_COMPRESSION,                      |
|   PRIMARY KEY (day_id, campaign_id, adgroup_id, keyword_id, creative_id, company_id, device_type_int) |
| )                                                                                                     |
| PARTITION BY HASH (day_id) PARTITIONS 2                                                               |
| STORED AS KUDU                                                                                        |
| TBLPROPERTIES ('kudu.master_addresses'='realtime-1:7051,realtime-2:7051,realtime-3:7051')             |
+-------------------------------------------------------------------------------------------------------+
+-----------------------------------------------------------------+
| result                                                          |
+-----------------------------------------------------------------+
| CREATE TABLE zhugeio.mccmnc (                                   |
|   mccmnc INT,                                                   |
|   name STRING                                                   |
| )                                                               |
| STORED AS TEXTFILE                                              |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/mccmnc' |
|                                                                 |
+-----------------------------------------------------------------+
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| result                                                                                                                                                                                             |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
| CREATE VIEW zhugeio.model AS                                                                                                                                                                       |
| SELECT count(event_name), zg_id FROM zhugeio.b_user_event_all_11 WHERE event_name = 'teacher_statReport_pageview' AND begin_day_id BETWEEN 20191223 AND 20200331 GROUP BY zg_id ORDER BY zg_id ASC |
+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
+------------------------------------------------------------------+
| result                                                           |
+------------------------------------------------------------------+
| CREATE TABLE zhugeio.network (                                   |
|   network INT,                                                   |
|   name STRING                                                    |
| )                                                                |
| STORED AS TEXTFILE                                               |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/network' |
|                                                                  |
+------------------------------------------------------------------+
+---------------------------------------------------------------------------+
| result                                                                    |
+---------------------------------------------------------------------------+
| CREATE TABLE zhugeio.order_data_1_1_1 (                                   |
|   zg_id BIGINT,                                                           |
|   run_times BIGINT,                                                       |
|   first_date BIGINT,                                                      |
|   random_id DOUBLE                                                        |
| )                                                                         |
| STORED AS PARQUET                                                         |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/order_data_1_1_1' |
|                                                                           |
+---------------------------------------------------------------------------+
+---------------------------------------------------------------------------+
| result                                                                    |
+---------------------------------------------------------------------------+
| CREATE TABLE zhugeio.order_data_1_1_3 (                                   |
|   zg_id BIGINT,                                                           |
|   run_times BIGINT,                                                       |
|   first_date BIGINT,                                                      |
|   random_id DOUBLE,                                                       |
|   last_visit_time BIGINT                                                  |
| )                                                                         |
| STORED AS PARQUET                                                         |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/order_data_1_1_3' |
|                                                                           |
+---------------------------------------------------------------------------+
+-------------------------------------------------------------------+
| result                                                            |
+-------------------------------------------------------------------+
| CREATE TABLE zhugeio.platform (                                   |
|   platform INT,                                                   |
|   name STRING                                                     |
| )                                                                 |
| STORED AS TEXTFILE                                                |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/platform' |
|                                                                   |
+-------------------------------------------------------------------+
+-------------------------------------------------------------------------------+
| result                                                                        |
+-------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.retention_data_1_1_1 (                                   |
|   zg_id BIGINT,                                                               |
|   day_id INT,                                                                 |
|   yearweek INT                                                                |
| )                                                                             |
| STORED AS PARQUET                                                             |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/retention_data_1_1_1' |
|                                                                               |
+-------------------------------------------------------------------------------+
+-------------------------------------------------------------------------------+
| result                                                                        |
+-------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.retention_data_1_1_3 (                                   |
|   zg_id BIGINT,                                                               |
|   day_id INT,                                                                 |
|   yearweek INT,                                                               |
|   yearmonth INT                                                               |
| )                                                                             |
| STORED AS PARQUET                                                             |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/retention_data_1_1_3' |
|                                                                               |
+-------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------+
| result                                                                             |
+------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.retention_data_step_1_1_1 (                                   |
|   zg_id BIGINT,                                                                    |
|   day_id INT,                                                                      |
|   yearweek INT                                                                     |
| )                                                                                  |
| STORED AS PARQUET                                                                  |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/retention_data_step_1_1_1' |
|                                                                                    |
+------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------+
| result                                                                             |
+------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.retention_data_step_1_1_3 (                                   |
|   zg_id BIGINT,                                                                    |
|   day_id INT,                                                                      |
|   yearweek INT,                                                                    |
|   yearmonth INT                                                                    |
| )                                                                                  |
| STORED AS PARQUET                                                                  |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/retention_data_step_1_1_3' |
|                                                                                    |
+------------------------------------------------------------------------------------+
+--------------------------------------------------------------------------------------------------+
| result                                                                                           |
+--------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.t_user_active_2 (                                                           |
|   zg_id BIGINT,                                                                                  |
|   begin_day_id INT,                                                                              |
|   times INT,                                                                                     |
|   yearweek INT,                                                                                  |
|   yearmonth INT,                                                                                 |
|   platform INT                                                                                   |
| )                                                                                                |
| STORED AS PARQUET                                                                                |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/t_user_active_2'                         |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='73538', 'totalSize'='407897') |
+--------------------------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------+
| result                                                                                            |
+---------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.t_user_detail_2 (                                                            |
|   zg_id BIGINT,                                                                                   |
|   platform INT,                                                                                   |
|   first_visit_time BIGINT,                                                                        |
|   last_visit_time BIGINT,                                                                         |
|   visit_times INT,                                                                                |
|   duration BIGINT,                                                                                |
|   first_version STRING,                                                                           |
|   first_channel STRING,                                                                           |
|   current_app_version STRING,                                                                     |
|   current_app_channel STRING,                                                                     |
|   first_website STRING,                                                                           |
|   utm_source STRING,                                                                              |
|   utm_medium STRING,                                                                              |
|   utm_campaign STRING,                                                                            |
|   utm_content STRING,                                                                             |
|   utm_term STRING,                                                                                |
|   first_referrer_url STRING,                                                                      |
|   current_country STRING,                                                                         |
|   current_area STRING,                                                                            |
|   current_city STRING,                                                                            |
|   current_mccmnc INT,                                                                             |
|   current_bs STRING,                                                                              |
|   current_bv INT,                                                                                 |
|   current_os STRING,                                                                              |
|   current_ov INT,                                                                                 |
|   current_l INT,                                                                                  |
|   current_h INT,                                                                                  |
|   current_device_brand STRING,                                                                    |
|   current_device_model STRING,                                                                    |
|   is_registered INT,                                                                              |
|   attr1 STRING,                                                                                   |
|   attr2 STRING,                                                                                   |
|   attr3 STRING,                                                                                   |
|   attr4 STRING,                                                                                   |
|   attr5 STRING                                                                                    |
| )                                                                                                 |
| STORED AS PARQUET                                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/t_user_detail_2'                          |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='40577', 'totalSize'='1130297') |
+---------------------------------------------------------------------------------------------------+
+--------------------------------------------------------------------------------------------------+
| result                                                                                           |
+--------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.t_user_detail_sum_2 (                                                       |
|   zg_id BIGINT,                                                                                  |
|   platform INT,                                                                                  |
|   visit_times INT,                                                                               |
|   duration BIGINT,                                                                               |
|   attr1 STRING,                                                                                  |
|   attr2 STRING,                                                                                  |
|   attr3 STRING,                                                                                  |
|   attr4 STRING,                                                                                  |
|   attr5 STRING                                                                                   |
| )                                                                                                |
| STORED AS PARQUET                                                                                |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/t_user_detail_sum_2'                     |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='40578', 'totalSize'='280710') |
+--------------------------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------+
| result                                                                                            |
+---------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.t_user_duration_2 (                                                          |
|   zg_id BIGINT,                                                                                   |
|   day_id INT,                                                                                     |
|   period STRING,                                                                                  |
|   duration BIGINT,                                                                                |
|   times INT,                                                                                      |
|   yearweek INT,                                                                                   |
|   yearmonth INT,                                                                                  |
|   platform INT                                                                                    |
| )                                                                                                 |
| STORED AS PARQUET                                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/t_user_duration_2'                        |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='119561', 'totalSize'='826844') |
+---------------------------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------+
| result                                                                                            |
+---------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.t_user_join_2 (                                                              |
|   zg_id BIGINT,                                                                                   |
|   device_id BIGINT,                                                                               |
|   begin_date BIGINT,                                                                              |
|   begin_day_id INT,                                                                               |
|   uuid STRING,                                                                                    |
|   yearweek INT,                                                                                   |
|   yearmonth INT,                                                                                  |
|   platform INT                                                                                    |
| )                                                                                                 |
| STORED AS PARQUET                                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/t_user_join_2'                            |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='40576', 'totalSize'='2122198') |
+---------------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18989 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18989' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18990 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18990' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18991 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18991' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18992 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18992' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18994 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18994' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18995 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18995' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18996 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18996' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+------------------------------------------------------------------------------------------+
| result                                                                                   |
+------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_filter_data_5_20200605_18997 (                                   |
|   uuid STRING                                                                            |
| )                                                                                        |
| STORED AS PARQUET                                                                        |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_filter_data_5_20200605_18997' |
| TBLPROPERTIES ('numRows'='-1')                                                           |
+------------------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------+
| result                                                                                      |
+---------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_funnel_data_6_20200605_18999 (                                      |
|   session_id BIGINT,                                                                        |
|   zg_id BIGINT,                                                                             |
|   begin_date BIGINT,                                                                        |
|   begin_day_id INT,                                                                         |
|   step SMALLINT                                                                             |
| )                                                                                           |
| STORED AS PARQUET                                                                           |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_funnel_data_6_20200605_18999'    |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='39', 'totalSize'='4472') |
+---------------------------------------------------------------------------------------------+
+-----------------------------------------------------------------------------------------------+
| result                                                                                        |
+-----------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_funnel_data_step_6_20200605_18999 (                                   |
|   begin_day_id INT,                                                                           |
|   session_id BIGINT,                                                                          |
|   zg_id BIGINT,                                                                               |
|   begin_date BIGINT,                                                                          |
|   step SMALLINT,                                                                              |
|   first_day_id BIGINT                                                                         |
| )                                                                                             |
| STORED AS PARQUET                                                                             |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_funnel_data_step_6_20200605_18999' |
| TBLPROPERTIES ('STATS_GENERATED_VIA_STATS_TASK'='true', 'numRows'='4', 'totalSize'='4329')    |
+-----------------------------------------------------------------------------------------------+
+-----------------------------------------------------------------------------------------+
| result                                                                                  |
+-----------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_group_data_5_20200605_18988 (                                   |
|   zg_id BIGINT                                                                          |
| )                                                                                       |
| STORED AS PARQUET                                                                       |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_group_data_5_20200605_18988' |
| TBLPROPERTIES ('numRows'='-1')                                                          |
+-----------------------------------------------------------------------------------------+
+-----------------------------------------------------------------------------------------+
| result                                                                                  |
+-----------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_group_data_5_20200605_18993 (                                   |
|   zg_id BIGINT                                                                          |
| )                                                                                       |
| STORED AS PARQUET                                                                       |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_group_data_5_20200605_18993' |
| TBLPROPERTIES ('numRows'='-1')                                                          |
+-----------------------------------------------------------------------------------------+
+-----------------------------------------------------------------------------------------+
| result                                                                                  |
+-----------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_group_data_6_20200605_18998 (                                   |
|   zg_id BIGINT                                                                          |
| )                                                                                       |
| STORED AS PARQUET                                                                       |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_group_data_6_20200605_18998' |
| TBLPROPERTIES ('numRows'='-1')                                                          |
+-----------------------------------------------------------------------------------------+
+-----------------------------------------------------------------------------------------+
| result                                                                                  |
+-----------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_group_data_6_20200605_19000 (                                   |
|   zg_id BIGINT                                                                          |
| )                                                                                       |
| STORED AS PARQUET                                                                       |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_group_data_6_20200605_19000' |
| TBLPROPERTIES ('numRows'='-1')                                                          |
+-----------------------------------------------------------------------------------------+
+----------------------------------------------------------------------------------------------+
| result                                                                                       |
+----------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_retention_data_20_20200605_19001 (                                   |
|   zg_id BIGINT,                                                                              |
|   day_id INT,                                                                                |
|   yearweek INT,                                                                              |
|   yearmonth INT                                                                              |
| )                                                                                            |
| STORED AS PARQUET                                                                            |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_retention_data_20_20200605_19001' |
| TBLPROPERTIES ('numRows'='-1')                                                               |
+----------------------------------------------------------------------------------------------+
+---------------------------------------------------------------------------------------------------+
| result                                                                                            |
+---------------------------------------------------------------------------------------------------+
| CREATE TABLE zhugeio.v2_retention_data_step_20_20200605_19001 (                                   |
|   zg_id BIGINT,                                                                                   |
|   day_id INT,                                                                                     |
|   yearweek INT,                                                                                   |
|   yearmonth INT                                                                                   |
| )                                                                                                 |
| STORED AS PARQUET                                                                                 |
| LOCATION 'hdfs://zhugeio/user/hive/warehouse/zhugeio.db/v2_retention_data_step_20_20200605_19001' |
| TBLPROPERTIES ('numRows'='-1')                                                                    |
+---------------------------------------------------------------------------------------------------+
```

### 四、所有分区表分区信息

详细描述见文件：[诸葛io平台impala表分区信息.md](./诸葛io平台impala表分区信息.md)

### 五、所有表名列表

```mysql
| apple_models                             |
| b_device_10                              |
| b_device_11                              |
| b_device_12                              |
| b_device_13                              |
| b_device_14                              |
| b_device_15                              |
| b_device_16                              |
| b_device_17                              |
| b_device_18                              |
| b_device_19                              |
| b_device_2                               |
| b_device_20                              |
| b_device_21                              |
| b_device_22                              |
| b_device_23                              |
| b_device_25                              |
| b_device_3                               |
| b_device_4                               |
| b_device_5                               |
| b_device_6                               |
| b_device_7                               |
| b_device_9                               |
| b_user_10                                |
| b_user_11                                |
| b_user_12                                |
| b_user_13                                |
| b_user_14                                |
| b_user_15                                |
| b_user_16                                |
| b_user_17                                |
| b_user_18                                |
| b_user_19                                |
| b_user_2                                 |
| b_user_20                                |
| b_user_21                                |
| b_user_22                                |
| b_user_23                                |
| b_user_25                                |
| b_user_3                                 |
| b_user_4                                 |
| b_user_5                                 |
| b_user_6                                 |
| b_user_7                                 |
| b_user_9                                 |
| b_user_delete_10                         |
| b_user_delete_11                         |
| b_user_delete_12                         |
| b_user_delete_13                         |
| b_user_delete_14                         |
| b_user_delete_15                         |
| b_user_delete_16                         |
| b_user_delete_17                         |
| b_user_delete_18                         |
| b_user_delete_19                         |
| b_user_delete_2                          |
| b_user_delete_20                         |
| b_user_delete_21                         |
| b_user_delete_23                         |
| b_user_delete_25                         |
| b_user_delete_3                          |
| b_user_delete_4                          |
| b_user_delete_5                          |
| b_user_delete_6                          |
| b_user_delete_7                          |
| b_user_delete_9                          |
| b_user_event_all_10                      |
| b_user_event_all_11                      |
| b_user_event_all_12                      |
| b_user_event_all_13                      |
| b_user_event_all_14                      |
| b_user_event_all_15                      |
| b_user_event_all_16                      |
| b_user_event_all_17                      |
| b_user_event_all_18                      |
| b_user_event_all_19                      |
| b_user_event_all_2                       |
| b_user_event_all_20                      |
| b_user_event_all_21                      |
| b_user_event_all_22                      |
| b_user_event_all_23                      |
| b_user_event_all_25                      |
| b_user_event_all_3                       |
| b_user_event_all_4                       |
| b_user_event_all_5                       |
| b_user_event_all_6                       |
| b_user_event_all_7                       |
| b_user_event_all_9                       |
| b_user_event_attr_10                     |
| b_user_event_attr_11                     |
| b_user_event_attr_12                     |
| b_user_event_attr_13                     |
| b_user_event_attr_14                     |
| b_user_event_attr_15                     |
| b_user_event_attr_16                     |
| b_user_event_attr_17                     |
| b_user_event_attr_18                     |
| b_user_event_attr_19                     |
| b_user_event_attr_2                      |
| b_user_event_attr_20                     |
| b_user_event_attr_21                     |
| b_user_event_attr_22                     |
| b_user_event_attr_23                     |
| b_user_event_attr_25                     |
| b_user_event_attr_3                      |
| b_user_event_attr_4                      |
| b_user_event_attr_5                      |
| b_user_event_attr_6                      |
| b_user_event_attr_7                      |
| b_user_event_attr_9                      |
| b_user_has_event_10                      |
| b_user_has_event_11                      |
| b_user_has_event_12                      |
| b_user_has_event_13                      |
| b_user_has_event_14                      |
| b_user_has_event_15                      |
| b_user_has_event_16                      |
| b_user_has_event_17                      |
| b_user_has_event_18                      |
| b_user_has_event_19                      |
| b_user_has_event_2                       |
| b_user_has_event_20                      |
| b_user_has_event_21                      |
| b_user_has_event_23                      |
| b_user_has_event_25                      |
| b_user_has_event_3                       |
| b_user_has_event_4                       |
| b_user_has_event_5                       |
| b_user_has_event_6                       |
| b_user_has_event_7                       |
| b_user_has_event_9                       |
| b_user_no_use_annoy_10                   |
| b_user_no_use_annoy_11                   |
| b_user_no_use_annoy_12                   |
| b_user_no_use_annoy_13                   |
| b_user_no_use_annoy_14                   |
| b_user_no_use_annoy_15                   |
| b_user_no_use_annoy_16                   |
| b_user_no_use_annoy_17                   |
| b_user_no_use_annoy_18                   |
| b_user_no_use_annoy_19                   |
| b_user_no_use_annoy_2                    |
| b_user_no_use_annoy_20                   |
| b_user_no_use_annoy_21                   |
| b_user_no_use_annoy_23                   |
| b_user_no_use_annoy_25                   |
| b_user_no_use_annoy_3                    |
| b_user_no_use_annoy_4                    |
| b_user_no_use_annoy_5                    |
| b_user_no_use_annoy_6                    |
| b_user_no_use_annoy_7                    |
| b_user_no_use_annoy_9                    |
| b_user_property_10                       |
| b_user_property_11                       |
| b_user_property_12                       |
| b_user_property_13                       |
| b_user_property_14                       |
| b_user_property_15                       |
| b_user_property_16                       |
| b_user_property_17                       |
| b_user_property_18                       |
| b_user_property_19                       |
| b_user_property_2                        |
| b_user_property_20                       |
| b_user_property_21                       |
| b_user_property_22                       |
| b_user_property_23                       |
| b_user_property_25                       |
| b_user_property_3                        |
| b_user_property_4                        |
| b_user_property_5                        |
| b_user_property_6                        |
| b_user_property_7                        |
| b_user_property_9                        |
| backup_b_user_event_all_11_20190420      |
| backup_b_user_event_all_6_20190420       |
| backup_b_user_event_all_a_10_20200318    |
| backup_b_user_event_all_a_11_20200318    |
| backup_b_user_event_all_a_12_20200318    |
| backup_b_user_event_all_a_13_20200318    |
| backup_b_user_event_all_a_14_20200318    |
| backup_b_user_event_all_a_15_20200318    |
| backup_b_user_event_all_a_16_20200318    |
| backup_b_user_event_all_a_18_20200318    |
| backup_b_user_event_all_a_19_20200318    |
| backup_b_user_event_all_a_20_20200318    |
| backup_b_user_event_all_a_21_20200318    |
| backup_b_user_event_all_a_22_20200318    |
| backup_b_user_event_all_a_23_20200318    |
| backup_b_user_event_all_a_2_20200318     |
| backup_b_user_event_all_a_3_20200318     |
| backup_b_user_event_all_a_4_20200318     |
| backup_b_user_event_all_a_5_20200318     |
| backup_b_user_event_all_a_6_20200318     |
| backup_b_user_event_all_a_7_20200318     |
| backup_b_user_event_all_a_9_20200318     |
| backup_b_user_event_all_b_10_20200318    |
| backup_b_user_event_all_b_11_20200318    |
| backup_b_user_event_all_b_12_20200318    |
| backup_b_user_event_all_b_13_20200318    |
| backup_b_user_event_all_b_14_20200318    |
| backup_b_user_event_all_b_15_20200318    |
| backup_b_user_event_all_b_16_20200318    |
| backup_b_user_event_all_b_18_20200318    |
| backup_b_user_event_all_b_19_20200318    |
| backup_b_user_event_all_b_20_20200318    |
| backup_b_user_event_all_b_21_20200318    |
| backup_b_user_event_all_b_22_20200318    |
| backup_b_user_event_all_b_23_20200318    |
| backup_b_user_event_all_b_2_20200318     |
| backup_b_user_event_all_b_3_20200318     |
| backup_b_user_event_all_b_4_20200318     |
| backup_b_user_event_all_b_5_20200318     |
| backup_b_user_event_all_b_6_20200318     |
| backup_b_user_event_all_b_7_20200318     |
| backup_b_user_event_all_b_9_20200318     |
| backup_b_user_event_attr_a_10_20200318   |
| backup_b_user_event_attr_a_11_20200318   |
| backup_b_user_event_attr_a_12_20200318   |
| backup_b_user_event_attr_a_13_20200318   |
| backup_b_user_event_attr_a_14_20200318   |
| backup_b_user_event_attr_a_15_20200318   |
| backup_b_user_event_attr_a_16_20200318   |
| backup_b_user_event_attr_a_18_20200318   |
| backup_b_user_event_attr_a_19_20200318   |
| backup_b_user_event_attr_a_20_20200318   |
| backup_b_user_event_attr_a_21_20200318   |
| backup_b_user_event_attr_a_22_20200318   |
| backup_b_user_event_attr_a_23_20200318   |
| backup_b_user_event_attr_a_2_20200318    |
| backup_b_user_event_attr_a_3_20200318    |
| backup_b_user_event_attr_a_4_20200318    |
| backup_b_user_event_attr_a_5_20200318    |
| backup_b_user_event_attr_a_6_20200318    |
| backup_b_user_event_attr_a_7_20200318    |
| backup_b_user_event_attr_a_9_20200318    |
| backup_b_user_event_attr_b_10_20200318   |
| backup_b_user_event_attr_b_11_20200318   |
| backup_b_user_event_attr_b_12_20200318   |
| backup_b_user_event_attr_b_13_20200318   |
| backup_b_user_event_attr_b_14_20200318   |
| backup_b_user_event_attr_b_15_20200318   |
| backup_b_user_event_attr_b_16_20200318   |
| backup_b_user_event_attr_b_18_20200318   |
| backup_b_user_event_attr_b_19_20200318   |
| backup_b_user_event_attr_b_20_20200318   |
| backup_b_user_event_attr_b_21_20200318   |
| backup_b_user_event_attr_b_22_20200318   |
| backup_b_user_event_attr_b_23_20200318   |
| backup_b_user_event_attr_b_2_20200318    |
| backup_b_user_event_attr_b_3_20200318    |
| backup_b_user_event_attr_b_4_20200318    |
| backup_b_user_event_attr_b_5_20200318    |
| backup_b_user_event_attr_b_6_20200318    |
| backup_b_user_event_attr_b_7_20200318    |
| backup_b_user_event_attr_b_9_20200318    |
| backup_device_10_20200318                |
| backup_device_11_20200318                |
| backup_device_12_20200318                |
| backup_device_13_20200318                |
| backup_device_14_20200318                |
| backup_device_15_20200318                |
| backup_device_16_20200318                |
| backup_device_18_20200318                |
| backup_device_19_20200318                |
| backup_device_20_20200318                |
| backup_device_21_20200318                |
| backup_device_22_20200318                |
| backup_device_23_20200318                |
| backup_device_2_20200318                 |
| backup_device_3_20200318                 |
| backup_device_4_20200318                 |
| backup_device_5_20200318                 |
| backup_device_6_20200318                 |
| backup_device_7_20200318                 |
| backup_device_9_20200318                 |
| backup_user_10_20200318                  |
| backup_user_11_20200318                  |
| backup_user_12_20200318                  |
| backup_user_13_20200318                  |
| backup_user_14_20200318                  |
| backup_user_15_20200318                  |
| backup_user_16_20200318                  |
| backup_user_18_20200318                  |
| backup_user_19_20200318                  |
| backup_user_20_20200318                  |
| backup_user_21_20200318                  |
| backup_user_22_20200318                  |
| backup_user_23_20200318                  |
| backup_user_2_20200318                   |
| backup_user_3_20200318                   |
| backup_user_4_20200318                   |
| backup_user_5_20200318                   |
| backup_user_6_20200318                   |
| backup_user_7_20200318                   |
| backup_user_9_20200318                   |
| backup_user_property_10_20200318         |
| backup_user_property_11_20200318         |
| backup_user_property_12_20200318         |
| backup_user_property_13_20200318         |
| backup_user_property_14_20200318         |
| backup_user_property_15_20200318         |
| backup_user_property_16_20200318         |
| backup_user_property_18_20200318         |
| backup_user_property_19_20200318         |
| backup_user_property_20_20200318         |
| backup_user_property_21_20200318         |
| backup_user_property_22_20200318         |
| backup_user_property_23_20200318         |
| backup_user_property_2_20200318          |
| backup_user_property_3_20200318          |
| backup_user_property_4_20200318          |
| backup_user_property_5_20200318          |
| backup_user_property_6_20200318          |
| backup_user_property_7_20200318          |
| backup_user_property_9_20200318          |
| category                                 |
| etl_log                                  |
| etl_mkt_event_10                         |
| etl_mkt_event_11                         |
| etl_mkt_event_12                         |
| etl_mkt_event_13                         |
| etl_mkt_event_14                         |
| etl_mkt_event_15                         |
| etl_mkt_event_16                         |
| etl_mkt_event_17                         |
| etl_mkt_event_18                         |
| etl_mkt_event_19                         |
| etl_mkt_event_2                          |
| etl_mkt_event_20                         |
| etl_mkt_event_21                         |
| etl_mkt_event_23                         |
| etl_mkt_event_25                         |
| etl_mkt_event_3                          |
| etl_mkt_event_4                          |
| etl_mkt_event_5                          |
| etl_mkt_event_6                          |
| etl_mkt_event_7                          |
| etl_mkt_event_9                          |
| etl_steps                                |
| f_user_detail_1                          |
| f_user_detail_10                         |
| f_user_detail_11                         |
| f_user_detail_12                         |
| f_user_detail_13                         |
| f_user_detail_14                         |
| f_user_detail_15                         |
| f_user_detail_16                         |
| f_user_detail_17                         |
| f_user_detail_18                         |
| f_user_detail_19                         |
| f_user_detail_2                          |
| f_user_detail_20                         |
| f_user_detail_21                         |
| f_user_detail_22                         |
| f_user_detail_23                         |
| f_user_detail_25                         |
| f_user_detail_3                          |
| f_user_detail_4                          |
| f_user_detail_5                          |
| f_user_detail_6                          |
| f_user_detail_7                          |
| f_user_detail_9                          |
| f_user_detail_sum_1                      |
| f_user_detail_sum_10                     |
| f_user_detail_sum_11                     |
| f_user_detail_sum_12                     |
| f_user_detail_sum_13                     |
| f_user_detail_sum_14                     |
| f_user_detail_sum_15                     |
| f_user_detail_sum_16                     |
| f_user_detail_sum_17                     |
| f_user_detail_sum_18                     |
| f_user_detail_sum_19                     |
| f_user_detail_sum_2                      |
| f_user_detail_sum_20                     |
| f_user_detail_sum_21                     |
| f_user_detail_sum_22                     |
| f_user_detail_sum_23                     |
| f_user_detail_sum_25                     |
| f_user_detail_sum_3                      |
| f_user_detail_sum_4                      |
| f_user_detail_sum_5                      |
| f_user_detail_sum_6                      |
| f_user_detail_sum_7                      |
| f_user_detail_sum_9                      |
| f_user_join_1                            |
| f_user_join_10                           |
| f_user_join_11                           |
| f_user_join_12                           |
| f_user_join_13                           |
| f_user_join_14                           |
| f_user_join_15                           |
| f_user_join_16                           |
| f_user_join_17                           |
| f_user_join_18                           |
| f_user_join_19                           |
| f_user_join_2                            |
| f_user_join_20                           |
| f_user_join_21                           |
| f_user_join_22                           |
| f_user_join_23                           |
| f_user_join_25                           |
| f_user_join_3                            |
| f_user_join_4                            |
| f_user_join_5                            |
| f_user_join_6                            |
| f_user_join_7                            |
| f_user_join_9                            |
| filter_data_1_1_1                        |
| funnel_data_1_1_1                        |
| funnel_data_step_1_1_1                   |
| group_data_1_1_1                         |
| hdfs_b_user_event_all_10                 |
| hdfs_b_user_event_all_11                 |
| hdfs_b_user_event_all_12                 |
| hdfs_b_user_event_all_13                 |
| hdfs_b_user_event_all_14                 |
| hdfs_b_user_event_all_15                 |
| hdfs_b_user_event_all_16                 |
| hdfs_b_user_event_all_17                 |
| hdfs_b_user_event_all_18                 |
| hdfs_b_user_event_all_19                 |
| hdfs_b_user_event_all_2                  |
| hdfs_b_user_event_all_20                 |
| hdfs_b_user_event_all_21                 |
| hdfs_b_user_event_all_22                 |
| hdfs_b_user_event_all_23                 |
| hdfs_b_user_event_all_25                 |
| hdfs_b_user_event_all_3                  |
| hdfs_b_user_event_all_4                  |
| hdfs_b_user_event_all_5                  |
| hdfs_b_user_event_all_6                  |
| hdfs_b_user_event_all_7                  |
| hdfs_b_user_event_all_9                  |
| hdfs_b_user_event_attr_10                |
| hdfs_b_user_event_attr_11                |
| hdfs_b_user_event_attr_12                |
| hdfs_b_user_event_attr_13                |
| hdfs_b_user_event_attr_14                |
| hdfs_b_user_event_attr_15                |
| hdfs_b_user_event_attr_16                |
| hdfs_b_user_event_attr_17                |
| hdfs_b_user_event_attr_18                |
| hdfs_b_user_event_attr_19                |
| hdfs_b_user_event_attr_2                 |
| hdfs_b_user_event_attr_20                |
| hdfs_b_user_event_attr_21                |
| hdfs_b_user_event_attr_22                |
| hdfs_b_user_event_attr_23                |
| hdfs_b_user_event_attr_25                |
| hdfs_b_user_event_attr_3                 |
| hdfs_b_user_event_attr_4                 |
| hdfs_b_user_event_attr_5                 |
| hdfs_b_user_event_attr_6                 |
| hdfs_b_user_event_attr_7                 |
| hdfs_b_user_event_attr_9                 |
| kudu_b_user_event_all_a_10               |
| kudu_b_user_event_all_a_11               |
| kudu_b_user_event_all_a_12               |
| kudu_b_user_event_all_a_13               |
| kudu_b_user_event_all_a_14               |
| kudu_b_user_event_all_a_15               |
| kudu_b_user_event_all_a_16               |
| kudu_b_user_event_all_a_17               |
| kudu_b_user_event_all_a_18               |
| kudu_b_user_event_all_a_19               |
| kudu_b_user_event_all_a_2                |
| kudu_b_user_event_all_a_20               |
| kudu_b_user_event_all_a_21               |
| kudu_b_user_event_all_a_22               |
| kudu_b_user_event_all_a_23               |
| kudu_b_user_event_all_a_25               |
| kudu_b_user_event_all_a_3                |
| kudu_b_user_event_all_a_4                |
| kudu_b_user_event_all_a_5                |
| kudu_b_user_event_all_a_6                |
| kudu_b_user_event_all_a_7                |
| kudu_b_user_event_all_a_9                |
| kudu_b_user_event_all_b_10               |
| kudu_b_user_event_all_b_11               |
| kudu_b_user_event_all_b_12               |
| kudu_b_user_event_all_b_13               |
| kudu_b_user_event_all_b_14               |
| kudu_b_user_event_all_b_15               |
| kudu_b_user_event_all_b_16               |
| kudu_b_user_event_all_b_17               |
| kudu_b_user_event_all_b_18               |
| kudu_b_user_event_all_b_19               |
| kudu_b_user_event_all_b_2                |
| kudu_b_user_event_all_b_20               |
| kudu_b_user_event_all_b_21               |
| kudu_b_user_event_all_b_22               |
| kudu_b_user_event_all_b_23               |
| kudu_b_user_event_all_b_25               |
| kudu_b_user_event_all_b_3                |
| kudu_b_user_event_all_b_4                |
| kudu_b_user_event_all_b_5                |
| kudu_b_user_event_all_b_6                |
| kudu_b_user_event_all_b_7                |
| kudu_b_user_event_all_b_9                |
| kudu_b_user_event_attr_a_10              |
| kudu_b_user_event_attr_a_11              |
| kudu_b_user_event_attr_a_12              |
| kudu_b_user_event_attr_a_13              |
| kudu_b_user_event_attr_a_14              |
| kudu_b_user_event_attr_a_15              |
| kudu_b_user_event_attr_a_16              |
| kudu_b_user_event_attr_a_17              |
| kudu_b_user_event_attr_a_18              |
| kudu_b_user_event_attr_a_19              |
| kudu_b_user_event_attr_a_2               |
| kudu_b_user_event_attr_a_20              |
| kudu_b_user_event_attr_a_21              |
| kudu_b_user_event_attr_a_22              |
| kudu_b_user_event_attr_a_23              |
| kudu_b_user_event_attr_a_25              |
| kudu_b_user_event_attr_a_3               |
| kudu_b_user_event_attr_a_4               |
| kudu_b_user_event_attr_a_5               |
| kudu_b_user_event_attr_a_6               |
| kudu_b_user_event_attr_a_7               |
| kudu_b_user_event_attr_a_9               |
| kudu_b_user_event_attr_b_10              |
| kudu_b_user_event_attr_b_11              |
| kudu_b_user_event_attr_b_12              |
| kudu_b_user_event_attr_b_13              |
| kudu_b_user_event_attr_b_14              |
| kudu_b_user_event_attr_b_15              |
| kudu_b_user_event_attr_b_16              |
| kudu_b_user_event_attr_b_17              |
| kudu_b_user_event_attr_b_18              |
| kudu_b_user_event_attr_b_19              |
| kudu_b_user_event_attr_b_2               |
| kudu_b_user_event_attr_b_20              |
| kudu_b_user_event_attr_b_21              |
| kudu_b_user_event_attr_b_22              |
| kudu_b_user_event_attr_b_23              |
| kudu_b_user_event_attr_b_25              |
| kudu_b_user_event_attr_b_3               |
| kudu_b_user_event_attr_b_4               |
| kudu_b_user_event_attr_b_5               |
| kudu_b_user_event_attr_b_6               |
| kudu_b_user_event_attr_b_7               |
| kudu_b_user_event_attr_b_9               |
| kudu_sem_kpi                             |
| kudu_sem_meta                            |
| kudu_sem_query_word_kpi                  |
| mccmnc                                   |
| model                                    |
| network                                  |
| order_data_1_1_1                         |
| order_data_1_1_3                         |
| platform                                 |
| retention_data_1_1_1                     |
| retention_data_1_1_3                     |
| retention_data_step_1_1_1                |
| retention_data_step_1_1_3                |
| t_user_active_1                          |
| t_user_active_10                         |
| t_user_active_11                         |
| t_user_active_12                         |
| t_user_active_13                         |
| t_user_active_14                         |
| t_user_active_15                         |
| t_user_active_16                         |
| t_user_active_17                         |
| t_user_active_18                         |
| t_user_active_19                         |
| t_user_active_2                          |
| t_user_active_20                         |
| t_user_active_21                         |
| t_user_active_22                         |
| t_user_active_23                         |
| t_user_active_25                         |
| t_user_active_3                          |
| t_user_active_4                          |
| t_user_active_5                          |
| t_user_active_6                          |
| t_user_active_7                          |
| t_user_active_9                          |
| t_user_detail_1                          |
| t_user_detail_10                         |
| t_user_detail_11                         |
| t_user_detail_12                         |
| t_user_detail_13                         |
| t_user_detail_14                         |
| t_user_detail_15                         |
| t_user_detail_16                         |
| t_user_detail_17                         |
| t_user_detail_18                         |
| t_user_detail_19                         |
| t_user_detail_2                          |
| t_user_detail_20                         |
| t_user_detail_21                         |
| t_user_detail_22                         |
| t_user_detail_23                         |
| t_user_detail_25                         |
| t_user_detail_3                          |
| t_user_detail_4                          |
| t_user_detail_5                          |
| t_user_detail_6                          |
| t_user_detail_7                          |
| t_user_detail_9                          |
| t_user_detail_sum_1                      |
| t_user_detail_sum_10                     |
| t_user_detail_sum_11                     |
| t_user_detail_sum_12                     |
| t_user_detail_sum_13                     |
| t_user_detail_sum_14                     |
| t_user_detail_sum_15                     |
| t_user_detail_sum_16                     |
| t_user_detail_sum_17                     |
| t_user_detail_sum_18                     |
| t_user_detail_sum_19                     |
| t_user_detail_sum_2                      |
| t_user_detail_sum_20                     |
| t_user_detail_sum_21                     |
| t_user_detail_sum_22                     |
| t_user_detail_sum_23                     |
| t_user_detail_sum_25                     |
| t_user_detail_sum_3                      |
| t_user_detail_sum_4                      |
| t_user_detail_sum_5                      |
| t_user_detail_sum_6                      |
| t_user_detail_sum_7                      |
| t_user_detail_sum_9                      |
| t_user_duration_1                        |
| t_user_duration_10                       |
| t_user_duration_11                       |
| t_user_duration_12                       |
| t_user_duration_13                       |
| t_user_duration_14                       |
| t_user_duration_15                       |
| t_user_duration_16                       |
| t_user_duration_17                       |
| t_user_duration_18                       |
| t_user_duration_19                       |
| t_user_duration_2                        |
| t_user_duration_20                       |
| t_user_duration_21                       |
| t_user_duration_22                       |
| t_user_duration_23                       |
| t_user_duration_25                       |
| t_user_duration_3                        |
| t_user_duration_4                        |
| t_user_duration_5                        |
| t_user_duration_6                        |
| t_user_duration_7                        |
| t_user_duration_9                        |
| t_user_join_1                            |
| t_user_join_10                           |
| t_user_join_11                           |
| t_user_join_12                           |
| t_user_join_13                           |
| t_user_join_14                           |
| t_user_join_15                           |
| t_user_join_16                           |
| t_user_join_17                           |
| t_user_join_18                           |
| t_user_join_19                           |
| t_user_join_2                            |
| t_user_join_20                           |
| t_user_join_21                           |
| t_user_join_22                           |
| t_user_join_23                           |
| t_user_join_25                           |
| t_user_join_3                            |
| t_user_join_4                            |
| t_user_join_5                            |
| t_user_join_6                            |
| t_user_join_7                            |
| t_user_join_9                            |
| v2_filter_data_5_20200605_18989          |
| v2_filter_data_5_20200605_18990          |
| v2_filter_data_5_20200605_18991          |
| v2_filter_data_5_20200605_18992          |
| v2_filter_data_5_20200605_18994          |
| v2_filter_data_5_20200605_18995          |
| v2_filter_data_5_20200605_18996          |
| v2_filter_data_5_20200605_18997          |
| v2_funnel_data_6_20200605_18999          |
| v2_funnel_data_step_6_20200605_18999     |
| v2_group_data_5_20200605_18988           |
| v2_group_data_5_20200605_18993           |
| v2_group_data_6_20200605_18998           |
| v2_group_data_6_20200605_19000           |
| v2_retention_data_20_20200605_19001      |
| v2_retention_data_step_20_20200605_19001
```

