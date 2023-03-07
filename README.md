# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=kqzl) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 空气质量查询
支持国内3400+个城市的整点观测，并附带空气质量监测点（全国共2335个）的整点观测数据。获取指定城市的整点观测空气质量，包含空气质量指数（AQI）、首要污染物、空气质量等级（优、良、轻度污染、中度污染、重度污染、严重污染）、6要素（CO、NO₂、O₃、PM10、PM2.5、SO₂）浓度（除了CO浓度单位为mg/m³之外，其余5种单位均为μg/m³）等。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/34324/introduction](https://www.apispace.com/eolink/api/34324/introduction?utm_source=github&utm_term=kqzl) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/34324/guidence/](https://www.apispace.com/eolink/api/34324/guidence/?utm_source=github&utm_term=kqzl)

**该产品拥有以下APIs：**
1. 空气质量实况
2. 空气质量实时排行
3. 空气质量昨日排行
4. 过去24小时空气质量
5. 逐小时空气质量预报
6. 逐日空气质量预报
7. 国内城市列表

### API列表
#### 1.空气质量实况 API
-   可获取指定城市的整点观测空气质量，包含空气质量指数（AQI）、首要污染物、空气质量等级（优、良、轻度污染、中度污染、重度污染、严重污染）、6要素（CO、NO₂、O₃、PM10、PM2.5、SO₂）浓度（除了CO浓度单位为mg/m³之外，其余5种单位均为μg/m³）等。空气质量为优时，无首要污染物。
-   支持国内3400+个城市的整点观测，并附带空气质量监测点（全国共2335个）的整点观测数据。整点观测数据滞后40分钟左右，如18：40可以得到18点的数据。

#### 2.空气质量实时排行 API
-   根据406个重点城市最近一个整点的空气质量观测数据，对全国城市空气质量进行排名，最好城市排名在前，最差城市排名在后。
-   可以单独查询某个城市的空气质量在全国的排名情况，及击败了多少（百分比）的城市。
-   支持国内406个重点城市的数据调取。
  
#### 3.空气质量昨日排行 API
-   根据406个重点城市昨日AQI均值，对全国城市空气质量进行排名，最好城市排名在前，最差城市排名在后。
-   可以单独查询某个城市的空气质量在全国的排名情况，及击败了多少（百分比）的城市。
-   支持国内406个重点城市的数据调取。

#### 4.过去24小时空气质量 API
-   查询国内3400+个城市过去24小时的逐小时空气质量指数（AQI）、首要污染物、空气质量等级（优、良、轻度污染、中度污染、重度污染、严重污染）、6要素（CO、NO₂、O₃、PM10、PM2.5、SO₂）浓度（除了CO浓度单位为mg/m³之外，其余5种单位均为μg/m³）等。
-   支持国内3400+个城市的过去24小时空气质量数据。

#### 5.逐小时空气质量预报 API
-   获取指定城市的未来3天逐小时空气质量预报，含空气质量指数（AQI）、空气质量状况（优、良、轻度污染、中度污染、重度污染、严重污染）、6要素（CO、NO₂、O₃、PM10、PM2.5、SO₂）浓度（除了CO浓度单位为mg/m³之外，其余5种单位均为μg/m³）等。
-   支持未来3天空气质量的精细化预报。
-   支持国内3400+个城市的数据调取。

#### 6.逐日空气质量预报 API
-   提供全国3400+个城市的未来7天空气质量预报，含空气质量指数（AQI）、空气质量状况（优、良、轻度污染、中度污染、重度污染、严重污染）、6要素（CO、NO₂、O₃、PM10、PM2.5、SO₂）浓度（除了CO浓度单位为mg/m³之外，其余5种单位均为μg/m³）等。
-   支持国内3400+个城市的数据调取。

#### 7.国内/国外城市查询 API
-   可根据城市中文名、英文名或拼音，检索匹配全球的城市信息。
-   支持模糊搜索，可指定搜索范围（中国或全球），设置返回结果数量等。
-   支持中国31个省、直辖市、自治区及港澳台地区共3400+个城市的地理信息；支持全球200多个国家和地区共39474个城市的地理信息。

### 相关附件
-   [查看国内城市_3405站](https://easy-open-link.feishu.cn/wiki/wikcnXfeZ1lmUCbCSac2hYAEFb2)


### 返回示例

以 空气质量实况API 为例

```
{
    “status”: 0,
    “result”: {
        “location”: {
            “areacode”: “101010100”,    //城市ID
            “name”: “北京”,        //城市中文名
            “country”: “中国”,        //所属国家中文名
            “path”: “北京,北京市,北京市,中国”    //行政区划路径
        },
        “realtimeAqi”: {
            “aqi”: 124,            //空气质量指数
            “aqi_level”: “轻度污染”,    //空气质量等级
            “pm10”: 59,        //PM10浓度，单位: 微克/立方米
            “pm25”: 94,        //PM2.5浓度，单位: 微克/立方米
            “no2”: 18,            //二氧化氮浓度，单位: 微克/立方米
            “so2”: 3,            //二氧化硫浓度，单位: 微克/立方米
            “co”: 1.0,            //一氧化碳浓度，单位: 毫克/立方米
            “o3”: 36,            //臭氧浓度，单位: 微克/立方米
            “pollutant”: “一氧化碳”,    //首要污染物，有时为空
            “data_time”: “2020-02-14 09:00:00”,    //实况数据时间
            “stations”: [
                {
                    “stationID”: “1011A”,    //站点编号
                    “lon”: 116.73,        //站点经度
                    “lat”: 39.68,        //站点纬度
                    “name”: “永定门”,        //站点名称
                    “aqi”: 68,            //实时空气质量指数
                    “aqi_level”: “良”,        //空气质量等级
                    “pm10”: 0,            //PM10浓度，单位: 微克/立方米
                    “pm25”: 49,        //PM2.5浓度，单位: 微克/立方米
                    “no2”: 27,            //二氧化氮浓度，单位: 微克/立方米
                    “so2”: 2,            //二氧化硫浓度，单位: 微克/立方米
                    “co”: 1.0,            //一氧化碳浓度，单位: 毫克/立方米
                    “o3”: 30,            //臭氧浓度，单位: 微克/立方米
                    “pollutant”: “细颗粒物(PM2.5)”,    //首要污染物，有时为空
                },
                ……                //其它站点实况信息
            ]
        }
        “last_update”: “2020-02-14 09:44:00”,    //数据更新时间
    }
}
```

### 产品优势
![image](https://user-images.githubusercontent.com/36323798/223364839-44ffc9d8-7d45-40bd-93b2-d0075c4f5264.png)

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223365050-2a81fcd2-69af-46b9-bb61-1fdc97faf768.png)

### Python(Requests) 调用代码示例
以 空气质量实况API 为例
```
import requests

url = "https://eolink.o.apispace.com/34324/air/v001/aqi"

payload = {"areacode" : "101010100"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey"
}

response=requests.request("GET", url, params=payload, headers=headers)

print(response.text)

```
