## 诸葛io平台信息

[TOC]

### 一、研究目标：

​	hive,kafka,kudu 需要研究，研究 数据字典，元数据，数据模型



### 二、数据获取：

#### 1、impala：

126的服务器上：
impala-shell -i 172.18.1.7
use zhugeio



目前的 CDH 集群上安装了 impala-shell  ，也可以在 CDH集群上的任意机器 执行impala-shell -i 172.18.1.7  登录 诸葛 io的 impala 



#### 2、诸葛io 的服务器 ip ： 

172.18.1.4/7/9

#### 3、kafka

服务器ip：172.18.1.7
kafka目录：/data/localization/kafka
过滤某个应用的实时数据：./bin/kafka-console-consumer.sh --zookeeper localhost:2182 --topic pay_statisv2 |grep 具体的appkey

教师 appkey     af6072edac8f4e51a25176f09c3c95c5



### 三、数据结构

#### 1、kafka

##### 1.1、动端数据格式

```json
{
  "owner": "zg",
  "st": 1493895485371,         //会话开始时间（unixtime，毫秒）
  "debug": 0,                  //是否开启了实时调试，0为关闭，1为开启
  "data": [                    //数据部分
    {
      "dt": "evt",             //数据类型，evt代表事件，ss代表会话开始，se代表会话结束，usr代表用户信息,pl代表设备信息
      "pr": {                  //"$"开头代表诸葛默认采集的属性，"_"开头代表是用户上传的自定义属性            
        "$os": "iOS",          //系统
        "$tz": 28800000,       //时区
        "$net": "4",           //网络类型（见下面参考值）
        "$ov": "10.2.1",       //系统版本
        "$eid": "background",  //事件名称
        "$cn": "App Store",    //下载渠道
        "$cr": "46002",        //运营商(见下面参考值)
        "$ct": 1493895485370,  //事件触发时间（unixtime，毫秒）
        "$sid": 1493895485370, //会话开始时间（unixtime，毫秒）
        "$mnet": "None",       //移动网络类型
        "$vn": "2.7.3",        //应用版本
        "_自定义属性名": "自定义属性值"
      }
    }
  ],
  "tz": 28800000,                //时区
  "ip": "113.222.112.181",       //ip地址，诸葛根据ip解析省份城市等信息
  "sdkv": "2.0.0",               //诸葛sdk版本
  "ak": "1234567890987654321",   //应用appkey
  "ua": "CFNetwork/808.3 Darwin/16.3.0",  //user-agent
  "sln": "itn",                  //行业方案，itn互联网
  "usr": {
    "did": "D9A586EF-7999-4ED5-808E-321111ddeds"  //设备id
  },
  "sdk": "zg-ios",              //诸葛sdk类型
  "pl": "ios",                   // 平台信息: js、android为and、iOS为ios
  "ut": "2017-05-04 18:58:05"   //上传时间
}
```

##### 1.2、参考值列表

###### 1.2.1、运营商

```
46000	中国移动
46001	中国联通
46002	中国移动
46003	中国电信
46005	中国电信
46006	中国联通
46007	中国移动
46011	中国电信
46020	中国铁通
```

###### 1.2.2、网络类型

```
0	移动网络
4	WIFI
```

##### 1.3、web端数据格式

```json
{
  "owner": "zg",
  "st": 1493895485371,         //会话开始时间（unixtime，毫秒）
  "debug": 0,                  //是否开启了实时调试，0为关闭，1为开启
  "data": [                    //数据部分
    {
      "dt": "evt",             //数据类型，evt代表事件，ss代表会话开始，se代表会话结束，usr代表用户信息,pl代表设备信息
      "pr": {                  //"$"开头代表诸葛默认采集的属性，"_"开头代表是用户上传的自定义属性            
        "$tz": 28800000,                      //时区
        "$eid": "background",                 //事件名称
        "$ct": 1493895485370,                 //事件触发时间（unixtime，毫秒）
        "$sid": 1493895485370,                //会话开始时间（unixtime，毫秒）
        "$browser_brand": "Chrome",           // 浏览器品牌
        "$browser_version": 54,               // 浏览器版本
        "$url": "https://zhugeio.com",        // 当前url
        "$ref": "https://zhugeio.com",        // 来源网址 
        "$utm_source": "",                    //utm参数                    
        "$utm_medium": "",                    
        "$utm_campaign": "",                  
        "$utm_content": "",                   
        "$utm_term": "",                      
        "$referrerDomain":""
        "_自定义属性名": "自定义属性值"
      }
    }
  ],
  "tz": 28800000,                    //时区
  "ip": "113.222.112.181",           //ip地址，诸葛根据ip解析省份城市等信息
  "sdkv": "2.0",                     //诸葛sdk版本
  "ak": "1234567890987654321",       //应用appkey
  "ua": "CFNetwork/808.3 Darwin/16.3.0",  //user-agent
  "sln": "itn",                      //行业方案，itn互联网
  "usr": {
    "did": "D9A586EF-7999-4ED5-808E-321111ddeds"  //设备id
  },
  "sdk": "zg-js",                    //诸葛sdk类型
   "pl": "js",                       // 平台信息: js、android为and、iOS为ios
  "ut": "2017-05-04 18:58:05"        //上传时间
}
```

##### 1.4、kafka topics:

###### 1.4.1、debug

```json
{
    "sln": "itn",
    "pl": "js",
    "sdk": "zg-js",
    "sdkv": "2.0",
    "owner": "zg",
    "ut": "2020-6-4 17:24:17",
    "tz": 28800000,
    "debug": 1,
    "ak": "af6072edac8f4e51a25176f09c3c95c5",
    "usr": {
        "did": "16dbf0674e676e-0913c099d3ec8a-5d5e490e-15f900-16dbf0674e78be"
    },
    "data": [
        {
            "dt": "abp",
            "pr": {
                "$ct": 1591262657118,
                "$tz": 28800000,
                "$cuid": "3976787",
                "$sid": 1591262285257,
                "$url": "https://www.ekwing.com/exam/review/addtest",
                "$ref": "https://www.ekwing.com/home/index?islogin",
                "$referrer_domain": "www.ekwing.com",
                "$eid": "click",
                "$page_url": "https://www.ekwing.com/exam/review/addtest",
                "$page_title": "智能题库_布置_教师",
                "$element_id": "h5Player15912624298876960",
                "$element_content": "00:00/01:19",
                "$element_type": "div",
                "$element_style": "audio",
                "$element_selector": "69e463e8aa9ee5e474cd2db1e9e5288e",
                "$element_link": null,
                "_应用名称": "教师端"
            }
        }
    ],
    "ip": "120.208.21.34",
    "st": 1591262387320,
    "ua": "Mozilla/5.0 (Windows NT 6.1; WOW64; Trident/7.0; rv:11.0) like Gecko"
}
```

###### 1.4.2、es_index

​	数据为空

###### 1.4.3、pay_statisv2

```json
{
    "ak": "373b07f02b874fcda2f678ece32d3cea",
    "data": [
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_main",
                "$cr": "46003",
                "$ct": 1591261803511,
                "$cuid": "8560222",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261731617,
                "$eid": "statistic_speech_score",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 21,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "8",
                "_score": "84",
                "_engine": "kSingSound",
                "_interval": "8"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_main",
                "$cr": "46003",
                "$ct": 1591261803543,
                "$cuid": "8560222",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261731617,
                "$eid": "statistic_score_singsound",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 22,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "8",
                "_score": "84",
                "_engine": "kSingSound",
                "_interval": "8"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_main",
                "$cr": "46003",
                "$ct": 1591261803572,
                "$cuid": "8560222",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261731617,
                "$eid": "stable_speech_singsound",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 23,
                "$ps": "com.ekwing.students",
                "_speechStatus": "success_online_sentence",
                "_duration": "0-500ms",
                "_score": "84",
                "_totalNums": "评分总次数",
                "_hwType": "success_101",
                "_speechType": "success_sentence",
                "_focusStatus": "success_",
                "_status": "success_"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_main",
                "$cr": "46003",
                "$ct": 1591261808060,
                "$cuid": "8560222",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261731617,
                "$eid": "statistic_speech_score",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 24,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "8",
                "_score": "84",
                "_engine": "kSingSound",
                "_interval": "8"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_main",
                "$cr": "46003",
                "$ct": 1591261808106,
                "$cuid": "8560222",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261731617,
                "$eid": "statistic_score_singsound",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 25,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "8",
                "_score": "84",
                "_engine": "kSingSound",
                "_interval": "8"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_main",
                "$cr": "46003",
                "$ct": 1591261808134,
                "$cuid": "8560222",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261731617,
                "$eid": "stable_speech_singsound",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 26,
                "$ps": "com.ekwing.students",
                "_speechStatus": "success_online_sentence",
                "_duration": "0-500ms",
                "_score": "84",
                "_totalNums": "评分总次数",
                "_hwType": "success_101",
                "_speechType": "success_sentence",
                "_focusStatus": "success_",
                "_status": "success_"
            }
        }
    ],
    "debug": 0,
    "sln": "itn",
    "sdk": "zg_android",
    "owner": "zg",
    "pl": "and",
    "sdkv": "3.3.3",
    "tz": 28800000,
    "usr": {
        "did": "ffffffff-a95b-d1a6-ffff-ffffe154c516"
    },
    "ut": "2020-06-04 17:10:08",
    "ip": "183.156.189.246",
    "st": 1591261809382,
    "ua": "Dalvik/2.1.0 (Linux; U; Android 9; ANE-AL00 Build/HUAWEIANE-AL00)"
}
```

###### 1.4.4、pay_zg_total

```json
{
    "ak": "373b07f02b874fcda2f678ece32d3cea",
    "data": [
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_huawei",
                "$cr": "46002",
                "$ct": 1591262026559,
                "$cuid": "4556118",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261796200,
                "$eid": "statistic_speech_score",
                "$net": "4",
                "$mnet": "2",
                "$ov": "8.0.0",
                "$sc": 114,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "9",
                "_score": "90",
                "_engine": "kSingSound",
                "_interval": "9",
                "$zg_did": 1301395,
                "$zg_sid": 1591261796200,
                "$uuid": "23b7f27fac8342f2898d9d1536e4745c",
                "$zg_uid": 228583,
                "$zg_zgid": 272868,
                "$zg_eid": 1955,
                "$zg_epid#_interval_sentence": 3299,
                "$zg_eptp#_interval_sentence": "string",
                "$zg_epid#_interval": 3291,
                "$zg_eptp#_interval": "string",
                "$zg_epid#_engine": 3295,
                "$zg_eptp#_engine": "string",
                "$zg_epid#_score": 3292,
                "$zg_eptp#_score": "string"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_huawei",
                "$cr": "46002",
                "$ct": 1591262026576,
                "$cuid": "4556118",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261796200,
                "$eid": "statistic_score_singsound",
                "$net": "4",
                "$mnet": "2",
                "$ov": "8.0.0",
                "$sc": 115,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "9",
                "_score": "90",
                "_engine": "kSingSound",
                "_interval": "9",
                "$zg_did": 1301395,
                "$zg_sid": 1591261796200,
                "$uuid": "136eef57a2694b23bbfd2872aae2330c",
                "$zg_uid": 228583,
                "$zg_zgid": 272868,
                "$zg_eid": 1954,
                "$zg_epid#_interval_sentence": 3298,
                "$zg_eptp#_interval_sentence": "string",
                "$zg_epid#_interval": 3280,
                "$zg_eptp#_interval": "string",
                "$zg_epid#_engine": 3281,
                "$zg_eptp#_engine": "string",
                "$zg_epid#_score": 3290,
                "$zg_eptp#_score": "string"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_huawei",
                "$cr": "46002",
                "$ct": 1591262026595,
                "$cuid": "4556118",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261796200,
                "$eid": "stable_speech_singsound",
                "$net": "4",
                "$mnet": "2",
                "$ov": "8.0.0",
                "$sc": 116,
                "$ps": "com.ekwing.students",
                "_speechStatus": "success_online_sentence",
                "_duration": "0-500ms",
                "_score": "90",
                "_totalNums": "评分总次数",
                "_hwType": "success_102",
                "_speechType": "success_sentence",
                "_focusStatus": "success_",
                "_status": "success_",
                "$zg_did": 1301395,
                "$zg_sid": 1591261796200,
                "$uuid": "f8149a508a4649169fb5eb3ee0ac2eac",
                "$zg_uid": 228583,
                "$zg_zgid": 272868,
                "$zg_eid": 1953,
                "$zg_epid#_totalNums": 3293,
                "$zg_eptp#_totalNums": "string",
                "$zg_epid#_hwType": 3287,
                "$zg_eptp#_hwType": "string",
                "$zg_epid#_focusStatus": 3289,
                "$zg_eptp#_focusStatus": "string",
                "$zg_epid#_speechStatus": 3294,
                "$zg_eptp#_speechStatus": "string",
                "$zg_epid#_status": 3283,
                "$zg_eptp#_status": "string",
                "$zg_epid#_duration": 3286,
                "$zg_eptp#_duration": "string",
                "$zg_epid#_speechType": 3282,
                "$zg_eptp#_speechType": "string",
                "$zg_epid#_score": 3285,
                "$zg_eptp#_score": "string"
            }
        },
        {
            "dt": "zgid",
            "pr": {
                "$ct": 1591262026559,
                "$zg_uid": 228583,
                "$zg_did": 1301395,
                "$tz": 28800000,
                "$zg_zgid": 272868
            }
        },
        {
            "dt": "pl",
            "pr": {
                "$dv": "zhuge.io",
                "$zg_did": 1301395
            }
        },
        {
            "dt": "usr",
            "pr": {
                "$ct": 1591262026559,
                "$zg_uid": 228583,
                "$zg_did": 1301395,
                "$tz": 28800000,
                "$cuid": "4556118",
                "$zg_zgid": 272868
            }
        }
    ],
    "debug": 0,
    "sln": "itn",
    "sdk": "zg_android",
    "owner": "zg",
    "pl": "and",
    "sdkv": "3.3.3",
    "tz": 28800000,
    "usr": {
        "did": "00000000-7a49-89aa-0000-00001f45c342",
        "$zg_did": 1301395
    },
    "ut": "2020-06-04 17:13:51",
    "ip": "222.129.58.103",
    "st": 1591262031927,
    "ua": "Dalvik/2.1.0 (Linux; U; Android 8.0.0; HUAWEI NXT-AL10 Build/HUAWEINXT-AL10)",
    "plat": 1,
    "app_id": 6
}
```

###### 1.4.5、pay_zg_total_random

```json
{
    "ak": "373b07f02b874fcda2f678ece32d3cea",
    "data": [
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_tencent",
                "$cr": "46011",
                "$ct": 1591262142067,
                "$cuid": "8909410",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261696481,
                "$eid": "statistic_speech_score",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 46,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "8",
                "_score": "85",
                "_engine": "kSingSound",
                "_interval": "8",
                "$zg_did": 6736006,
                "$zg_sid": 1591261696481,
                "$uuid": "2b50c0d7df944b608ee8ceae61762fec",
                "$zg_uid": 3017012,
                "$zg_zgid": 5306275,
                "$zg_eid": 1955,
                "$zg_epid#_interval_sentence": 3299,
                "$zg_eptp#_interval_sentence": "string",
                "$zg_epid#_interval": 3291,
                "$zg_eptp#_interval": "string",
                "$zg_epid#_engine": 3295,
                "$zg_eptp#_engine": "string",
                "$zg_epid#_score": 3292,
                "$zg_eptp#_score": "string"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_tencent",
                "$cr": "46011",
                "$ct": 1591262142099,
                "$cuid": "8909410",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261696481,
                "$eid": "statistic_score_singsound",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 47,
                "$ps": "com.ekwing.students",
                "_interval_sentence": "8",
                "_score": "85",
                "_engine": "kSingSound",
                "_interval": "8",
                "$zg_did": 6736006,
                "$zg_sid": 1591261696481,
                "$uuid": "9212fb7606f74a17b9beb947a3c5e0d1",
                "$zg_uid": 3017012,
                "$zg_zgid": 5306275,
                "$zg_eid": 1954,
                "$zg_epid#_interval_sentence": 3298,
                "$zg_eptp#_interval_sentence": "string",
                "$zg_epid#_interval": 3280,
                "$zg_eptp#_interval": "string",
                "$zg_epid#_engine": 3281,
                "$zg_eptp#_engine": "string",
                "$zg_epid#_score": 3290,
                "$zg_eptp#_score": "string"
            }
        },
        {
            "dt": "evt",
            "pr": {
                "$an": "翼课学生",
                "$cn": "ekwing_tencent",
                "$cr": "46011",
                "$ct": 1591262142117,
                "$cuid": "8909410",
                "$os": "Android",
                "$tz": 28800000,
                "$vn": "3.8.6",
                "$sid": 1591261696481,
                "$eid": "stable_speech_singsound",
                "$net": "4",
                "$mnet": "13",
                "$ov": "9",
                "$sc": 48,
                "$ps": "com.ekwing.students",
                "_speechStatus": "success_online_sentence",
                "_duration": "0-500ms",
                "_score": "85",
                "_totalNums": "评分总次数",
                "_hwType": "success_101",
                "_speechType": "success_sentence",
                "_focusStatus": "success_",
                "_status": "success_",
                "$zg_did": 6736006,
                "$zg_sid": 1591261696481,
                "$uuid": "912ad9c85c154df3aaf96d6c2394d373",
                "$zg_uid": 3017012,
                "$zg_zgid": 5306275,
                "$zg_eid": 1953,
                "$zg_epid#_totalNums": 3293,
                "$zg_eptp#_totalNums": "string",
                "$zg_epid#_hwType": 3287,
                "$zg_eptp#_hwType": "string",
                "$zg_epid#_focusStatus": 3289,
                "$zg_eptp#_focusStatus": "string",
                "$zg_epid#_speechStatus": 3294,
                "$zg_eptp#_speechStatus": "string",
                "$zg_epid#_status": 3283,
                "$zg_eptp#_status": "string",
                "$zg_epid#_duration": 3286,
                "$zg_eptp#_duration": "string",
                "$zg_epid#_speechType": 3282,
                "$zg_eptp#_speechType": "string",
                "$zg_epid#_score": 3285,
                "$zg_eptp#_score": "string"
            }
        },
        {
            "dt": "zgid",
            "pr": {
                "$ct": 1591262142067,
                "$zg_uid": 3017012,
                "$zg_did": 6736006,
                "$tz": 28800000,
                "$zg_zgid": 5306275
            }
        },
        {
            "dt": "pl",
            "pr": {
                "$dv": "zhuge.io",
                "$zg_did": 6736006
            }
        },
        {
            "dt": "usr",
            "pr": {
                "$ct": 1591262142067,
                "$zg_uid": 3017012,
                "$zg_did": 6736006,
                "$tz": 28800000,
                "$cuid": "8909410",
                "$zg_zgid": 5306275
            }
        }
    ],
    "debug": 0,
    "sln": "itn",
    "sdk": "zg_android",
    "owner": "zg",
    "pl": "and",
    "sdkv": "3.3.3",
    "tz": 28800000,
    "usr": {
        "did": "ffffffff-9e5b-fe30-0000-0000621c5aa2",
        "$zg_did": 6736006
    },
    "ut": "2020-06-04 17:15:47",
    "ip": "171.41.11.120",
    "st": 1591262146312,
    "ua": "Dalvik/2.1.0 (Linux; U; Android 9; PCHM10 Build/PKQ1.190714.001)",
    "plat": 1,
    "app_id": 6
}
```



###### 1.4.6、sdklua_online

```json
{
    "Ip": "61.142.103.107",
    "Now": 1591262246316,
    "Header": "{\"accept-language\":\"zh-CN,zh;q=0.9\",\"accept\":\"image\\\/webp,image\\\/apng,image\\\/*,*\\\/*;q=0.8\",\"referer\":\"https:\\\/\\\/www.ekwing.com\\\/exam\\\/teacher\\\/index\\\/selfdetail?self_id=2428369\",\"host\":\"zgd.ekwing.com\",\"x-forwarded-for\":\"61.142.103.107\",\"x-forwarded-proto\":\"https\",\"sec-fetch-mode\":\"no-cors\",\"cookie\":\"zg_did=%7B%22did%22%3A%20%2217225c9f712331-0ba37c06e4cf2-5c63397d-15f900-17225c9f7152a7%22%7D; zg_373b07f02b874fcda2f678ece32d3cea=%7B%22sid%22%3A%201589771892513%2C%22updated%22%3A%201589771957085%2C%22info%22%3A%201589771892527%2C%22superProperty%22%3A%20%22%7B%5C%22%E5%BA%94%E7%94%A8%E5%90%8D%E7%A7%B0%5C%22%3A%20%5C%22%E5%AD%A6%E7%94%9F%E7%AB%AF%5C%22%7D%22%2C%22platform%22%3A%20%22%7B%7D%22%2C%22utm%22%3A%20%22%7B%7D%22%2C%22referrerDomain%22%3A%20%22www.ekwing.com%22%7D; IS_SCHOOL_LOGIN=1; from_type=2; client_type=0; Hm_lvt_b4c8ad78a28febf2e2e8a8d38c14165f=1590375502,1590746808,1590966822,1591262193; EKWUID=vOTk2ODAjIzE2NjA2NTg0IyM5MmQ5YzljMzI4ZmVlNThlNjUyOTNlMDFhNmJkNjQzZCMjNmU3NWFhY2JjNzVjZmY3MmUyMzUwZDE1MDdmMzcwYzEjIzE1OTEzNDg2MjAjIzEjIzEjI2Vrd190ZWFjaGVyv; uid=baBd9G4waF%2B9LNT1KbZzPUFRhFQrGI3HGqZwTQj8x1U%3D; Hm_lpvt_b4c8ad78a28febf2e2e8a8d38c14165f=1591262243; zg_af6072edac8f4e51a25176f09c3c95c5=%7B%22sid%22%3A%201591262226404%2C%22updated%22%3A%201591262246597%2C%22info%22%3A%201591262226450%2C%22superProperty%22%3A%20%22%7B%5C%22%E5%BA%94%E7%94%A8%E5%90%8D%E7%A7%B0%5C%22%3A%20%5C%22%E6%95%99%E5%B8%88%E7%AB%AF%5C%22%7D%22%2C%22platform%22%3A%20%22%7B%7D%22%2C%22utm%22%3A%20%22%7B%7D%22%2C%22referrerDomain%22%3A%20%22www.ekwing.com%22%2C%22cuid%22%3A%20%2299680%22%7D\",\"accept-encoding\":\"gzip, deflate, br\",\"sec-fetch-site\":\"same-site\",\"user-agent\":\"Mozilla\\\/5.0 (Windows NT 6.1) AppleWebKit\\\/537.36 (KHTML, like Gecko) Chrome\\\/78.0.3904.108 Safari\\\/537.36\"}",
    "Method": "GET",
    "Args": "{\"method\":\"web_event_srv.upload\",\"_\":\"1591262246598\",\"event\":\"{\\\"sln\\\": \\\"itn\\\",\\\"pl\\\": \\\"js\\\",\\\"sdk\\\": \\\"zg-js\\\",\\\"sdkv\\\": \\\"2.0\\\",\\\"owner\\\": \\\"zg\\\",\\\"ut\\\": \\\"2020-6-4 17:17:26\\\",\\\"tz\\\": 28800000,\\\"debug\\\": 1,\\\"ak\\\": \\\"af6072edac8f4e51a25176f09c3c95c5\\\",\\\"usr\\\": {\\\"did\\\": \\\"17225c9f712331-0ba37c06e4cf2-5c63397d-15f900-17225c9f7152a7\\\"},\\\"data\\\": [\\n    {\\\"dt\\\": \\\"evt\\\",\\\"pr\\\": {\\\"$ct\\\": 1591262246598,\\\"$tz\\\": 28800000,\\\"$cuid\\\": \\\"99680\\\",\\\"$sid\\\": 1591262226404,\\\"$url\\\": \\\"https:\\\/\\\/www.ekwing.com\\\/exam\\\/teacher\\\/index\\\/selfdetail?self_id=2428369\\\",\\\"$ref\\\": \\\"https:\\\/\\\/www.ekwing.com\\\/exam\\\/teacher\\\/selflist\\\",\\\"$referrer_domain\\\": \\\"www.ekwing.com\\\",\\\"$eid\\\": \\\"teacher_schoolReport_pageView\\\",\\\"_taskType\\\": \\\"听说考试\\\",\\\"_classType\\\": \\\"全部班级\\\",\\\"_应用名称\\\": \\\"教师端\\\"}}\\n]}\"}"
}
```



#### 2、hive与kudu

详细描述见文件：[诸葛io平台impala数据信息.md](./诸葛io平台impala数据信息.md)


