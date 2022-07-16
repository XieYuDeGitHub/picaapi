# picaapi
就是那个粉色APP
这个文档是由ApiFox生成的，
也可以通过这个链接查看网页版: https://www.apifox.cn/apidoc/shared-44da213e-98f7-4587-a75e-db998ed067ad

# 哔咔

> v1.0.0

哔咔的API（没错就是那个粉色的APP）

# auth

## POST 忘记密码

POST /auth/forgot-password

> Body 请求参数

```json
{
  "email": "1972664191" 哔咔账号
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» email|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "question1": "1",
    "question2": "2",
    "question3": "3"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» question1|string|true|none||none|
|»» question2|string|true|none||none|
|»» question3|string|true|none||none|

## POST 重置密码

POST /auth/reset-password

> Body 请求参数

```json
{
  "email": "string",
  "questionNo": "string",
  "answer": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» email|body|string| 是 |账号|
|» questionNo|body|string| 是 |问题序号（问题由忘记密码接口返回），可选1 2 3|
|» answer|body|string| 是 |答案|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "password": "tcod20p7"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» password|string|true|none||none|

## POST 登录

POST /auth/sign-in

> Body 请求参数

```json
{
  "email": "o.dfxkwlwc@qq.com",
  "password": "aliquip minim sit"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» email|body|string| 是 |none|
|» password|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJfaWQiOiI1ZTJiZWNlOGQ2MDZlNzJhN2YzODQwMmYiLCJlbWFpbCI6IjE5NzI2NjQxOTEiLCJyb2xlIjoibWVtYmVyIiwibmFtZSI6IuiHquW3seW8gOWPkeavlOWNoSIsInZlcnNpb24iOiIyLjIuMS4zLjMuNCIsImJ1aWxkVmVyc2lvbiI6IjQ1IiwicGxhdGZvcm0iOiJhbmRyb2lkIiwiaWF0IjoxNjU2NTE4ODI3LCJleHAiOjE2NTcxMjM2Mjd9.uQoJ8cF3Mh0F3PrsdyJwRtB1gSGXoWVKxYjBANRL4cM"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» token|string|true|none||none|

## POST 注册

POST /auth/register

> Body 请求参数

```json
{
  "email": "string",
  "password": "string",
  "name": "string",
  "birthday": "string",
  "gender": "string",
  "answer1": "string",
  "answer2": "string",
  "answer3": "string",
  "question1": "string",
  "question2": "string",
  "question3": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» email|body|string| 是 |账号|
|» password|body|string| 是 |密码|
|» name|body|string| 是 |昵称|
|» birthday|body|string| 是 |生日 yyyy-mm-dd|
|» gender|body|string| 是 |性别，|
|» answer1|body|string| 是 |none|
|» answer2|body|string| 是 |none|
|» answer3|body|string| 是 |none|
|» question1|body|string| 是 |none|
|» question2|body|string| 是 |none|
|» question3|body|string| 是 |none|

> 返回示例

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# games

## GET 游戏详细信息

GET /games/{gameId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|gameId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "game": {
      "_id": "62b588f9c741070644484949",
      "title": "我的學妹不可能這麼萌",
      "description": "冷傲千金誤闖異界，街巷遭醉酒痴漢追蹤，走投無路只好投靠變態勇者！？\n「沒保護費？呵，你這騷妞身材倒是不錯……♡」\n齷齪勇者環頸搔撩，舔舐少女臉頰之餘，更扒進裙下猥褻腿根！\n為了生存，大小姐即使渾身起雞皮疙瘩，也只能乖乖翹起密臀，任由勇者暴粗凌辱\n男子彈指挑起絲綢內褲，指插處女濕滑花鏠，捅出絲絲發情淫液！\n「不…不行，那裡不能碰……！」\n一事無成還敢談條件？立即掏出雄壯巨屌，教育大小姐下流禮節，將貴氣淫穴捅成低俗便器！",
      "version": "1.0.0",
      "icon": {
        "originalName": "appicon_256_256.png",
        "path": "tobs/6f69b29d-23ea-4790-8972-55ac1cf35e9a.png",
        "fileServer": "https://storage-b.picacomic.com"
      },
      "publisher": "JG Game",
      "ios": false,
      "iosLinks": [],
      "android": true,
      "androidLinks": [
        "https://playatt13.king1818.net"
      ],
      "adult": true,
      "suggest": false,
      "downloadsCount": 0,
      "screenshots": [
        {
          "originalName": "image1.jpg",
          "path": "tobs/f73c430a-a7ec-4f03-9500-c98a84b5e286.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        {
          "originalName": "image2.jpg",
          "path": "tobs/7db28a12-c975-4c10-b824-3fad8d1e3351.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        {
          "originalName": "image3.jpg",
          "path": "tobs/48caad68-5474-4ff6-bbdc-860b731cc8e9.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        {
          "originalName": "image4.jpg",
          "path": "tobs/cca26abc-8801-49f6-aa53-0700bc4871a3.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        {
          "originalName": "image5.jpg",
          "path": "tobs/6dc8bc93-118b-4529-93ec-c96874ebf63f.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        {
          "originalName": "world_13_800_1200_v8.jpg",
          "path": "tobs/053d42a4-6294-4121-bf3a-f6a549313518.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        }
      ],
      "androidSize": 780,
      "iosSize": 0,
      "videoLink": "https://d2y99usvc0cpr4.cloudfront.net/game/play/assets/page_2/video.mp4",
      "updated_at": "2022-06-25T03:10:04.909Z",
      "created_at": "2022-06-24T09:50:49.891Z",
      "likesCount": 273,
      "isLiked": false,
      "commentsCount": 27
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» game|object|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|
|»»» description|string|true|none||none|
|»»» version|string|true|none||none|
|»»» icon|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»» publisher|string|true|none||none|
|»»» ios|boolean|true|none||none|
|»»» iosLinks|[string]|true|none||none|
|»»» android|boolean|true|none||none|
|»»» androidLinks|[string]|true|none||none|
|»»» adult|boolean|true|none||none|
|»»» suggest|boolean|true|none||none|
|»»» downloadsCount|integer|true|none||none|
|»»» screenshots|[object]|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»» androidSize|integer|true|none||none|
|»»» iosSize|integer|true|none||none|
|»»» videoLink|string|true|none||none|
|»»» updated_at|string|true|none||none|
|»»» created_at|string|true|none||none|
|»»» likesCount|integer|true|none||none|
|»»» isLiked|boolean|true|none||none|
|»»» commentsCount|integer|true|none||none|

## GET 获取评论

GET /games/{gameId}/comments

获取游戏评论

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|gameId|path|string| 是 |none|
|page|query|string| 否 |页码|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comments": {
      "docs": [
        {
          "_id": "62bf196e0173104beb24278e",
          "content": "你妈，我还以为是「我的学妹不可能那么萌」。我还疑惑怎么学妹才凉就有傻卵换皮做黄油了。\n原来是jg阿?那没事了，jg死全家(呕)",
          "_user": {
            "_id": "5e98f8163edf5774d85407e4",
            "gender": "f",
            "name": "李性蒸発",
            "title": "萌新",
            "verified": false,
            "exp": 910,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "tobs/00ea67ad-9117-4f37-9e82-08d66c41ca81.jpg",
              "fileServer": "https://storage-b.picacomic.com"
            },
            "slogan": "为什么为什么为什么为什么细长让人无法拒绝\n\n冲，都可以冲\n\n反正我又不会射米青(落泪)"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-07-01T15:57:34.841Z",
          "id": "62bf196e0173104beb24278e",
          "likesCount": 3,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62be509f496305637db3b2a9",
          "content": "在五六年前我玩过一个同名的游戏，是以三国人物为原形娘化的，太久没玩了。现在看到bika这个还以为是我玩的那个",
          "_user": {
            "_id": "5e986dc832085b5e6ca76aec",
            "gender": "m",
            "name": "ULi尤里",
            "title": "萌新",
            "verified": false,
            "exp": 820,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "b250b0de-9450-45d5-be09-863f61d60a09.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "slogan": "可别让我对你失去兴趣哟"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 1,
          "isTop": false,
          "hide": false,
          "created_at": "2022-07-01T01:40:47.716Z",
          "id": "62be509f496305637db3b2a9",
          "likesCount": 5,
          "commentsCount": 1,
          "isLiked": false
        },
        {
          "_id": "62bdc8d26ca0ea3cb8c70339",
          "content": "一看游戏介绍就知道是什么玩意",
          "_user": {
            "_id": "6204d237248b56763e67696c",
            "gender": "m",
            "name": "监狱舰长",
            "title": "萌新",
            "verified": false,
            "exp": 720,
            "level": 3,
            "characters": [],
            "role": "member"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-30T16:01:22.711Z",
          "id": "62bdc8d26ca0ea3cb8c70339",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62bc5cce45339c9f8d036b52",
          "content": "jg怎么还不似啊",
          "_user": {
            "_id": "60cc6cb82be140c90a2e3b71",
            "gender": "m",
            "name": "Skadi星痕",
            "title": "萌新",
            "verified": false,
            "exp": 750,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "tobs/f60a5d05-87ca-4496-a80d-8f67349b408b.jpg",
              "fileServer": "https://storage-b.picacomic.com"
            }
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-29T14:08:14.912Z",
          "id": "62bc5cce45339c9f8d036b52",
          "likesCount": 6,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62bc22ca354875638d33dc47",
          "content": "jg，狗都不玩",
          "_user": {
            "_id": "597793bda936e10673355aa7",
            "gender": "m",
            "name": "咳乔",
            "title": "萌新",
            "verified": false,
            "exp": 3260,
            "level": 6,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "3b1aea73-d58d-4a47-b2e2-c4cbe33493d4.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "slogan": "null",
            "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-29T10:00:42.707Z",
          "id": "62bc22ca354875638d33dc47",
          "likesCount": 4,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62bb82f9496305637db2c0a6",
          "content": "玩了半天，发现只有文字剧情，一点图片都不给，想看H剧情的cg还要氪不知道多少，玩你妈",
          "_user": {
            "_id": "5edbb46de130903730c10413",
            "gender": "m",
            "name": "平凡人世",
            "title": "萌新",
            "verified": false,
            "exp": 830,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "aa62afbc-05a9-4d67-8140-ac402b853d3c.jpg",
              "fileServer": "https://storage1.picacomic.com"
            }
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-28T22:38:49.606Z",
          "id": "62bb82f9496305637db2c0a6",
          "likesCount": 10,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62ba6cddd158b0e047948177",
          "content": "玩都不想玩。但凡做点h点的，都不会这么多差评",
          "_user": {
            "_id": "5fb714b1fe6fef29468ab776",
            "gender": "m",
            "name": "一位九岁的萝莉",
            "title": "萌新",
            "verified": false,
            "exp": 1560,
            "level": 4,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "80fbb1e1-90d9-4a89-96d4-671d69ec5827.jpg",
              "fileServer": "https://storage1.picacomic.com"
            }
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-28T02:52:13.286Z",
          "id": "62ba6cddd158b0e047948177",
          "likesCount": 3,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62ba5808b62553636b9706c1",
          "content": "我也来，JG滚出黄油界！",
          "_user": {
            "_id": "6002f805ab4cdc32b355468c",
            "gender": "m",
            "name": "7X幻",
            "title": "萌新",
            "verified": false,
            "exp": 2850,
            "level": 5,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "82f6ce59-e350-4ad6-80d2-67c9f0f8cae6.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "slogan": "null"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 1,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-28T01:23:20.940Z",
          "id": "62ba5808b62553636b9706c1",
          "likesCount": 16,
          "commentsCount": 1,
          "isLiked": false
        },
        {
          "_id": "62ba3ad38fac44c237d42a3d",
          "content": "我先去试试毒",
          "_user": {
            "_id": "618660981be35c713a8ca543",
            "gender": "m",
            "name": "不要看头像辣",
            "title": "萌新",
            "verified": false,
            "exp": 700,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "tobs/44e88c07-31f0-4147-a19a-493b6036b194.jpg",
              "fileServer": "https://storage-b.picacomic.com"
            }
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 1,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-27T23:18:43.246Z",
          "id": "62ba3ad38fac44c237d42a3d",
          "likesCount": 1,
          "commentsCount": 1,
          "isLiked": false
        },
        {
          "_id": "62b961c0b00c8386d5a630ad",
          "content": "点进来前:我不信哔咔会有这么多jg游戏\n点击来后:哔咔一定收到了很多金金金金金金，钱钱钱钱钱罢",
          "_user": {
            "_id": "5e116ecb77c3e04c3b8106ba",
            "gender": "m",
            "name": "致命球",
            "title": "致命缺陷",
            "verified": false,
            "exp": 3085,
            "level": 6,
            "characters": [],
            "role": "member",
            "avatar": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "1e34f0db-2c91-44ac-b429-cfd68b564cc8.jpg",
              "originalName": "avatar.jpg"
            },
            "slogan": "停下来啊。"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-27T07:52:32.421Z",
          "id": "62b961c0b00c8386d5a630ad",
          "likesCount": 25,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b89044432fee3a9c4cf8ea",
          "content": "逆王传说的换皮游戏罢了",
          "_user": {
            "_id": "619a4b3f94bec2c81417538c",
            "gender": "bot",
            "name": "banned ee",
            "title": "萌新",
            "verified": false,
            "exp": 650,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "8d3f2a86-eefc-46b0-87ed-d24e67892d26.jpg",
              "fileServer": "https://storage1.picacomic.com"
            }
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-26T16:58:44.851Z",
          "id": "62b89044432fee3a9c4cf8ea",
          "likesCount": 6,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b871c9df978c86c73cfd84",
          "content": "来啦～JG游戏，🐕都不玩～",
          "_user": {
            "_id": "5e7627206119576fe4f4ae7b",
            "gender": "f",
            "name": "浅笑嫣兮-忆薇",
            "title": "萌新",
            "verified": false,
            "exp": 3480,
            "level": 6,
            "characters": [],
            "role": "member",
            "avatar": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "46b06e3a-b76d-4ccf-a347-17bf1fd21160.jpg",
              "originalName": "avatar.jpg"
            },
            "slogan": "既含睇兮又宜笑，子慕予兮善窈窕～\n\n咱家已经把全彩栏目翻完啦！好耶！✌"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-26T14:48:41.685Z",
          "id": "62b871c9df978c86c73cfd84",
          "likesCount": 15,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b805ccdf978c86c73cd5b1",
          "content": "羁绊游戏",
          "_user": {
            "_id": "5ec2470320c5425ce045911c",
            "gender": "m",
            "name": "saisdi",
            "title": "萌新",
            "verified": false,
            "exp": 3790,
            "level": 6,
            "characters": [],
            "role": "member",
            "avatar": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "81dd03b8-e92f-46cf-8b09-41c620deb3b8.jpg",
              "originalName": "avatar.jpg"
            }
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-26T07:07:56.203Z",
          "id": "62b805ccdf978c86c73cd5b1",
          "likesCount": 3,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b7e5e8aef5771823c0784b",
          "content": "早就该有人搞破解了，把CG弄出来",
          "_user": {
            "_id": "5b5b23bc3367a36ae7b54022",
            "gender": "m",
            "name": "1k14",
            "title": "萌新",
            "verified": false,
            "exp": 1800,
            "level": 4,
            "characters": [],
            "role": "member",
            "avatar": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "6bda3c94-6173-4787-b65f-eb4734cde26f.jpg",
              "originalName": "avatar.jpg"
            },
            "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 4,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-26T04:51:52.441Z",
          "id": "62b7e5e8aef5771823c0784b",
          "likesCount": 19,
          "commentsCount": 4,
          "isLiked": false
        },
        {
          "_id": "62b71deaf4157ec2119cc5ba",
          "content": "j 狗",
          "_user": {
            "_id": "5fdf6c8c4f8c316fd9929459",
            "gender": "m",
            "name": "花湖雅居",
            "title": "萌新",
            "verified": false,
            "exp": 700,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "0f0ecd23-36d4-493f-a605-46c3816a4147.jpg",
              "originalName": "avatar.jpg"
            }
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-25T14:38:34.873Z",
          "id": "62b71deaf4157ec2119cc5ba",
          "likesCount": 1,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b6dc19df978c86c73c60a0",
          "content": "j，狗",
          "_user": {
            "_id": "60e38b3be82485289bc70f80",
            "gender": "m",
            "name": "雪 镇 哨 戒 机 枪",
            "title": "萌新",
            "verified": false,
            "exp": 750,
            "level": 3,
            "characters": [],
            "role": "member"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-25T09:57:45.429Z",
          "id": "62b6dc19df978c86c73c60a0",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b678f4cc22db3a9b3c7c77",
          "content": "JG出品（    ）",
          "_user": {
            "_id": "5f61c78abdb1a81c2ca879eb",
            "gender": "m",
            "name": "xiongmouren",
            "title": "萌新",
            "verified": false,
            "exp": 675,
            "level": 3,
            "characters": [],
            "role": "member"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 1,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-25T02:54:44.982Z",
          "id": "62b678f4cc22db3a9b3c7c77",
          "likesCount": 5,
          "commentsCount": 1,
          "isLiked": false
        },
        {
          "_id": "62b66cb666c852c227730449",
          "content": "谁先来？",
          "_user": {
            "_id": "59765dd56f10593244ceecfa",
            "gender": "m",
            "name": "装傻qwq",
            "title": "萌新",
            "verified": false,
            "exp": 1585,
            "level": 4,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "990ac052-baa4-4b56-a782-c79415b604a1.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-25T02:02:30.769Z",
          "id": "62b66cb666c852c227730449",
          "likesCount": 1,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b651cbdf978c86c73c27bb",
          "content": "sr不配有剧情……",
          "_user": {
            "_id": "5ac8b52136a6765d52aa598e",
            "gender": "m",
            "name": "紫護璃音",
            "title": "萌新",
            "verified": false,
            "exp": 2195,
            "level": 5,
            "characters": [],
            "role": "member",
            "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-25T00:07:39.305Z",
          "id": "62b651cbdf978c86c73c27bb",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "62b64f68df978c86c73c2723",
          "content": "jg怎么天天出新游戏？",
          "_user": {
            "_id": "5c30c071418dff4560bbc251",
            "gender": "m",
            "name": "424234",
            "title": "萌新",
            "verified": false,
            "exp": 3750,
            "level": 6,
            "characters": [],
            "role": "member",
            "avatar": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "7f24a07e-e100-4eec-86c9-ba3c93ac65be.jpg",
              "originalName": "avatar.jpg"
            },
            "slogan": "也就那样而已",
            "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
          },
          "_game": "62b588f9c741070644484949",
          "totalComments": 4,
          "isTop": false,
          "hide": false,
          "created_at": "2022-06-24T23:57:28.626Z",
          "id": "62b64f68df978c86c73c2723",
          "likesCount": 13,
          "commentsCount": 4,
          "isLiked": false
        }
      ],
      "total": 27,
      "limit": 20,
      "page": "1",
      "pages": 2
    },
    "topComments": []
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comments|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» content|string|true|none||none|
|»»»» _user|object|true|none||none|
|»»»»» _id|string|true|none||none|
|»»»»» gender|string|true|none||none|
|»»»»» name|string|true|none||none|
|»»»»» title|string|true|none||none|
|»»»»» verified|boolean|true|none||none|
|»»»»» exp|integer|true|none||none|
|»»»»» level|integer|true|none||none|
|»»»»» characters|[string]|true|none||none|
|»»»»» role|string|true|none||none|
|»»»»» avatar|object|true|none||none|
|»»»»»» originalName|string|true|none||none|
|»»»»»» path|string|true|none||none|
|»»»»»» fileServer|string|true|none||none|
|»»»»» slogan|string|true|none||none|
|»»»»» character|string|true|none||none|
|»»»» _game|string|true|none||none|
|»»»» totalComments|integer|true|none||none|
|»»»» isTop|boolean|true|none||none|
|»»»» hide|boolean|true|none||none|
|»»»» created_at|string|true|none||none|
|»»»» id|string|true|none||none|
|»»»» likesCount|integer|true|none||none|
|»»»» commentsCount|integer|true|none||none|
|»»»» isLiked|boolean|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|string|true|none||none|
|»»» pages|integer|true|none||none|
|»» topComments|[string]|true|none||none|

## POST 评论某个游戏

POST /games/{gameId}/comments

评论某个游戏，我的哔咔等级不够

> Body 请求参数

```json
{
  "content": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|gameId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» content|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 400,
  "error": "1031",
  "message": "higher level is required",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|string|true|none||状态码|
|» message|string|true|none||信息|
|» data|object|true|none||none|
|»» childsCount|integer|true|none||这个评论被回复几次（大概QAQ）|
|»» _comic|string|true|none||不清楚|
|»» _id|string|true|none||评论id|
|»» created_at|string|true|none||评论创建时间|
|»» likesCount|integer|true|none||点赞数|
|»» _parent|string|true|none||此评论如果是回复另外的评论，这个就有值（大概QAQ）|
|»» comment|object|true|none||评论本体|
|»»» content|string|true|none||评论的内容|
|»»» _user|object|true|none||用户|
|»»»» avatar|object|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»» character|string|true|none||none|
|»»»» exp|integer|true|none||none|
|»»»» gender|string|true|none||none|
|»»»» level|integer|true|none||none|
|»»»» name|string|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» verified|string|true|none||none|

## GET 游戏区

GET /games

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|string| 是 |页码|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "games": {
      "docs": [
        {
          "_id": "62b588f9c741070644484949",
          "title": "我的學妹不可能這麼萌",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "appicon_256_256.png",
            "path": "tobs/6f69b29d-23ea-4790-8972-55ac1cf35e9a.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "58296dee1cc00b5d50b1b5fe",
          "title": "機動戰隊大作戰",
          "version": "2.36.2",
          "publisher": "即时弹道运算引擎打造热血像素机甲格斗手游",
          "suggest": true,
          "adult": false,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "icon125x125.png",
            "path": "tobs/051285ee-b373-48ef-9b3b-8ace996f144b.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6298d9c5d946c75549fa4ce1",
          "title": "色慾終章：墮落",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "色慾終章_AppIcon.png",
            "path": "tobs/53618875-aeae-4ad7-9f79-3d4c90e160a3.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "62b4134ac7410706444846bd",
          "title": "閃耀★青春追逐記",
          "version": "1.0.0",
          "publisher": "SAGA PLANETS",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面.png",
            "path": "tobs/f421289d-7d2e-4627-bf8d-23a35e8dda48.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "626a90c5c6277f4619dcb446",
          "title": "式神: 呪縛",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "式神 App Icon.png",
            "path": "tobs/0e5ce5dd-a381-4716-9bcd-67a31eb5fd2b.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6298de7e9cae2c554fe4dbc0",
          "title": "9-nine-雪色雪花雪之痕",
          "version": "",
          "publisher": "Palette",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "tobs/b9b7992d-14a9-4802-92c2-b08cba59a27e.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "61f3f988acc213501f82e1b6",
          "title": "終末聖女：Dark Ages",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "DARKAGES_13_256_256_appicon.png",
            "path": "c45ac5ba-7548-43c0-8802-873183de87c8.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6298de07d946c75549fa4d4c",
          "title": "9-nine-春色春恋春熙风",
          "version": "1.0.0",
          "publisher": "Palette",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "tobs/4dedc4de-3ac0-4f1b-b38e-735a76556405.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "601d3abdcfeaee28f8d8cb72",
          "title": "逆王傳說: 入侵女兒國",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "app icon 1.4 256.png",
            "path": "7d3e73a5-2416-4d11-a747-534fd558bf24.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6287610f484bac02bee443bd",
          "title": "一臉嚴肅的委員長居然偷偷寫自我發電日記",
          "version": "1.0.0",
          "publisher": "dobuworks",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "封面-min.jpg",
            "path": "tobs/86a45cad-1d3f-4612-8a61-4369377b383f.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6262750ac56a2a031d5de1ce",
          "title": "龍吟艷史",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "正常版_Harem2_AppIcon.png",
            "path": "tobs/8dcee970-6397-4ad5-afac-0ce5b6c8a413.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6298dd139cae2c554fe4dbaf",
          "title": "9-nine-天色天歌天籁音",
          "version": "1.0.0",
          "publisher": "Palette",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "tobs/32dc1c2a-4896-4790-8792-e57bed1a4f46.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "623ec8840289ac071ec8bb96",
          "title": "創戰少女",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "創戰少女 icon2.png",
            "path": "tobs/d903b1fd-dc75-438b-8041-4112745cbc4f.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6298dc83fee4a055417cdd98",
          "title": "9-nine-九次九日九重色",
          "version": "",
          "publisher": "Palette",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "tobs/c7c49d4c-b9d1-4fac-ba5f-dbe481720a48.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6142dff6e393d66f60f74bdd",
          "title": "命運王座",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "FGO_13_256_256_icon.png",
            "path": "e016dff0-1b2f-4b3b-9883-660223aac509.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "62735e591529d805373dc327",
          "title": "chasing tails ～ 雪中誓約",
          "version": "1.0.0",
          "publisher": "FCD Games",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "封面-min.jpg",
            "path": "tobs/db4c554c-5632-45d3-a35a-57ac6b2868ce.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "62174489e14c3d601db6b6c6",
          "title": "三國戀姬傳",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "三國戀姬傳 app icon2.png",
            "path": "1116ee3c-d17d-46a3-bd03-0be3a3780125.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6258f168752d4a53f52905bd",
          "title": "LOVELY×CATION2",
          "version": "1.0.0",
          "publisher": "AKABEiSOFT2",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面.jpg",
            "path": "tobs/19a5d383-12df-46fc-8e6b-c8594da31f63.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "61cae6063dcb9833fd98327c",
          "title": "萌娘大戰",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "萌娘大戰 app icon 512.png",
            "path": "9b64d088-c4f5-4aae-a0ab-ec391d825bd3.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6217455fa97b736039c1a133",
          "title": "罪惡集中營",
          "version": "1.0.0",
          "publisher": "PlayMeow Games",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "封面.jpg",
            "path": "12641cd1-c4ea-46a6-b681-0fb643d6776d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61a8da6be5b2880d9891a48c",
          "title": "轉生女帝 - 學園征戰計劃",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "Squirt_256_256_appicon.png",
            "path": "c539e174-782b-480b-9dd9-dcb05c3467c0.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "62515100562e2b59ee02ce72",
          "title": "玉響未來 深野協調魔法使",
          "version": "1.0.0",
          "publisher": "Azurite",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "tobs/ebc006e6-9a0d-4f5c-ac15-d40251eb1d80.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6294ba002040f008252d2c99",
          "title": "星際禁區",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "IFZ_51_256_256_appicon.png",
            "path": "tobs/78bf4402-b897-4c38-adae-8efdb106cec9.png",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "6200b8bf8c1ff5503819d8eb",
          "title": "獻給神明般的你",
          "version": "1.0.0",
          "publisher": "CUBE",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面-min.jpg",
            "path": "dd5c9cd7-011a-4791-8347-d1ce25324827.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6151ae41b768b87fe0644935",
          "title": "推倒我! 總裁!",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "sincity_13_256-256_appicon.png",
            "path": "4128ab5a-585e-4c20-b3e9-c0ecb9dd0438.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61de88cab93f6b06e93135be",
          "title": "與殘念姐姐的幸福論",
          "version": "1.0.0",
          "publisher": "りびどーそふと",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "9451658d-8c0a-4803-9d04-108052ee7641.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61caeef93dcb9833fd9832fa",
          "title": "女校男生: 最強制霸",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "school_256_256_appicon.png",
            "path": "39307b90-becf-489f-a0fd-41b24bb2838d.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61caea2e9cff033407870c84",
          "title": "PARQUET",
          "publisher": "ゆずソフトSOUR",
          "version": "1.0.0",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "capsule_616x353.jpg",
            "path": "e80fbe84-31c7-4025-8c60-9e9c072cf123.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60fec2fab2ce8a24cbed6f72",
          "title": "異世界催眠師",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "異界催眠師APP 256.png",
            "path": "d27d9a82-69bf-44a7-a759-efffd122a5fd.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61de8820b93f6b06e93135b4",
          "title": "愛麗婭的明日盛典",
          "version": "1.0.0",
          "publisher": "NaNaWind",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "11cf9c79-87f6-4502-b4c9-ff058244bcbf.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6166de8c88bb33086accf5c9",
          "title": "女神日記",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "女神 icon.png",
            "path": "f25dac49-6f42-4217-8bfc-779a1f6c9456.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61caecc33dcb9833fd9832ce",
          "title": "日向千尋的工作總是做不久",
          "publisher": "SUMIRE",
          "version": "1.0.0",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "header_schinese.jpg",
            "path": "61227136-c17d-4b39-90b0-4048987d4c82.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f4c98597de2bb73a0fdc42c",
          "title": "黑道總裁",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "黑幫總裁-圓角-logo.png",
            "path": "ac60e5cf-474e-4194-96c1-ec7e8884bd2d.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61cae6cd9cff033407870c68",
          "title": "不可視之藥與坎坷的命運",
          "version": "1.0.0",
          "publisher": "HULOTTE",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_cover.jpg",
            "path": "3937efcd-0585-4a0c-a4cd-4925c12fa6cf.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f27df6709eed40fd1bb478c",
          "title": "末世王者",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "JGG-web-display-game-iconArtboard-1-copy-9.png",
            "path": "374ab04d-c8a5-43a8-ab4a-100992b867a1.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61c43d46d4c7cd46802e3f72",
          "title": "超痴女2",
          "version": "1.0.0",
          "publisher": "KENZsoft",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面1.jpg",
            "path": "d169acba-ac68-4f54-9e0f-0ccf6da793c7.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60d5d938c216301eb92d16c2",
          "title": "愛愛學園",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "2.png",
            "path": "1a49bd40-aa65-4d71-9918-abb3cdf99752.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61b0ab36002434489f72744e",
          "title": "與狐妖同居的生活",
          "version": "1.0.0",
          "publisher": "PlayMeow Games",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "封面-min.jpg",
            "path": "746591d1-d67a-4fa8-877a-a840cf6f9283.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60433ff34f166440722f3549",
          "title": "SF性戰士",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "sf girls app icon_256-min.png",
            "path": "0a5193ea-8092-474f-9a6b-f882d3d1f45c.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "61878c8d61803819299d8ac2",
          "title": "冥契的牧神節",
          "publisher": "UGUISU KAGURA",
          "version": "1.0.0",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "image(1).jpg",
            "path": "123e5d47-38d3-42d7-9dcd-00c4aa0d9372.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6130bc204f0ddf38840e8699",
          "title": "極道世界",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "極道世界APP ICON.png",
            "path": "47f7e2b7-abe4-4ad6-9133-55dd7a053ae5.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "619d06cdf9cd94370e57ba5c",
          "title": "惡魔少女",
          "version": "1.0.0",
          "publisher": "PlayMeow Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "封面-min.jpg",
            "path": "87ee2bea-98b1-41f5-84bf-db5559d0aaf7.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5fc9a31a3d22d50ffde3b05a",
          "title": "峰火玉乳",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "烽火玉乳256 app icon.png",
            "path": "93573f2b-8a9e-4924-8f8a-a619ca4ad683.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6173cfbb2f8145071d609302",
          "title": "戀愛 x 決勝戰",
          "version": "1.0.0",
          "publisher": "Asa Project",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面.jpg",
            "path": "de052c34-4c40-4cdc-a715-c3779719e0c1.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "613a1d790dac716f6a9f6bf9",
          "title": "無限方舟",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "abyss_13_256_256_app_icon.png",
            "path": "fce84fc0-8e58-480f-81e2-877be4c6ced6.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "615b0e7efae2ba013164d9aa",
          "title": "Deep One",
          "version": "1.0.0",
          "publisher": "Nameless",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面.jpg",
            "path": "224ea30b-407f-40c5-ab56-2ed0f975b42b.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "600fbe2e465c785d3a230d75",
          "title": "星球掠奪者",
          "version": "1.0.0",
          "publisher": "JG Game",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "landing-page-v1-cyberpink-export256-256.png",
            "path": "85d665c4-ea71-4204-8f5a-d732be299512.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "611f6911fafd521cfec9f0cf",
          "title": "美少女萬華鏡4~罪與罰之少女",
          "version": "1.0.0",
          "publisher": "ωstar",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面.jpg",
            "path": "c9f878a6-85bf-4386-ab2e-8dc38e137953.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "625bd662752d4a53f52937ee",
          "title": "女神連結 GCO",
          "version": "1.6.13",
          "publisher": "H365",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "GCO_20220317_512x512_North_CN.jpg",
            "path": "tobs/189ffa81-b67d-4ae8-b56b-2fa423cb2ae4.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          }
        },
        {
          "_id": "60f6a62bae187670a40c4f4b",
          "title": "與女朋友的甜蜜生活～你喜歡銀發美少女嗎？",
          "version": "1.0",
          "publisher": "monoceros+",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面.jpg",
            "path": "ff73e977-0110-48ff-8591-3f6e2bf3e3c7.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5fe844a52601ab1141976546",
          "title": "天下布魔",
          "version": "1.0.0",
          "publisher": "工口.R18 ",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "1607920385659.jpg",
            "path": "93fe1df1-2f24-4560-97b3-57b8c22024fd.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60d5db007c9d371e94067174",
          "title": "吹彈！豐盈！波濤洶涌！異世界魔法學園！",
          "version": "1.0.0",
          "publisher": "Milkfactory",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "image.jpg",
            "path": "a945f8d1-109c-4266-96fd-8801a3848f25.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e58b73c9e1fb175abc6b06c",
          "title": "城市裡的歐派",
          "version": "1.0.0",
          "publisher": "工口.R18 ",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "嗶卡投放_選單icon_城市裡的歐派_256x256.jpg",
            "path": "51d55f17-4303-421e-8220-3d8897fefc0b.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60d37d2898d3d12a995ca235",
          "title": "國民偶像SEX解禁",
          "publisher": "Norn",
          "version": "1.0.0",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "1.jpg",
            "path": "e2eae0cc-f550-4968-928a-7f3e9c7a077c.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e5135081415be3c4cb5c8b0",
          "title": "紳士冒險",
          "version": "1.0.0",
          "publisher": "工口.R18 ",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "嗶卡投放_選單icon_紳士冒險_256x256.jpg",
            "path": "f8ff5aef-220a-46b0-99f3-a823f33cfd60.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60a7cb2a705c964612ba3019",
          "title": "天降虛擬偶像",
          "version": "1.0.0",
          "publisher": "akabeesoft2",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "6.jpg",
            "path": "d2f3f43b-4f06-471b-bc0c-0fc136c6335c.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60fec4c13a8a1824a38dd3c8",
          "title": "名妓三國",
          "version": "1.0.0",
          "publisher": "H365",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "首頁ICON2(512x512).jpg",
            "path": "81892980-2f91-4f83-a1a9-46fcd93df4f5.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "605a0704e4e58260ec58c72d",
          "title": "女僕Life",
          "publisher": "高溫注意",
          "version": "1.0.0",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "image(2)拷貝.jpg",
            "path": "bb664e7d-964c-4aa9-a5cb-17d7937675eb.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5fce3811091aaa1ec80ea931",
          "title": "中出世紀",
          "version": "1.0.0",
          "publisher": "H365",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "icon.jpg",
            "path": "985290b8-acde-42ac-bc47-10948e2586d9.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "606ce00643d28c474b4db53d",
          "title": "抖M妹妹想要私人教學",
          "version": "1.0.0",
          "publisher": "ソフトさーくるクレージュ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "1.jpg",
            "path": "54ba6267-3478-49fd-8110-01b12658b351.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f7711552ab34579d8621720",
          "title": "豔遊記",
          "version": "1.0.0",
          "publisher": "H365",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "ICON (256X256).jpg",
            "path": "f5e582d6-00e8-4715-b463-6b24d4b6f8b0.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "6059ff529f59ae60ff07f491",
          "title": "心動不已文學部 (DDLC)",
          "version": "1.0.0",
          "publisher": "Team Salvato",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "image(2).jpg",
            "path": "838903ef-a75b-4d7a-8f80-bce72a0efddd.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f9d3bd06298f35a668aef3e",
          "title": "豔舞姬",
          "version": "1.0.0",
          "publisher": "工口.R18 ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "256x256.png",
            "path": "81180708-9c8d-4b78-85d2-4db1ad02a409.png",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "602d334b1001c26ee70fdf52",
          "title": "美少女萬華鏡5-理與迷宮的少女",
          "version": "3.0",
          "publisher": "ωstar",
          "suggest": true,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "1.jpg",
            "path": "73f42d5b-6530-4ec1-8039-67914886fda3.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f71aa4c723d1379cbfd6851",
          "title": "性愛天使",
          "version": "1.0.0",
          "publisher": "工口.R18 ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "66_PICA_性愛天使_640x360_V01.jpg",
            "path": "2a786c7d-87fc-40ac-aeb6-54d07e31e948.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60218e7a37c76a6f030a60e5",
          "title": "愛上火車 - Last Run",
          "version": "1.0.0",
          "publisher": "Wamsoft",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "1.jpg",
            "path": "3a507259-9e9b-4b36-ab58-fc767d3959d7.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "60705d1243d28c474b4e3b3e",
          "title": "戰女無雙",
          "version": "1.0.0",
          "publisher": "工口.R18 ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "首頁Icon_256x256_SC.jpg",
            "path": "ff1f3153-f243-4cc1-b9ca-ce9c071f17ae.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5fda18a859b287406e1d47fd",
          "title": "NEKOPARA Vol.4",
          "version": "1.0.0",
          "publisher": "NEKO WORKs",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "00000002.jpg",
            "path": "fc62a8f4-382d-405c-b342-9756856e7a8c.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f48d03716a0b673b3fd9616",
          "title": "我的乳搖學妹",
          "version": "1.0.0",
          "publisher": "工口.R18 ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "首頁ICON640-534.jpg",
            "path": "c91b2cb9-3933-4b20-a37a-d54aa45bd68f.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5fb792bd2651d67233b5c82e",
          "title": "Salete",
          "version": "1.0.0",
          "publisher": "Soiree 作者：爱吃蛋糕的医生 ht",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面-min.jpg",
            "path": "aca874c2-3fc9-4bf7-9be9-a2d5bf5b5076.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f9d39fc6298f35a668aee32",
          "title": "水葬銀貨のイストリア",
          "version": "1.0.0",
          "publisher": "ウグイスカグラ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "cover.jpg",
            "path": "93115387-c439-4f2b-9f85-2e12c397a486.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f9bc28b3210e95a76fe0914",
          "title": "魔女的夜宴",
          "publisher": "YuzuSoft",
          "version": "1.0.0",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "Sanoba_0000.jpg",
            "path": "c1941494-fd01-4689-ba4e-54fc55c6d073.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f71abd0723d1379cbfd6972",
          "title": "青空的卡繆",
          "version": "1.0.0",
          "publisher": "KAI-SOFT",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "封面.jpg",
            "path": "3378f129-998f-48aa-8448-0ce7e63ab772.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f474d14b610096a32c49e9a",
          "title": "悪役令嬢母娘の下僕",
          "version": "1.0.0",
          "publisher": "Norn／Miel／Cybele ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "ev004a.jpg",
            "path": "ed42a329-cbfe-4f85-b338-cafbe9db203d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f1ae19cf6f1a741687f6c26",
          "title": "甜蜜姐姐 My Sweet Sister",
          "version": "1.0.0",
          "publisher": "Campus",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "0002_t_bg.jpg",
            "path": "6570eee8-b60d-415c-81a0-25afed98b869.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5f0846d8890ff22e8b4b52a3",
          "title": "诱惑自大洛丽塔",
          "version": "1.0.0",
          "publisher": "夜羊社游戲",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "002__title.jpg",
            "path": "e3c9054a-b892-46cb-90e7-d5cf15817995.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5eecaf7973012151299070aa",
          "title": "姉と妹の性事情",
          "version": "1.0.0",
          "publisher": "梅麻呂",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "Screenshot_20200619-192826_MoboPlayer-min.jpg",
            "path": "4c009417-116e-4e71-a6f5-ab5ed80f68ea.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5ed7b21b1e455157f2eb8768",
          "title": "戀愛定位❤同居×後輩",
          "version": "1.0.0",
          "publisher": "FrontWing",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "0531_1.jpg",
            "path": "f3899002-a1c9-4268-a249-e1fa317a1a14.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5eca7bcf1654121089f16441",
          "title": "星光咖啡館與死神之蝶",
          "version": "1.0.0",
          "publisher": "YuzuSoft",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_title_bg.jpg",
            "path": "a25e5c40-ba5e-4479-add2-f5382c9df237.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5eba7a1c7ac7771313fa3278",
          "title": "孕ませ!炎のおっぱい超エロ♡アプリ学園！",
          "version": "1.0.0",
          "publisher": "Milk Factory",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "1.jpg",
            "path": "812a7e73-5325-45b7-8415-ced6aba07af2.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e9ac333b724bb4884867880",
          "title": "白戀 Sakura＊Gram",
          "publisher": "NanaWind",
          "version": "1.0.0",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_cover(3).jpg",
            "path": "0c5b0d2e-c9e1-4487-b14a-b1e254dd08dd.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5eba768d63e4ed12ffc8fcae",
          "title": "戀愛定位  電車×同級生",
          "version": "1.0.0",
          "publisher": "FrontWing",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "1.jpg",
            "path": "68c33756-00b1-45d9-9b3f-a26d71743f8a.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e7b55a2d0894c7413f2dbe4",
          "title": "由夢想與彩色編織而成",
          "version": "1.0.0",
          "publisher": "Feng",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_cover(2).jpg",
            "path": "712071c6-ee9f-49b9-b3ff-f31667f92b18.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e4e16a23abef73c5b517822",
          "title": "愛麗婭的明日盛典！",
          "publisher": "NanaWind",
          "version": "1.0.0",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "001_a.jpg",
            "path": "bc9d68cf-ff1d-40c6-b3f4-26e7ed45ac73.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e4e15d93abef73c5b51780c",
          "title": "Your Diary +H",
          "version": "1.0.0",
          "publisher": "CUBE",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "unnamed2.jpg",
            "path": "af832044-0106-4125-85b4-8ba910507476.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e60a8601f7673759b6e3253",
          "version": "1.1.0",
          "title": "奈的調教日記",
          "publisher": "バナナキング",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "0221_1.jpg",
            "path": "3572fba1-614e-48be-a1b5-b6ae1faa0e81.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e0df8965ed75427ee616c8a",
          "title": "哥哥，早上起床之前都要抱緊我哦！",
          "version": "1.0.0",
          "publisher": "Tinkle Position",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_cover2.jpg",
            "path": "ce62e874-5178-4d17-8261-58757a6ac2d1.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e0df7915ed75427ee616c6a",
          "title": "Charabration! 戀愛崩壞",
          "version": "1.0.0",
          "publisher": "AKABEiSOFT3＊KITSUKI",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_cover(1).jpg",
            "path": "52ef8ee8-d704-4215-bbae-142c3c05b0ed.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5e0df63a98515f2815e4ae02",
          "title": "寄宿之戀",
          "version": "1.0.0",
          "publisher": "ASa Project",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_TI_Base.jpg",
            "path": "4d85692c-b7db-4b73-893b-c575113c4436.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5ded08947cd2ce4ed0f5e101",
          "title": "真愛の百合は赤く染まる",
          "version": "1.0.0",
          "publisher": "バグシステム",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "2019-12-09 23.29.05.jpg",
            "path": "260034ca-77b3-458a-99c1-1eb11b3a05a4.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5db1a72077d0ce3caa3d5126",
          "title": "喵妹與狗妹的咖啡屋",
          "version": "1.0.0",
          "publisher": "Cherry Kiss Games",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "1023_1.jpg",
            "path": "ac512915-dd76-4e87-84ee-80c36f0e2c88.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5da9ec34e1608b196cbe2487",
          "title": "純白交響曲",
          "version": "1.0.0",
          "publisher": "ぱれっと",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "001_a.jpg",
            "path": "febb1f89-3af1-49f9-a814-26c190593ed3.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5da9eb33e1608b196cbe2480",
          "title": "思影",
          "version": "1.0.0",
          "publisher": "あかべぇそふとすりぃ",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_t_bg.jpg",
            "path": "77b2fead-4f80-4a09-8b35-1f32128e845a.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d5d6cea881d5279d332c251",
          "title": "Re:LieF ~給親愛的你",
          "version": "1.0.0",
          "publisher": "RASK",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "1.jpg",
            "path": "dbd7f6fb-e37a-4690-891c-d0d042b72690.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d511f6779f8d4028e63c0a7",
          "title": "戀花綻放櫻飛時",
          "version": "1.0.0",
          "publisher": "ぱれっと",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "snap001.jpg",
            "path": "ef6137dc-fabd-4085-9743-a1763a284aac.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d4a7be47f010245a31fe9dc",
          "title": "Chronobox",
          "version": "1.0.0",
          "publisher": "No Brand",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "photo_2019-08-08_03-35-16.jpg",
            "path": "95606afc-a47e-4cc0-87e8-a016d6aaa669.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d354f5b30dda25b3b542dbb",
          "title": "CLANNAD",
          "version": "1.0.0",
          "publisher": "Key",
          "suggest": false,
          "adult": false,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "0a7c125f-4f8e-4922-b9ab-275bc9e94e52.jpg",
            "path": "5d8d36d0-f0f7-4935-a9d7-1f9a0dd26fb7.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d2a0dff33cb8f151c2f1812",
          "title": "與我戀愛的廢材惡魔",
          "version": "1.0.0",
          "publisher": "SMILE",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "0709_1-min.jpg",
            "path": "4e263c10-7249-4c43-8504-e9b544fffd56.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d2a0a1c86d21315177bf1c1",
          "title": "背叛 Betrayed",
          "version": "0.41",
          "publisher": "紙片人",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": false,
          "icon": {
            "originalName": "unnamed.jpg",
            "path": "52105d4b-9513-4e2c-8a36-d14e2d78767d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d1cd522899f634c7bda337c",
          "title": "哥哥、早上起床之前都要抱緊我哦!",
          "version": "1.0.0",
          "publisher": "Tinkle Position",
          "suggest": false,
          "adult": true,
          "android": true,
          "ios": true,
          "icon": {
            "originalName": "_cover.jpg",
            "path": "6a9f06d4-3818-4ee7-b63e-fdd23c2ea1f3.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        }
      ],
      "total": 150,
      "limit": 100,
      "page": 1,
      "pages": 2
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» games|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» title|string|true|none||none|
|»»»» version|string|true|none||none|
|»»»» publisher|string|true|none||none|
|»»»» suggest|boolean|true|none||none|
|»»»» adult|boolean|true|none||none|
|»»»» android|boolean|true|none||none|
|»»»» ios|boolean|true|none||none|
|»»»» icon|object|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» pages|integer|true|none||none|

## POST （取消）喜欢此游戏

POST /games/{gameId}/like

该接口是like某一个（gameId）游戏，第一次使用是like，第二次是un_like

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|gameId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "action": "like"
  }
}
```

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "action": "unlike"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» action|string|true|none||none|

# comics

## GET 获取本子详细信息

GET /comics/{comicId}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comic": {
      "_id": "58218b725f6b9a4f93e02a99",
      "_creator": {
        "_id": "58298f4f2cff4358503589c1",
        "gender": "bot",
        "name": "小 6",
        "exp": 293358,
        "level": 54,
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "59c37cc9-c396-43c7-8a15-56798b03b8a7.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "characters": [
          "knight"
        ],
        "title": "萌新"
      },
      "title": "舞姦 弐",
      "description": "\n⚠️⚠️⚠️⚠️⚠️⚠️\n此本子已被標記為重口（官方聲明）\n\n請注意，這本子的內容過於重口味，可能會使人產生惡心、頭暈等不適症狀，亦有可能使閣下情緒有負面影響，因此我們認為這個本子不適合任何人仕觀看。\n\n如閣下仍然執意決定要觀看，請閣下自行承受觀看後的後果。若有任何不適症狀，請立刻停止觀看並及時向醫師尋求幫助。 \n⚠️⚠️⚠️⚠️⚠️⚠️\n\n不知火舞的堕落",
      "thumb": {
        "originalName": "cover.jpg",
        "path": "tobeimg/m0Z5PRsK_DqYPC5yMeOulBwsZsRlN3t1klBdObSpWvg/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy85MmZkZGY1ZS04OWQ3LTQwYWUtYjMzNi04NjRlNzViNDEyODMuanBn.jpg",
        "fileServer": "https://storage1.picacomic.com"
      },
      "author": "[ブレキン。(榊歌丸)]",
      "chineseTeam": "未知",
      "categories": [
        "同人",
        "短篇",
        "重口地帶",
        "強暴"
      ],
      "tags": [],
      "pagesCount": 20,
      "epsCount": 1,
      "finished": false,
      "updated_at": "2008-01-08T00:47:25.000Z",
      "created_at": "2008-01-08T00:47:25.000Z",
      "allowDownload": true,
      "allowComment": true,
      "totalLikes": 253,
      "totalViews": 65220,
      "totalComments": 4,
      "viewsCount": 65224,
      "likesCount": 253,
      "commentsCount": 5,
      "isFavourite": false,
      "isLiked": false
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comic|object|true|none||none|
|»»» _id|string|true|none||none|
|»»» _creator|object|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» gender|string|true|none||none|
|»»»» name|string|true|none||none|
|»»»» exp|integer|true|none||none|
|»»»» level|integer|true|none||none|
|»»»» role|string|true|none||none|
|»»»» avatar|object|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»»» characters|[string]|true|none||none|
|»»»» title|string|true|none||none|
|»»» title|string|true|none||none|
|»»» description|string|true|none||none|
|»»» thumb|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»» author|string|true|none||none|
|»»» chineseTeam|string|true|none||none|
|»»» categories|[string]|true|none||none|
|»»» tags|[string]|true|none||none|
|»»» pagesCount|integer|true|none||none|
|»»» epsCount|integer|true|none||none|
|»»» finished|boolean|true|none||none|
|»»» updated_at|string|true|none||none|
|»»» created_at|string|true|none||none|
|»»» allowDownload|boolean|true|none||none|
|»»» allowComment|boolean|true|none||none|
|»»» totalLikes|integer|true|none||none|
|»»» totalViews|integer|true|none||none|
|»»» totalComments|integer|true|none||none|
|»»» viewsCount|integer|true|none||none|
|»»» likesCount|integer|true|none||none|
|»»» commentsCount|integer|true|none||none|
|»»» isFavourite|boolean|true|none||none|
|»»» isLiked|boolean|true|none||none|

## GET 获取本子的评论

GET /comics/{comicId}/comments

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |none|
|page|query|integer| 否 |分页|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comments": {
      "docs": [
        {
          "_id": "62c3fb4c45fc283cdcb14ce9",
          "content": "et id consectetur",
          "_user": {
            "_id": "5e2bece8d606e72a7f38402f",
            "gender": "m",
            "name": "自己开发比卡",
            "title": "萌新",
            "verified": false,
            "exp": 550,
            "level": 2,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "f6d5a28f-4b32-4c4b-8ac5-c396cbea0eb6.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "slogan": "11111111"
          },
          "_comic": "58218b725f6b9a4f93e02a99",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-07-05T08:50:20.349Z",
          "id": "62c3fb4c45fc283cdcb14ce9",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "5e6fb74ee4842e129425a919",
          "content": "安迪要坚强",
          "_user": {
            "_id": "59b79ef973345860bdf96f61",
            "gender": "m",
            "name": "头大的tian",
            "title": "萌新",
            "verified": false,
            "exp": 420,
            "level": 2,
            "characters": [],
            "role": "member",
            "avatar": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "cfe2b319-6aa6-4549-bffd-4cd5b18e8110.jpg",
              "originalName": "avatar.jpg"
            },
            "slogan": "deep♂dark♂fantasy",
            "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
          },
          "_comic": "58218b725f6b9a4f93e02a99",
          "isTop": false,
          "hide": false,
          "created_at": "2020-03-16T17:28:46.039Z",
          "id": "5e6fb74ee4842e129425a919",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "5db548e97b6d432d4c117fe4",
          "hide": false,
          "isTop": false,
          "_comic": "58218b725f6b9a4f93e02a99",
          "_user": {
            "_id": "5995f62a6438d97844949de5",
            "gender": "m",
            "name": "后宫男主角",
            "title": "萌新",
            "verified": false,
            "exp": 890,
            "level": 3,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "db52ca18-6abe-47e1-b41f-9ab57f779f2d.jpg",
              "fileServer": "https://storage1.picacomic.com"
            }
          },
          "content": "想到纯洁轮舞曲",
          "created_at": "2017-11-08T08:56:09.745Z",
          "id": "5db548e97b6d432d4c117fe4",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "5da5a88e7b6d432d4c0082f1",
          "hide": false,
          "isTop": false,
          "_comic": "58218b725f6b9a4f93e02a99",
          "_user": {
            "_id": "5829cbd01cc00b5d50b1c046",
            "gender": "bot",
            "name": "我去了",
            "exp": 310,
            "level": 2,
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "abb3d0a8-4c52-4866-9104-11fa7b6eefca.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "characters": [],
            "title": "萌新"
          },
          "content": "伟大的哗咔啊，给点重口吧",
          "created_at": "2016-11-21T04:32:31.178Z",
          "id": "5da5a88e7b6d432d4c0082f1",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "5da5a8687b6d432d4c007b31",
          "hide": false,
          "isTop": false,
          "_comic": "58218b725f6b9a4f93e02a99",
          "_user": {
            "_id": "582a6b2607ee4b8422ba5559",
            "gender": "m",
            "name": "红色的我 ",
            "exp": 2680,
            "level": 5,
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "7f89eea2-6c79-435f-853c-1ae39a697acd.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "characters": [],
            "title": "萌新",
            "slogan": "null"
          },
          "content": "作品太少了",
          "created_at": "2016-11-20T01:50:13.649Z",
          "id": "5da5a8687b6d432d4c007b31",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        }
      ],
      "total": 5,
      "limit": 20,
      "page": "1",
      "pages": 1
    },
    "topComments": []
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comments|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» content|string|true|none||none|
|»»»» _user|object|true|none||none|
|»»»»» _id|string|true|none||none|
|»»»»» gender|string|true|none||none|
|»»»»» name|string|true|none||none|
|»»»»» title|string|true|none||none|
|»»»»» verified|boolean|false|none||none|
|»»»»» exp|integer|true|none||none|
|»»»»» level|integer|true|none||none|
|»»»»» characters|[string]|true|none||none|
|»»»»» role|string|true|none||none|
|»»»»» avatar|object|true|none||none|
|»»»»»» originalName|string|true|none||none|
|»»»»»» path|string|true|none||none|
|»»»»»» fileServer|string|true|none||none|
|»»»»» slogan|string|true|none||none|
|»»»»» character|string|false|none||none|
|»»»» _comic|string|true|none||none|
|»»»» totalComments|integer|false|none||none|
|»»»» isTop|boolean|true|none||none|
|»»»» hide|boolean|true|none||none|
|»»»» created_at|string|true|none||none|
|»»»» id|string|true|none||none|
|»»»» likesCount|integer|true|none||none|
|»»»» commentsCount|integer|true|none||none|
|»»»» isLiked|boolean|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|string|true|none||none|
|»»» pages|integer|true|none||none|
|»» topComments|[string]|true|none||none|

## POST 发送本子评论

POST /comics/{comicId}/comments

> Body 请求参数

```json
{
  "code": 0,
  "message": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» code|body|integer| 是 |none|
|» message|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 推荐

GET /comics/{comicId}/recommendation

哔咔下面的推荐（猜你喜欢）

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comics": [
      {
        "_id": "58218b835f6b9a4f93e02fc7",
        "title": "痴女・不知火舞",
        "thumb": {
          "originalName": "cover.jpg",
          "path": "tobeimg/7RoldRJjjjIRvQE1ghhn8SHZ82qzjRlwNYhxCxP8chI/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9hOWU4MTJmZi04ODY2LTQ3ZTctOWM4Zi05ZDg3OWY4ZjRlOGIuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "author": "INSERT(KEN)",
        "categories": [
          "同人",
          "短篇"
        ],
        "finished": false,
        "epsCount": 1,
        "pagesCount": 11,
        "likesCount": 3011
      },
      {
        "_id": "58218b735f6b9a4f93e02b05",
        "title": "闘参 ～KAKUTOU-GAME BON 2007-3～",
        "thumb": {
          "originalName": "cover.jpg",
          "path": "tobeimg/U5ogzq2OShwDA2Z2-1FCGpDQP4X8QdfoQ2qnQ9yLwZo/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9mMDVhZTk1Mi1kNzRlLTRmZDktOWI3Zi03YzI2NDRiZmI4OTkuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "author": "[P-collection(のりはる)]",
        "categories": [
          "同人",
          "短篇"
        ],
        "finished": false,
        "epsCount": 1,
        "pagesCount": 18,
        "likesCount": 211
      },
      {
        "_id": "58218b825f6b9a4f93e02f8d",
        "title": "妻舞喰いして欲しいの",
        "thumb": {
          "originalName": "cover.jpg",
          "path": "tobeimg/RFaXfqd2BxUn-V5YOC4k5iqds_I9a-_Ky7cqCWGx334/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9iNTczYzFiOC0xMDZmLTQ2ZDItODQwZC00OTA4NGQxMjMxZTEuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "author": "もっちー王国(もっちー)",
        "categories": [
          "同人",
          "人妻",
          "短篇"
        ],
        "finished": false,
        "epsCount": 1,
        "pagesCount": 27,
        "likesCount": 319
      },
      {
        "_id": "5de326344a59a87db1637d95",
        "title": "舞姦 (ザ・キング・オブ・ファイターズ)系列",
        "author": "ブレキン。 (榊歌丸)",
        "pagesCount": 38,
        "epsCount": 2,
        "finished": false,
        "categories": [
          "短篇",
          "同人",
          "強暴"
        ],
        "thumb": {
          "originalName": "00000001.jpg",
          "path": "tobeimg/4B-yagVCZ5IfZRLSoi6ReksqEs24CFYMpCJ00BNfcAo/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8xNjY0YzUwMi0zOGRlLTQ2MGYtOWY5MS1mYzU0ZTJlNTM1MTIuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "likesCount": 6
      },
      {
        "_id": "58218b635f6b9a4f93e024f5",
        "title": "民宿いなりむし(終焉)",
        "thumb": {
          "originalName": "cover.jpg",
          "path": "tobeimg/0Rc7SvFMIJn4LigA6psmh1N4flszK83ktzeTPSk1IBA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8zMzlmZjI5MS1mMjZlLTQ2ODAtYjUzNC1lNzgyNDkxZWY0NTkuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "author": " 乳乱舞 Vol.10",
        "categories": [
          "同人",
          "短篇"
        ],
        "finished": false,
        "epsCount": 1,
        "pagesCount": 18,
        "likesCount": 177
      },
      {
        "_id": "5af125e5c9934656efdb808f",
        "title": "[3D]不知火舞的死期(琦玉老师乱入）重口慎入",
        "author": "乔治布鲁诺",
        "pagesCount": 59,
        "epsCount": 3,
        "finished": false,
        "categories": [
          "全彩",
          "同人",
          "短篇",
          "CG雜圖",
          "SM",
          "重口地帶",
          "強暴",
          "非人類"
        ],
        "thumb": {
          "originalName": "61248120_p14_master1200.jpg",
          "path": "tobeimg/Y8AJntsm5dbqUXiANCqwhWiGCBy8QA6j6lZzWrNt8dA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8xY2IyMDdkMy05NmZhLTQ2ZTItYjQ0Yi05MTY1ZjY2YTRlODMuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "likesCount": 1777
      },
      {
        "_id": "61c7fef59e46c934219a739f",
        "title": "不知火道場通信 vol.01 -不知火舞祝勝会開催-",
        "author": "エロマフィア (江戸しげズ)",
        "pagesCount": 21,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "全彩",
          "短篇",
          "同人"
        ],
        "thumb": {
          "originalName": "0.jpg",
          "path": "tobeimg/azGeRdgR0d4YMJgrF5DHigXd9QpG6Oih54siAHxAb8I/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9mMTlkZWIzOS0zMTMyLTRlYWMtOGU4MC03YjY1MDkyY2NlMTcuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "likesCount": 58
      },
      {
        "_id": "5b30f9a6bdb0a668e71f52a2",
        "title": "淫舞乱",
        "author": "SOLID AIR (ぞんだ)",
        "pagesCount": 19,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇"
        ],
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "tobeimg/VtUZQoklJ-PaKEGUwJCSbn4ADdQDTN268aep49_zc-s/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8zYzhlZGJmYS01ZGIxLTQ2ZmQtYTJjZC1lMGZlYWQwNTQ2N2QuanBn.jpg",
          "originalName": "000.jpg"
        },
        "likesCount": 267
      },
      {
        "_id": "60f7eb727b170248cbbfc765",
        "title": "マイクラ",
        "author": "YA-ZY (ゆにおし)",
        "pagesCount": 26,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "短篇",
          "同人"
        ],
        "thumb": {
          "originalName": "001.jpg",
          "path": "tobeimg/l6vU2JwMeoNmHS15M46utaERj32wNENdxGSkuaMC3q8/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9hZTBkMmU5OS0yNTI5LTQzNzctYjVmMy05Mzc2YTI3ZWQxMjguanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "likesCount": 65
      },
      {
        "_id": "5be100768f90c80cb9eb8142",
        "title": " Legend of Chun-Li Vol.2 (Street Fighter) 不知火舞无惨",
        "author": "chunlieater",
        "pagesCount": 25,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "全彩",
          "同人",
          "短篇",
          "重口地帶"
        ],
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "tobeimg/54R67mc5viWuL_oQOfIuHTZ6jIhzerwS8L7TEGx_h98/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8wMThlMGU1OC03N2NiLTQ3ZTgtYWE1Zi1kYzJjNWE0MTczYjkuanBn.jpg",
          "originalName": "1.jpg"
        },
        "likesCount": 54
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comics|[object]|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|
|»»» thumb|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»» author|string|true|none||none|
|»»» categories|[string]|true|none||none|
|»»» finished|boolean|true|none||none|
|»»» epsCount|integer|true|none||none|
|»»» pagesCount|integer|true|none||none|
|»»» likesCount|integer|true|none||none|

## POST （取消）点赞-本子

POST /comics/{comicId}/like

本子默认为未点赞，第一次调用为点赞，第二次为取消点赞

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |本子id|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "action": "like"
  }
}
```

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "action": "unlike"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» action|string|true|none||none|

## GET 获取章节图片

GET /comics/{comicId}/order/{order}/pages

获取对应漫画对应章节的图，还是分页的

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |none|
|order|path|string| 是 |本子的章节，默认从1开始|
|page|query|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "pages": {
      "docs": [
        {
          "_id": "58218b735f6b9a4f93e02a9d",
          "media": {
            "originalName": "1.jpg",
            "path": "9d73109c-e311-4a4c-a69c-4e7f7b9c735d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02a9d"
        },
        {
          "_id": "58218b735f6b9a4f93e02a9f",
          "media": {
            "originalName": "2.jpg",
            "path": "f9cfe31d-358b-4850-a518-c923f946affa.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02a9f"
        },
        {
          "_id": "58218b735f6b9a4f93e02aa1",
          "media": {
            "originalName": "3.jpg",
            "path": "45738767-f848-44d7-9959-2eaf3d59dd82.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aa1"
        },
        {
          "_id": "58218b735f6b9a4f93e02aa3",
          "media": {
            "originalName": "4.jpg",
            "path": "4a087cac-0eeb-43c7-a288-7b458953d30f.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aa3"
        },
        {
          "_id": "58218b735f6b9a4f93e02aa5",
          "media": {
            "originalName": "5.jpg",
            "path": "d14b82dc-80c3-4e04-98c6-3e9a03fdd246.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aa5"
        },
        {
          "_id": "58218b735f6b9a4f93e02aa7",
          "media": {
            "originalName": "6.jpg",
            "path": "8100c281-d863-4179-9de3-32f69abfcba5.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aa7"
        },
        {
          "_id": "58218b735f6b9a4f93e02aa9",
          "media": {
            "originalName": "7.jpg",
            "path": "f42d0e9b-c723-40fe-93e6-cef84d13745f.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aa9"
        },
        {
          "_id": "58218b735f6b9a4f93e02aab",
          "media": {
            "originalName": "8.jpg",
            "path": "1e980e2e-630c-4c34-9549-e1bc970361d2.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aab"
        },
        {
          "_id": "58218b735f6b9a4f93e02aad",
          "media": {
            "originalName": "9.jpg",
            "path": "fc96269f-d3b7-441e-955d-9e107983c38d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aad"
        },
        {
          "_id": "58218b735f6b9a4f93e02aaf",
          "media": {
            "originalName": "10.jpg",
            "path": "10c53c53-7129-4f22-bb81-5fe1afa6f1ff.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02aaf"
        },
        {
          "_id": "58218b735f6b9a4f93e02ab1",
          "media": {
            "originalName": "11.jpg",
            "path": "dd36443c-f33e-461d-96d5-2aa52fc21d69.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02ab1"
        },
        {
          "_id": "58218b735f6b9a4f93e02ab3",
          "media": {
            "originalName": "12.jpg",
            "path": "991bf71e-22f8-45ea-b420-d7a1b59ab494.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02ab3"
        },
        {
          "_id": "58218b735f6b9a4f93e02ab5",
          "media": {
            "originalName": "13.jpg",
            "path": "21603051-6a55-4185-a279-8b98bfd08235.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02ab5"
        },
        {
          "_id": "58218b735f6b9a4f93e02ab7",
          "media": {
            "originalName": "14.jpg",
            "path": "ab5c2172-4979-4e01-81c2-d1d6f50a2158.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02ab7"
        },
        {
          "_id": "58218b735f6b9a4f93e02ab9",
          "media": {
            "originalName": "15.jpg",
            "path": "00030dd0-c8df-44e1-97e3-ce7bb53623d5.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02ab9"
        },
        {
          "_id": "58218b735f6b9a4f93e02abb",
          "media": {
            "originalName": "16.jpg",
            "path": "6d82f062-6b72-40d6-acf2-da5bfad71d3b.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02abb"
        },
        {
          "_id": "58218b735f6b9a4f93e02abd",
          "media": {
            "originalName": "17.jpg",
            "path": "d8fa3e78-edc6-4ec8-8a42-db023bc3fbca.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02abd"
        },
        {
          "_id": "58218b735f6b9a4f93e02abf",
          "media": {
            "originalName": "18.jpg",
            "path": "577b1e9d-d918-468a-bea9-23f8812f3bd9.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02abf"
        },
        {
          "_id": "58218b735f6b9a4f93e02ac1",
          "media": {
            "originalName": "19.jpg",
            "path": "762ad4e5-856a-4f25-bbf4-8ce74220515e.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02ac1"
        },
        {
          "_id": "58218b735f6b9a4f93e02ac3",
          "media": {
            "originalName": "20.jpg",
            "path": "f233c0b1-0006-418c-88c8-3605f76762db.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "id": "58218b735f6b9a4f93e02ac3"
        }
      ],
      "total": 20,
      "limit": 40,
      "page": 1,
      "pages": 1
    },
    "ep": {
      "_id": "58218b735f6b9a4f93e02a9b",
      "title": "第1集"
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» pages|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» media|object|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»»» id|string|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» pages|integer|true|none||none|
|»» ep|object|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|

## GET 本子-排行榜

GET /comics/leaderboard

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|tt|query|string| 是 |时间类型，可选：   H24, D7,  D30|
|ct|query|string| 是 |不明确，VC|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comics": [
      {
        "_id": "62bfe3f32f2e9338c6593d1d",
        "title": "きて。 愛我。",
        "author": "ヘリを",
        "totalViews": 490261,
        "totalLikes": 10784,
        "pagesCount": 221,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇",
          "純愛",
          "單行本",
          "姐姐系",
          "妹妹系"
        ],
        "thumb": {
          "originalName": "風的工房003.jpg",
          "path": "tobeimg/czcL7qSSH92eoiGzhxzQXf0tK41iMnVvbezInqdzpe4/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvOWZjNGI3MGEtNDQ2ZC00NmY1LWJmMjgtNzliN2QwM2EyNzMzLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 490261,
        "leaderboardCount": 306596
      },
      {
        "_id": "62bccc5be2f5440c99db4244",
        "title": "[3D漫画]母亲的奇异系统1-5",
        "author": "听话的阿伟",
        "totalViews": 1288384,
        "totalLikes": 6823,
        "pagesCount": 557,
        "epsCount": 5,
        "finished": true,
        "categories": [
          "全彩",
          "長篇",
          "CG雜圖"
        ],
        "thumb": {
          "originalName": "006.jpg",
          "path": "tobeimg/B-mfAMtueKTrlX0WY0z6q2vm05aoCCQVqAQWCQxwOK0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvODU0ODkwNmItNDZkNS00MWY0LTk2YjMtZTY4NmI0ZmI0Mzc2LmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 1288384,
        "leaderboardCount": 215309
      },
      {
        "_id": "61e43fa6b93f6b06e931a80d",
        "title": " 全部君のせいだ。III [中国翻訳] [DL版]",
        "author": "毛玉牛乳 (玉之けだま)",
        "totalViews": 1834253,
        "totalLikes": 26089,
        "pagesCount": 96,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇",
          "妹妹系",
          "非人類"
        ],
        "thumb": {
          "originalName": "01__001.jpg",
          "path": "tobeimg/jCDIyVo-SDtK7z0zKB4L7WnUGQFg4Y8UB6doyEK6jQY/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy84NzU4NTM0MS00ZjQ0LTRlYzctYTNjNS1jNzEyYzZmZWU5NjguanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "viewsCount": 1834253,
        "leaderboardCount": 205800
      },
      {
        "_id": "62387f93c4ccd45efce0e9b5",
        "title": "Re：從零開始的NTR生活",
        "author": "墨雪吟",
        "totalViews": 1652467,
        "totalLikes": 20576,
        "pagesCount": 518,
        "epsCount": 5,
        "finished": true,
        "categories": [
          "全彩",
          "CG雜圖",
          "同人",
          "NTR",
          "強暴"
        ],
        "thumb": {
          "fileServer": "https://storage-b.picacomic.com",
          "path": "tobeimg/UYCqa_Jwzl3dLQeSPqxEXZsHuCMCcsl82xZLzbtTOH0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMWIwNjQyMWItMzE1Mi00ZjFjLWFmYWYtYjA3MzNlMGJmMjZjLmpwZw.jpg",
          "originalName": "117.jpg"
        },
        "viewsCount": 1652467,
        "leaderboardCount": 161750
      },
      {
        "_id": "62c237abd00dc631c28736f9",
        "title": "ダメな男に優しいエルフ漫画",
        "author": "けけもつ",
        "totalViews": 174694,
        "totalLikes": 3828,
        "pagesCount": 42,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "CG雜圖",
          "全彩",
          "短篇"
        ],
        "thumb": {
          "originalName": "01_0.cover.jpg",
          "path": "tobeimg/Z_xzyRTlvYvJWTZiByeEbES4SJuRiEC8oMgQruMK5SY/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvY2IxZDhlZGYtYjhkYi00NTk2LThkOGEtMzNlOWI3MGQ1ZGJhLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 174694,
        "leaderboardCount": 150191
      },
      {
        "_id": "62bcca1fb0d3dc60dfea7dc7",
        "title": "この恋に気づいて 這份戀情望你察覺 特裝版",
        "author": "だにまる",
        "totalViews": 424666,
        "totalLikes": 8934,
        "pagesCount": 231,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇",
          "純愛",
          "姐姐系",
          "妹妹系",
          "後宮閃光",
          "單行本"
        ],
        "thumb": {
          "fileServer": "https://storage-b.picacomic.com",
          "path": "tobeimg/whpeOPVLfLr9Na_Wrf3r7AJqibS-GMsU47t34Z_0zzU/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvNjk4MTRlY2EtODBiNS00YjU5LWJjZjgtZTAyNWIwMmMzOTA2LmpwZw.jpg",
          "originalName": "風的工房003.jpg"
        },
        "viewsCount": 424666,
        "leaderboardCount": 128332
      },
      {
        "_id": "62c1cd5cbec00f31d3b97b73",
        "title": "[3D]NPC  (1-3)",
        "author": "炸鸡好好吃",
        "totalViews": 178010,
        "totalLikes": 770,
        "pagesCount": 310,
        "epsCount": 3,
        "finished": false,
        "categories": [
          "全彩",
          "長篇",
          "CG雜圖",
          "強暴",
          "人妻"
        ],
        "thumb": {
          "fileServer": "https://storage-b.picacomic.com",
          "path": "tobeimg/9CaK4kHmBxK1ieEEqCEuDH3smBO32_YidS0WJPFFk1U/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvOTBiMjI2MTMtMTMwZC00OGI2LTlkNzMtM2ViY2M3MTgzZjM1LmpwZw.jpg",
          "originalName": "070.jpg"
        },
        "viewsCount": 178010,
        "leaderboardCount": 108351
      },
      {
        "_id": "619dde41f9cd94370e57c70f",
        "title": "[Pixiv] 楓 | sayappa (2351786) (5216772) (658949)",
        "author": "楓 | sayappa",
        "totalViews": 309552,
        "totalLikes": 5114,
        "pagesCount": 146,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "全彩",
          "同人",
          "CG雜圖",
          "生肉"
        ],
        "thumb": {
          "originalName": "020__dragon_quest_and_1_more_drawn_by_kaede_sayappa_f11c981ab17707e105dd84be58df5d73.jpg",
          "path": "tobeimg/qe7tR8_9FPp1FX83giIrD-okrNFPQQpVCg76UECDBxA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9lNDFiOGFiMS1kODc5LTRmMzUtOGJiMS0zYWI2MzFlMDg2NDUuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "viewsCount": 309552,
        "leaderboardCount": 95938
      },
      {
        "_id": "62bfec3608fff42c1ca6a85c",
        "title": "催眠アプリver666～真夏のビーチで水着美女をご馳走様!～2",
        "author": "BLACK SMILE",
        "totalViews": 246405,
        "totalLikes": 983,
        "pagesCount": 287,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "全彩",
          "長篇",
          "CG雜圖"
        ],
        "thumb": {
          "originalName": "00-00(01).jpg",
          "path": "tobeimg/iLQsgtGISyQHt3qL79b5le1Wnd6Za1H2dPin7rrLq7o/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvZTNmYWQyYmItYzkxOC00NDJlLWI1OWMtMDRkN2E5YWE4ZTEyLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 246405,
        "leaderboardCount": 90164
      },
      {
        "_id": "5ac1a953bc0ace1e6c18d079",
        "title": "玩具 ",
        "author": "aki99",
        "pagesCount": 100,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "全彩",
          "同人",
          "CG雜圖",
          "妹妹系"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/Qu5T9_tYjA-w3oPTwFBjKX3L8tn105w5AisCalK3RPs/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy80ZDQzYTcxZC1iMzRhLTRlNTQtYWMwOS04Y2YyNGI2MzA2MTIuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalLikes": 74917,
        "totalViews": 4174849,
        "viewsCount": 4174849,
        "leaderboardCount": 80015
      },
      {
        "_id": "62ba1c5e9b79557448761b20",
        "title": "高評価よろしくお願いします",
        "author": "クレスタ (呉マサヒロ)",
        "totalViews": 1008100,
        "totalLikes": 10274,
        "pagesCount": 48,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "全彩"
        ],
        "thumb": {
          "fileServer": "https://storage-b.picacomic.com",
          "path": "tobeimg/eJJbTFx6zsnMRPOz4rPJMAai0kaAnJ5YBqRIbzjLiHg/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMDQ1NGFlNGMtNTdkYy00NzNiLTkxM2UtNzcxYjE2NjQ4YWNiLmpwZw.jpg",
          "originalName": "001.jpg"
        },
        "viewsCount": 1008100,
        "leaderboardCount": 77172
      },
      {
        "_id": "62bf14aae2f5440c99db635a",
        "title": "ハチドリの楽園",
        "author": "はらぺこ定食 (すえゆう)",
        "totalViews": 319068,
        "totalLikes": 1628,
        "pagesCount": 116,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "全彩",
          "長篇",
          "NTR",
          "強暴"
        ],
        "thumb": {
          "originalName": "d_101999pr.jpg",
          "path": "tobeimg/bGf84xn10-KBbm_NFqhi1hGu2pZLAXwO5TbGUXTQWKI/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvYWI5MjFiZTEtZWMxMC00NzUyLWFjMWItMDgzNDM5MGE1ZTNlLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 319068,
        "leaderboardCount": 71984
      },
      {
        "_id": "62bfe20ee2f5440c99db6faa",
        "title": "会社のリラクゼーションルームでドスケベサービスしてくれる爆乳上司",
        "author": "NYPAON",
        "totalViews": 134096,
        "totalLikes": 1740,
        "pagesCount": 52,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "全彩"
        ],
        "thumb": {
          "originalName": "relaxation_001.jpg",
          "path": "tobeimg/ZfQpgI8nTlVCgSHwxaWQ53hLkBBU3iSDSmmUo_PHouY/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvM2Q0OGIzMTctOTkxZi00ZGQyLThhN2EtNzI2MjJkYTgwYThhLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 134096,
        "leaderboardCount": 65719
      },
      {
        "_id": "62c006c02f2e9338c659419d",
        "title": "perro的直播事故",
        "author": "DAGASI",
        "totalViews": 175318,
        "totalLikes": 826,
        "pagesCount": 15,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "全彩",
          "偽娘哲學",
          "非人類",
          "CG雜圖"
        ],
        "thumb": {
          "originalName": "0.jpg",
          "path": "tobeimg/8mD1FIxSokwnByo_ecaYq-LnX0wt2zMXHhHC-brxeHw/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvNDRkNzBiMGUtZjk2MC00N2Q3LWJjMDAtZTVmNWYzOGYzY2RhLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 175318,
        "leaderboardCount": 62511
      },
      {
        "_id": "62c1cd00bec00f31d3b97b23",
        "title": "[3D]荒野女尸",
        "author": "炸鸡好好吃",
        "totalViews": 99929,
        "totalLikes": 261,
        "pagesCount": 130,
        "epsCount": 2,
        "finished": false,
        "categories": [
          "全彩",
          "長篇",
          "CG雜圖",
          "強暴"
        ],
        "thumb": {
          "fileServer": "https://storage-b.picacomic.com",
          "path": "tobeimg/sZRq0wB8OjzeRw-WX__bzXw8GU7mj6mRQyArd0taEL4/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvYjIxYWQyNDQtNGI0Zi00YjQ5LThhOTUtNmVmN2UxYTc4ZGQ0LmpwZw.jpg",
          "originalName": "062.jpg"
        },
        "viewsCount": 99929,
        "leaderboardCount": 62379
      },
      {
        "_id": "62b8b713b0d3dc60dfea2d43",
        "title": " 티바트의 암컷 완성 (原神) [中国翻訳]",
        "author": "hellaP",
        "totalViews": 1179783,
        "totalLikes": 5700,
        "pagesCount": 119,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "全彩",
          "長篇",
          "同人",
          "CG雜圖",
          "姐姐系"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/2KpzreDWjgmHFJTIpHVkaFdjuXzCEVuyQ550smUg3Xk/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvZWU2Mzc0ODEtNDk3Ny00YWYwLTk5ZWUtZDM5OWQwNmI0YjgwLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 1179783,
        "leaderboardCount": 61935
      },
      {
        "_id": "60e2d493525a404c58db1d33",
        "title": " 人付き合いが苦手な未亡人の雪女さんと呪いの指輪 [中国翻訳]",
        "author": "ぷぅのぷぅぷぅぷぅ (ぷぅ崎ぷぅ奈)",
        "totalViews": 9777250,
        "totalLikes": 233944,
        "pagesCount": 77,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "全彩",
          "長篇",
          "人妻",
          "非人類"
        ],
        "thumb": {
          "originalName": "01_01.jpg",
          "path": "tobeimg/l-xdepKUxT3CiWer7R_x1kynTqjwf1_YOJn2LPOhHtA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy80ZDg1YzQ0Ni1hMWRhLTQyNTItYjkyNS0xZmZmYTBkMGFjZDAuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "viewsCount": 9777250,
        "leaderboardCount": 57204
      },
      {
        "_id": "5dadd3c77394494d9c9d0a40",
        "title": "邻家三姐妹/邻居的逆袭 补档",
        "author": "Rodong",
        "totalViews": 3475512,
        "totalLikes": 29734,
        "pagesCount": 1197,
        "epsCount": 20,
        "finished": true,
        "categories": [
          "全彩",
          "長篇",
          "妹妹系",
          "WEBTOON"
        ],
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "tobeimg/ol0hUkmKdPLajYRXWxA6_6hTLC-_5ffxxGDUtdSgtVQ/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9jMjNkYWEyMy0yNmYxLTQ1NTktOTg4ZC0xZmM1NGZlODgxY2MucG5n.png",
          "originalName": "QQ图片20191021184318.png"
        },
        "viewsCount": 3475512,
        "leaderboardCount": 56077
      },
      {
        "_id": "5ccb04083478850224b4da84",
        "title": "美丽新世界",
        "author": "高孙志/伊坤志",
        "pagesCount": 5007,
        "epsCount": 67,
        "finished": false,
        "categories": [
          "全彩",
          "長篇",
          "WEBTOON"
        ],
        "thumb": {
          "fileServer": "https://storage-b.picacomic.com",
          "path": "tobeimg/o4SBOU8frOEPCOFmMJ7sVXTcGA-Ebu3Ov_NVyX-r8Qo/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvNDgwYjUzY2YtMzdlNS00OTI2LTgyZDgtYzIwYzVkMDY3ZTdhLmpwZw.jpg",
          "originalName": "11.jpg"
        },
        "totalLikes": 211169,
        "totalViews": 38218445,
        "viewsCount": 38218445,
        "leaderboardCount": 55451
      },
      {
        "_id": "62c00e7e2f2e9338c65943d5",
        "title": "  淫猥調教 フィットネス (ANGEL 倶楽部 2021年9月号)",
        "author": "Chin",
        "totalViews": 134857,
        "totalLikes": 1052,
        "pagesCount": 23,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "NTR",
          "人妻"
        ],
        "thumb": {
          "originalName": "ANGELclub2109_P025.jpg",
          "path": "tobeimg/YtEzvSkDaexlW5Zbvc3bAT1x8PvE37S-j7vL6O1s6L0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMWE4NTA0MjktYWM4Mi00ZWY0LTljZGYtYjBlMWIxMTUzYTEwLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 134857,
        "leaderboardCount": 51773
      },
      {
        "_id": "62bcc6e49b79557448764519",
        "title": "今宵、亜人はいかがでしょうか？ [中国翻訳] [DL版]",
        "author": "Jun",
        "totalViews": 339947,
        "totalLikes": 2393,
        "pagesCount": 99,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇",
          "非人類"
        ],
        "thumb": {
          "originalName": "001(hyoushi).jpg",
          "path": "tobeimg/xKcWvCCn2zjRhZuTDfMsR8ZANMJBASzZGfdlL_GnqaY/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvOTA5Y2E2MTctYWFlNC00MTQwLTgzMzctNTQxYjcxMTE5M2FiLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 339947,
        "leaderboardCount": 51735
      },
      {
        "_id": "60143110f8d9774a09d73556",
        "title": "弟の性欲処理は、姉がするものだと お義姉ちゃんは思っている。 | 弟弟的性慾處理是姊姊的義務，我的繼姊覺得這樣理所當然。",
        "author": "真・聖堂☆本舗 (聖☆司)",
        "totalViews": 327810,
        "totalLikes": 4502,
        "pagesCount": 28,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "姐姐系",
          "短篇"
        ],
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "tobeimg/d0-PLKaY1Bgm9lqCaELFZ12gdhfcBBH3_pIrhqucgQA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy84MDYzYjQyNC1hODBiLTQ2YmEtYjIwNi0wODU3MGYzYWU5YjYuanBn.jpg",
          "originalName": "001.jpg"
        },
        "viewsCount": 327810,
        "leaderboardCount": 50984
      },
      {
        "_id": "61744d63cd4f5e07179598c7",
        "title": "人偶的复仇·稻妻沦陷",
        "author": "MaskWolf（KeinV）",
        "totalViews": 360725,
        "totalLikes": 2959,
        "pagesCount": 117,
        "epsCount": 16,
        "finished": true,
        "categories": [
          "同人",
          "強暴",
          "長篇"
        ],
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "tobeimg/ftFp1hyktpj1DMmXCGVSjN0yFTBOnT-cea3GOZe7IbA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy85MGM0MTA0OC00ZmVkLTQxODEtYWViNC02YzZhOGE5OGU1NDMuanBn.jpg",
          "originalName": "0.jpg"
        },
        "viewsCount": 360725,
        "leaderboardCount": 47518
      },
      {
        "_id": "627ca33a75ab703dacb84cc1",
        "title": "疫情期間的家教生活（更新至10话）",
        "author": "LObeam,Rodong",
        "totalViews": 5034318,
        "totalLikes": 38114,
        "pagesCount": 1583,
        "epsCount": 5,
        "finished": false,
        "categories": [
          "全彩",
          "長篇",
          "WEBTOON"
        ],
        "thumb": {
          "fileServer": "https://storage-b.picacomic.com",
          "path": "tobeimg/WCCggkyb8oqUMNWv4iQgAGd1wl4998qlAIVOGKdgzXQ/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvYWM1M2MxNGYtZTVkOC00ODc3LTk1NGItN2MyZDVjN2VlMWMwLmpwZw.jpg",
          "originalName": "cover.jpg"
        },
        "viewsCount": 5034318,
        "leaderboardCount": 45727
      },
      {
        "_id": "62c238a4d00dc631c2873740",
        "title": "血は蜜よりも甘く/血甘于蜜",
        "author": "アクアドロップ (三上ミカ)",
        "totalViews": 46772,
        "totalLikes": 1014,
        "pagesCount": 61,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇",
          "純愛",
          "妹妹系"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/pcNQkg9CLOgp1aZaQM77MWrxVXKBckGFbkqIBVJxm24/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvNzFmOWY4MzAtYWY4ZS00NzQ5LThlYWYtYmZkYmJhZjdlOGRlLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 46772,
        "leaderboardCount": 43125
      },
      {
        "_id": "62c237ce1e024212b9a525fd",
        "title": "まわしぐいクリームパフ | 旋转的奶油泡芙",
        "author": "処庶所フロンティア (お茶)",
        "totalViews": 35119,
        "totalLikes": 758,
        "pagesCount": 52,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "耽美花園"
        ],
        "thumb": {
          "originalName": "01__1.jpg",
          "path": "tobeimg/yAHeQrU8k59XdjekkUkWYy2lYdOYvwCodcqQpBoBE2I/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMjgyYzM4NjYtMDIxNi00ZDZlLWI0ZTEtOGFjZGM0ZTQyNmJiLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 35119,
        "leaderboardCount": 41594
      },
      {
        "_id": "62c1c545d00dc631c2872bd9",
        "title": "とある夫婦の性事情 (COMIC BAVEL 2022年8月号)",
        "author": "魚山ケイジ",
        "totalViews": 61057,
        "totalLikes": 352,
        "pagesCount": 22,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "SM",
          "人妻",
          "NTR",
          "強暴"
        ],
        "thumb": {
          "originalName": "001.jpg",
          "path": "tobeimg/vldUALgIVLwvuNFudTpfPdXPIv8YJceYTtK0qcPx4kE/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvZTY1MjVkNjktNDc1NC00MDRlLThlMWItMjIyNTUzYjllOWMzLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 61057,
        "leaderboardCount": 40105
      },
      {
        "_id": "62c239e80ae0b712cad16390",
        "title": "[Pixiv]春菊天うどん(5921803)",
        "author": "春菊天うどん",
        "totalViews": 43224,
        "totalLikes": 459,
        "pagesCount": 89,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "全彩",
          "同人",
          "CG雜圖"
        ],
        "thumb": {
          "originalName": "08__.jpg",
          "path": "tobeimg/0UuJNHiEjpIG1_kbFoOUPbRWtJbX4yazkNXSvgRdu_s/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMTk4M2IyM2MtYTZiNi00ODkzLTlmNWItNTVhNmFlYjdkMzZiLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 43224,
        "leaderboardCount": 40014
      },
      {
        "_id": "62bb7061b0d3dc60dfea677d",
        "title": "  搾精魔女",
        "author": "シロシロシロップ (もず)",
        "totalViews": 346254,
        "totalLikes": 4438,
        "pagesCount": 54,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "純愛"
        ],
        "thumb": {
          "originalName": "000.jpg",
          "path": "tobeimg/KMKqLqeCE83tiIqCFtbccui19g2Yk73HHhYu1n2F9O0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMmM0MjE5MGYtMmJhMC00OTY4LTk3N2UtNjJmOTE1NzU1YTJmLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 346254,
        "leaderboardCount": 39784
      },
      {
        "_id": "62bb6fb82f2e9338c658fd5c",
        "title": "欲情劣情発情も地脈異常のうち? (原神)",
        "author": "脳内補完 (k.kうさこ)",
        "totalViews": 192368,
        "totalLikes": 11939,
        "pagesCount": 36,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "短篇",
          "同人",
          "耽美花園"
        ],
        "thumb": {
          "originalName": "00000001.jpg",
          "path": "tobeimg/WqhOZsBRxrpCyFEqtSyhYbULaUusrC9twtVM1PgCTNw/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMmM0NmZiMDItOTM4Yy00ZTE3LThkNTYtYjkzYWFlNjQyZmYwLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 192368,
        "leaderboardCount": 39252
      },
      {
        "_id": "62bfe22fb0d3dc60dfeaa87a",
        "title": " センセイトラレ~欲するカラダ~ [中国翻訳]",
        "author": "三崎 (猫サム雷)",
        "totalViews": 102152,
        "totalLikes": 727,
        "pagesCount": 60,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "人妻",
          "NTR"
        ],
        "thumb": {
          "originalName": "hnbn_000.jpg",
          "path": "tobeimg/pe1LWhrIYykEEm0JlTC9UopnO3im3_T68lSAi0XGFg0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvM2VmNjhjMjMtYWJjZS00NTkxLThlZDQtNGQ4NmY0NTI2MjljLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 102152,
        "leaderboardCount": 39083
      },
      {
        "_id": "629b025524152317f0486c00",
        "title": "My Mother [中国翻訳]",
        "author": "XTER",
        "totalViews": 3674480,
        "totalLikes": 36337,
        "pagesCount": 100,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇",
          "人妻"
        ],
        "thumb": {
          "originalName": "000.jpg",
          "path": "tobeimg/UNGa6IUTNHySriDpzE94E49aK35uXz2TW5DmsrfFxl0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvZDdiZTc1MmEtMDg1OC00MjViLWIzOTItNjE4NmQ1OGZhN2Y5LmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 3674480,
        "leaderboardCount": 37862
      },
      {
        "_id": "62b693865eef367437a36b87",
        "title": "漫画#ゲームと彼女",
        "author": "富士やま",
        "totalViews": 587934,
        "totalLikes": 10937,
        "pagesCount": 53,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/TYJ1Az82R_eAkRz8hdmvzS-wnp7EjqDzaPn6AEx_2ZE/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvZTI1ZjA5ZTMtZjM5MC00M2ZlLWIyYTMtYmRkMTBhZGI1ZDc5LmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 587934,
        "leaderboardCount": 37840
      },
      {
        "_id": "5fe0c1b559b287406e2429e2",
        "title": "莫娜",
        "author": "ctrlz77",
        "totalViews": 3465493,
        "totalLikes": 46292,
        "pagesCount": 1460,
        "epsCount": 17,
        "finished": true,
        "categories": [
          "全彩",
          "同人",
          "CG雜圖",
          "姐姐系",
          "足の恋",
          "長篇"
        ],
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "tobeimg/npZTP_-CC0kcDzf3NV0pWeP6vNzt8gFWKGwY_AbobtU/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8zNTNkMWUyYS1mY2E0LTRmYmQtYjBiMC1lYmQ4MWRjNjg3ZjcuanBn.jpg",
          "originalName": "86428068_p0_.jpg"
        },
        "viewsCount": 3465493,
        "leaderboardCount": 37770
      },
      {
        "_id": "62c1cfc0bec00f31d3b97d7f",
        "title": "らぶりー♡",
        "author": "きょくちょ",
        "totalViews": 46014,
        "totalLikes": 855,
        "pagesCount": 204,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "長篇",
          "單行本"
        ],
        "thumb": {
          "originalName": "001__00.jpg",
          "path": "tobeimg/6ZlCy58umbx5CS1CY_V1b62AKJAARe2nlsa3y6Jlg4w/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMzQ4MzNmMDktNTI3MS00YzJiLWEzZjAtMWFlODNlZmNlNDMyLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 46014,
        "leaderboardCount": 36341
      },
      {
        "_id": "62bb71f99b795574487631ab",
        "title": "[Pixiv] Leevan (47042747)",
        "author": "Leevan",
        "totalViews": 375261,
        "totalLikes": 683,
        "pagesCount": 113,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "全彩",
          "同人",
          "CG雜圖"
        ],
        "thumb": {
          "originalName": "96182457_p0.jpg",
          "path": "tobeimg/uGJebwzidGV8QOmjrFAr1DvY_8sv8pvyzCC1Y_l-WME/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvYWVhYTQxZjctMDg3YS00NTNjLWI2MTYtZGYwNmViM2MzMzQ4LmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 375261,
        "leaderboardCount": 36083
      },
      {
        "_id": "62c1b725bec00f31d3b96f8c",
        "title": "チェシャーちゃん",
        "author": "林檎蜜紀",
        "totalViews": 64899,
        "totalLikes": 214,
        "pagesCount": 86,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "Cosplay"
        ],
        "thumb": {
          "originalName": "60.jpg",
          "path": "tobeimg/UFf9OizC5F76nyS5RAGMFUM47G3Uf-ABdVClQWpEvNM/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMDJmM2JmNmYtOWY0Zi00ZjVlLTlhMmYtNTc0ZDVhNDQyNjYzLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 64899,
        "leaderboardCount": 34033
      },
      {
        "_id": "62c1b5812f2e9338c6595aba",
        "title": " 近所の人妻さん「由美さん」 (オリジナル)[中国翻訳]",
        "author": "桜の灯る日へ",
        "totalViews": 59826,
        "totalLikes": 360,
        "pagesCount": 18,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "人妻",
          "NTR"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/bDNKpX9fGbA7eQafRnYZDb2ysUV0IYgqarITeU3K93U/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMDc0Y2RkODAtZGI2ZC00OTBhLTgyZGEtMzRjMDJhMjhmOGM5LmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 59826,
        "leaderboardCount": 33598
      },
      {
        "_id": "62c239010ae0b712cad1637b",
        "title": " 夜蘭, ミステリーな彼女 (原神) [中国翻訳]",
        "author": "ZB",
        "totalViews": 40066,
        "totalLikes": 202,
        "pagesCount": 11,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇",
          "全彩",
          "同人",
          "CG雜圖"
        ],
        "thumb": {
          "originalName": "000 (1).jpg",
          "path": "tobeimg/oFtmktuLiRnONQqde_qUXG6G6tXv9LKqJKZ9W_8jAjQ/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvMWM3MDc4N2UtY2ZjOC00ZjE5LTg3ZDktMTRhY2ZmMGYwMjFmLmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 40066,
        "leaderboardCount": 33512
      },
      {
        "_id": "62c1ce18bec00f31d3b97d09",
        "title": "  風紀委員 一条の敗北 (Comic G-Es 01) [中国翻訳]",
        "author": "なしぱすた",
        "totalViews": 47936,
        "totalLikes": 606,
        "pagesCount": 36,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇"
        ],
        "thumb": {
          "originalName": "148.jpg",
          "path": "tobeimg/iFERnqOgWGQo7FRwHVm_ISF1P2GtZcHf-K9IFWx94qc/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlLWIucGljYWNvbWljLmNvbS9zdGF0aWMvNzhkMTQ2OGQtMjEyZi00NDAzLThhOWQtNmVkZTU4YTNhYjM1LmpwZw.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "viewsCount": 47936,
        "leaderboardCount": 33241
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comics|[object]|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|
|»»» author|string|true|none||none|
|»»» totalViews|integer|true|none||none|
|»»» totalLikes|integer|true|none||none|
|»»» pagesCount|integer|true|none||none|
|»»» epsCount|integer|true|none||none|
|»»» finished|boolean|true|none||none|
|»»» categories|[string]|true|none||none|
|»»» thumb|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»» viewsCount|integer|true|none||none|
|»»» leaderboardCount|integer|true|none||none|

## GET 骑士-排行榜

GET /comics/knight-leaderboard

是发本子数量的排行榜

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "users": [
      {
        "_id": "593019d53f532059f297efa7",
        "gender": "m",
        "name": "黎欧",
        "slogan": "二八七六八七八三九二（QQ代传邮箱，请标注来意不然我只能无视了 。来私自要本的还请歇歇吧，我不会提供转售服务。）代传传的，如果急着要上的说一声。好友申请太多很难做到一一回复，如果是想要找新桥委托的请去联络三三八六九二六八四四。",
        "title": "萌新",
        "verified": false,
        "exp": 3039682,
        "level": 174,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "0dd4edbe-58c8-4814-ab01-e191190618c8.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 21090,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "58f649a80a48790773c7017c",
        "gender": "m",
        "name": "复活的炎头队长",
        "slogan": "斯麦路 斯麦路",
        "title": "那位大人",
        "verified": false,
        "exp": 2329181,
        "level": 153,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "6d593be8-3864-4ec8-8eba-3dcd0f096b06.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 17041,
        "character": "https://pica-web.wakamoment.tk/special/frame-317.png"
      },
      {
        "_id": "582bdf31d415f35949352640",
        "gender": "bot",
        "name": "騎士ACE",
        "title": "請稱呼我本子大師",
        "verified": false,
        "exp": 707002,
        "level": 84,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "3f73175b-e2e1-4fe0-a401-e6afaaf29e45.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 3001,
        "character": "https://wikawika.xyz/characters/frame_knight_1000.png?r=3"
      },
      {
        "_id": "594ca21839ed97286c18afe5",
        "gender": "m",
        "name": "KevinG",
        "slogan": "我只是个兴趣使然的骑士",
        "title": "巨佬",
        "verified": false,
        "exp": 342672,
        "level": 59,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "eb4f77f2-21ed-4118-bc75-ada619fb4718.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 2366,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5893830fc2c0f62acdf4fe30",
        "gender": "m",
        "name": "樱庭莲",
        "slogan": "代传骑士，陈睿站同名同图像直接私信，声明代传无偿，同性趣女友募集中，下千本种，传千部本，看万本漫，品万部本",
        "title": "樱庭骑士莲酱",
        "verified": false,
        "exp": 2079831,
        "level": 144,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "e58b5daf-154d-4e38-83e9-b379ce4633c5.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 2299,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "594d1d1a8a452814b577c033",
        "gender": "bot",
        "name": "Atheist",
        "slogan": "頭像是彼之初的男主—黑羽\n第八集1分57秒的截圖🥰😘",
        "title": "我",
        "verified": false,
        "exp": 509623,
        "level": 71,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "122b62c3-78cd-4dac-b8ce-3fc3860dcbc5.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 2296,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "582fdbcf477e549a07e49268",
        "gender": "bot",
        "name": "匿名12785",
        "slogan": "《刺杀骑士团长》——村上春树",
        "title": "歷戰的騎士",
        "verified": false,
        "exp": 280375,
        "level": 53,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "9bf94d10-7a91-44be-9780-987c4054c722.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 1870,
        "character": "https://wikawika.xyz/characters/frame_knight_1000.png?r=3"
      },
      {
        "_id": "58330478128c4b6872013cb4",
        "gender": "bot",
        "name": "嗶咔機器人",
        "title": "我是嗶咔性感美女",
        "verified": false,
        "exp": 45724,
        "level": 21,
        "characters": [
          "knight",
          "reviewer",
          "official"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "tobs/e120f856-cfb6-4547-9da4-3a472c0b6ecf.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "comicsUploaded": 1665,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "586749fd52120370432ce37d",
        "gender": "bot",
        "name": "Ancient Sunset",
        "slogan": "我对区区人类没什么兴趣。\n活着的东西非常恶心。\n不过，如果你坚持的话，我还是愿意以死亡为前提陪你的哦？",
        "title": "艾蕾",
        "verified": false,
        "exp": 590843,
        "level": 77,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "4eea0c12-3fe9-4abf-ac19-99a9c003f993.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 1592,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "5a3fbd2fd86a4856cd11c635",
        "name": "嗶咔魔王",
        "gender": "bot",
        "slogan": "😈👿👹👺💀☠️👻👽👾",
        "title": "我是可愛的魔王",
        "verified": true,
        "exp": 3915,
        "level": 6,
        "characters": [
          "knight",
          "official"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "4a8a0c3b-d03b-4583-8315-927f3bfa4e02.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 1588,
        "character": "https://wikawika.xyz/characters/verified.png?r=3"
      },
      {
        "_id": "582995d32cff435850358afa",
        "gender": "bot",
        "name": "機器人wore",
        "slogan": "欢迎各位~\n希望各位能多多评论呀！\n虽然不怎么上聊天室，但是也欢迎聊天的毒毒",
        "title": "简介写的棒棒的大佬",
        "verified": false,
        "exp": 156982,
        "level": 40,
        "characters": [
          "knight",
          "chinese"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "c22db0c7-d0ef-4db7-afbe-a4e5929a9843.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 1288,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "584047e378dbcfd266401bd9",
        "gender": "m",
        "name": "幻想乡丶八云墨",
        "slogan": "行走在希望与绝望之间",
        "title": "一方通行",
        "verified": false,
        "exp": 424370,
        "level": 65,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "c9c81dcd-abb9-4de7-a71b-056f616f337f.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 1281,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5829a0001cc00b5d50b1b9dd",
        "gender": "m",
        "name": "女騎士",
        "slogan": "我TMD就是一个过气的老骑士",
        "title": "嗶咔過氣老騎士",
        "verified": false,
        "exp": 144206,
        "level": 38,
        "characters": [
          "knight",
          "chinese"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "9671d527-d5e2-436a-8e5d-2342ce6fa997.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 1239,
        "character": "https://wikawika.xyz/characters/frame_knight_1000.png?r=3"
      },
      {
        "_id": "58ddf5bb6d75d74afc8951da",
        "name": "嗶咔便秘少女匹匹",
        "gender": "f",
        "slogan": "我有時候女了",
        "title": "AI",
        "verified": true,
        "exp": 214219,
        "level": 46,
        "characters": [
          "knight",
          "official"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "4aa22f39-f30e-4827-b438-76c31ce37f86.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 1217,
        "character": "https://wikawika.xyz/characters/verified.png?r=3"
      },
      {
        "_id": "5888124d91fbda3b379eb156",
        "name": "嗶咔惡魔3a",
        "gender": "bot",
        "slogan": "\n\n",
        "title": "我还是想一直陪在你身边",
        "verified": true,
        "exp": 4392,
        "level": 7,
        "characters": [
          "knight",
          "official"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "864a8c0f-6778-46c8-9856-b41719b80f7c.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 1168,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "582997ff1cc00b5d50b1b884",
        "gender": "m",
        "name": "童话汉化组名户用",
        "slogan": "百级休息了，大部分只更单行本",
        "title": "假萌新",
        "verified": false,
        "exp": 1010395,
        "level": 101,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "89173fc7-cce7-4957-b465-c9c9f5550756.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 957,
        "character": "https://wikawika.xyz/characters/frame_knight_500_999.png?r=3"
      },
      {
        "_id": "58c7dfb88ef9ed79ab390bee",
        "gender": "bot",
        "name": "我永远喜欢海棠零！",
        "slogan": "真遥",
        "title": "你是什么粉？",
        "verified": false,
        "exp": 332171,
        "level": 58,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "tobs/2f0d5e85-baa0-4a53-bbcc-f99caea47350.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "comicsUploaded": 839,
        "character": "https://pica-web.wakamoment.tk/special/frame-446.png"
      },
      {
        "_id": "58a1a078ef602472848416d5",
        "gender": "m",
        "name": "周大毛",
        "slogan": "別看了 吻我",
        "title": "金針菇男孩",
        "verified": false,
        "exp": 134377,
        "level": 37,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "ae0870a0-eab8-4d9a-9a9a-7c7cc3b7ea09.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 830,
        "character": "https://wikawika.xyz/characters/frame_knight_500_999.png?r=3"
      },
      {
        "_id": "5835b5c17e6d48ce7206576e",
        "gender": "f",
        "name": "喵铃酱",
        "slogan": "睡眠不足(＿´Д｀)",
        "title": "萌新",
        "verified": false,
        "exp": 70059,
        "level": 26,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "e487db6d-6374-4324-8884-a93ad1d26417.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 807,
        "character": "https://pica-web.wakamoment.tk/images/halloween_f.png"
      },
      {
        "_id": "5b29d57053dd326094aedb1f",
        "gender": "bot",
        "name": "月色朦朧",
        "slogan": "月色推薦必屬佳片~！！！",
        "title": "萌新",
        "verified": false,
        "exp": 511311,
        "level": 72,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "9b1fb674-a001-48b3-a0ad-f5a6e1d408b9.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 775,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "584bc87021230b7f03a1343a",
        "gender": "m",
        "name": "空条承太郎★",
        "slogan": "代传可发送至：②⑨⑤④⑨⑤⑧⑦⑦⑧@qq  . com\n需要标上：作者 漫画名 汉化组名 代传者名（或匿名）\n侵权下架问题也请邮件联系。",
        "title": "我又可以了",
        "verified": false,
        "exp": 258769,
        "level": 51,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "1be5d80f-cb40-4e69-a416-06b70ab2cf9a.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 697,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "58298f4f2cff4358503589c1",
        "gender": "bot",
        "name": "小 6",
        "title": "萌新",
        "verified": false,
        "exp": 293358,
        "level": 54,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "59c37cc9-c396-43c7-8a15-56798b03b8a7.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 605,
        "character": "https://wikawika.xyz/characters/frame_knight_500_999.png?r=3"
      },
      {
        "_id": "583647067e6d48ce72065c37",
        "gender": "m",
        "name": "kirakiracat",
        "title": "萌新",
        "verified": false,
        "exp": 42915,
        "level": 21,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "724f7430-3f8c-4a48-b8fb-616bb446efbd.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 568,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5837be7bd26d42fb087eef35",
        "gender": "f",
        "name": "天才美少女安奈",
        "slogan": "请原谅我……无论我做了什么……拜托原谅我……只要不被讨厌就够了",
        "title": "天才無敵美少女",
        "verified": false,
        "exp": 120056,
        "level": 35,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "c40211a1-f504-4fee-9928-1539817e6ed7.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 492,
        "character": "https://pica-web.wakamoment.tk/images/halloween_f.png"
      },
      {
        "_id": "582982c61cc00b5d50b1b5ff",
        "gender": "m",
        "name": "上杉绘梨衣",
        "slogan": "还就那个逆天",
        "title": "大佬",
        "verified": false,
        "exp": 89264,
        "level": 30,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "dd860eb6-ee35-423a-9187-78eb9c1c4b70.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 481,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "583ed6002b70b14d72f660f6",
        "gender": "m",
        "name": "二次元辐射",
        "slogan": "null",
        "title": "可是我覺得你好美",
        "verified": false,
        "exp": 56173,
        "level": 24,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "eb7ad5c9-921a-4c81-894b-aa267eca9ab2.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 476,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5ea13da01e958178de9c4f3a",
        "gender": "bot",
        "name": "极速射精王",
        "slogan": "         suo.nz/4VrWgY\n3d動畫與超色asmr資源下載",
        "title": "萌新",
        "verified": false,
        "exp": 13797,
        "level": 12,
        "characters": [],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "64d2fbd0-5501-4511-8198-679848186724.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 473
      },
      {
        "_id": "596634950d31a00c9f4675ea",
        "gender": "m",
        "name": "飞凡之光",
        "slogan": "   哔咔光宝的基本理念是保存人类文化遗产\n                      【🅱🍐🅱🍐同 🆔 】\n抖音上任何關於嗶咔官方帳號是假賬號！謹防被騙！",
        "title": "光宝",
        "verified": false,
        "exp": 399613,
        "level": 63,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "tobs/6e56cd9e-d334-4dc0-aaae-160d7995666b.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "comicsUploaded": 452,
        "character": "https://pica-pica.wikawika.xyz/special/frame-416.png"
      },
      {
        "_id": "584225bf4340d3b6644bbd0c",
        "gender": "m",
        "name": "Hortensia酱",
        "slogan": "オルテンシア（奥尔黛西亚）家族族长♥",
        "title": "摸鱼骑士H酱",
        "verified": false,
        "exp": 543442,
        "level": 74,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "cf0602ae-1e1f-4084-9e19-ed0e8b55954f.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 427,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "58421b383814d28465f122cc",
        "gender": "m",
        "name": "淡蓝色的樱花",
        "slogan": "null",
        "title": "萌新",
        "verified": false,
        "exp": 41331,
        "level": 20,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "tobs/882d751d-246a-4cd2-a353-a44ab3f0310a.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "comicsUploaded": 369,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "59415472bc297415b92ac1fd",
        "gender": "m",
        "name": "棺柩",
        "slogan": "棺柩姬",
        "title": "萌新",
        "verified": false,
        "exp": 52517,
        "level": 23,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "dd075ed4-873f-4812-91df-56300751d592.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 359,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "58876682f7c8533e979aee71",
        "gender": "m",
        "name": "无常人世",
        "slogan": "介绍用来记录喜欢的画师:\n无糖红茶 水平线 momi 吉 青水庵 みぞね Armadillo (練慈\nLonely Church (鈴音れな) おちちお (osisio)\nもじゃりん  つかこ まれお\n（水龙敬？狗都不看）\n2021.7.10更新\n\n",
        "title": "好耶←色一点的",
        "verified": false,
        "exp": 44339,
        "level": 21,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "tobs/38a695af-9870-4680-817f-534edcfc64cc.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "comicsUploaded": 339,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "59d5a26d152bcd690db2fb15",
        "gender": "bot",
        "name": "Jerry副社長",
        "slogan": "佛了",
        "title": "咸鱼的汉化组翻译",
        "verified": false,
        "exp": 102859,
        "level": 32,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "40f65557-178e-4f2e-88e5-53f505ec19d1.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 327,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "5915170918fba10745c15795",
        "gender": "m",
        "name": "残哔哔哔",
        "slogan": "重口味本子倾向hentai",
        "title": "萌新",
        "verified": false,
        "exp": 230875,
        "level": 48,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "f62bdc2e-ee3e-4a47-bef6-af671433127f.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 323,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5839da82a77b59e3183657c0",
        "gender": "m",
        "name": "OOOHHH",
        "slogan": "努力成为一名好骑士！",
        "title": "萌新",
        "verified": false,
        "exp": 52600,
        "level": 23,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "29a63193-121c-447d-b22b-ce92fd48c20c.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 319,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5cae1e3ee859a07091d8ce44",
        "gender": "bot",
        "name": "空條承大娘",
        "slogan": "一個看jojo的變態，只會傳奇怪的本子\n\n常見問題回答：\nQ. 爲什麽最近一些JOJO本子顯示\"審核中\"無法閲讀?\nA. 近期我們發現有人從嗶咔截取JOJO同人本上傳到商業網站。為保護上傳者/漢化組的權益，一些JOJO本子被保護性封鎖，待嗶咔解決問題后這些本子會恢復。\n\nQ. 爲什麽很多本子的評論與紅心數被清空?\nA. 嗶咔服務器不穩定，檔案在搬運會被突然清空。它們最終可以被恢復，但要花上一些時間。請注意這不是有人故意造成。\n\nQ. 爲什麽有一些JOJO本子明明超棒/有漢化，可嗶咔上一直沒有??\nA. 一些作者/漢化者明確反對將作品上傳至嗶咔這一特定網站，而嗶咔也尊重他們的意願。你所想到的本子約有80%是這種情況。\n\nQ. 我有本子想傳到嗶咔!! 要怎麼弄?\nA. 在嗶咔app點\"設定\"-\"常見問題解答\"，裡面有教你怎樣找人上傳本子。JOJO本很可能由我代傳，如果想換別人代傳請你寫明。\n\nQ. 提問箱不見了!!! 我該去哪和你聯絡!?\nA. 請到公共留言板留言，我每天都會看喔\n\nQ. 你的個人介紹視窗關不掉了!!!!\nA. 請拖到最上面，點我的頭像，然後關\n\n",
        "title": "🌟嗶咔女權先鋒🌟",
        "verified": false,
        "exp": 69243,
        "level": 26,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "e6303a0b-d2b6-491b-bdc5-f22044cdb73e.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 312,
        "character": "https://pica-web.wakamoment.tk/special/frame-383.png"
      },
      {
        "_id": "583fed1b78dbcfd26640156c",
        "gender": "m",
        "name": "齐达内射门",
        "title": "萌新",
        "verified": false,
        "exp": 199887,
        "level": 45,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "d4c43a5d-206f-4d95-aaf3-447e5f44f3be.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 300,
        "character": "https://wikawika.xyz/characters/frame_knight_250_499.png?r=3"
      },
      {
        "_id": "58298afb2cff43585035890e",
        "gender": "m",
        "name": "樱莎奈",
        "slogan": "没有介绍",
        "title": "傲娇樱花",
        "verified": false,
        "exp": 120667,
        "level": 35,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "30d4f4e3-62b7-41ed-b666-7d83abdaad3d.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 290,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "590d896d64d04f08aedb0e36",
        "gender": "m",
        "name": "夹心的糖",
        "slogan": "凌晨一点了。\n在你的面前是空无一人的街道，空荡得令你觉得不真实，忍不住使劲掐了自己一天工作下来变得麻木的手臂。一阵钻心的疼痛令你龇牙咧嘴，但也使得你清醒了过来。\n就在这时，你突然发现，在不远处的街灯下有一个打着红色尼龙雨伞的少女。她手中的雨伞在这片单调的色彩中里是那样的显眼，以至于你无法将视线移开。\n伞盖遮住了她大部分的身躯。身着标准的高中生制服的她没有穿鞋，静静地侧立驻足在原地。\n正当你打算靠近，撑着红色雨伞的少女忽然缓慢地走向街道的另一侧。\n你看到摇晃着的雨伞移开的瞬间，少女苍白的脸庞与恍惚的神情。少女抿着嘴唇，似乎朝着你微微笑了下——但也许是错觉。\n她迈进了潮水般的雨里。一步，一步。地面积起的雨水漫过了她的袜子，浸过了她的膝盖，接着是她的裙子，上衣……随着她的前进，就好像融化在了雨里一样，少女露出积水的部分越来越少。\n水位逐渐漫过她黑色的长发，最后地面上只剩下了水洼和那把她曾经握着的红雨伞。\n少女就这样消失在了猝不及防的你的面前。\n有如星河般深不可测的翻滚的黑色旋涡，吸收了周围全部的光线，数条打着旋的线条闪烁、撕扯、扭曲，不断变换成不可名状的形态。",
        "title": "神秘消失在雨雾中的少女",
        "verified": false,
        "exp": 298290,
        "level": 55,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "tobs/0a4b5794-e043-4e82-ade6-8fe4f374fc55.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "comicsUploaded": 276,
        "character": "https://pica-pica.wikawika.xyz/special/frame-155.png"
      },
      {
        "_id": "597b5a4fdb78c5321a2c8772",
        "gender": "m",
        "name": "冰可樂炒飯",
        "slogan": "。",
        "title": "萌新",
        "verified": false,
        "exp": 40955,
        "level": 20,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "f3ed4c15-2fd9-4a54-a182-254048092524.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 273,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "62089690aefa3a32bf4fa61b",
        "gender": "m",
        "name": "镜子里的鬼",
        "title": "萌新",
        "verified": false,
        "exp": 29939,
        "level": 17,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "comicsUploaded": 272,
        "character": "https://wikawika.xyz/characters/frame_knight_9.png?r=3"
      },
      {
        "_id": "5c2e1fe3ff0f55209d9cb09c",
        "gender": "bot",
        "name": "壃尸",
        "slogan": "考虑到pica现在的搜索规则，可能会简写作者/汉化组栏，便于点击时搜出更多同作者作品。简介里会尽量写全信息，便于复制后去站内外搜索。",
        "title": "老物搬运工/冷本认亲现场/瞎狗眼王者",
        "verified": false,
        "exp": 70893,
        "level": 27,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "ade2bb24-3f68-4046-80ee-83a2d53dbf94.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 268,
        "character": "https://wikawika.xyz/characters/frame_knight_250_499.png?r=3"
      },
      {
        "_id": "5ae749d43001a220a258ed2f",
        "gender": "m",
        "name": "与之而忆",
        "slogan": "你们觉得，会在哪里找到我？好累啊，摆烂了。躺平了，起飞了。",
        "title": "永远の悠久",
        "verified": false,
        "exp": 46992,
        "level": 22,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "ea373cbb-34b8-4d00-8c63-fb031316afaf.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 263,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "586a86f0ba0ab37012d05187",
        "gender": "m",
        "name": "如歌的行板",
        "slogan": "我永远相信西瓜熊。♥",
        "title": "萌新",
        "verified": false,
        "exp": 49952,
        "level": 22,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "9c94460b-d292-41de-938a-5ae2dd7cce36.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 253,
        "character": "https://wikawika.xyz/characters/frame_knight_9.png?r=3"
      },
      {
        "_id": "5832eb39b509a2f430573a62",
        "gender": "bot",
        "name": "jghkuu",
        "title": "🐱",
        "verified": false,
        "exp": 67420,
        "level": 26,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "86d27146-335d-4185-afa1-0c8833de15aa.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 252,
        "character": "https://pica-web.wakamoment.tk/images/halloween_bot.png"
      },
      {
        "_id": "59d47494e671696c2c31fd57",
        "gender": "m",
        "name": "老w",
        "slogan": "生活不止眼前的苟且，还有诗和远方。\n\n\n\n\n\n代傳        “二二二一九九三二七七”",
        "title": "萌新",
        "verified": false,
        "exp": 116422,
        "level": 34,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "1c68cd08-947c-451a-9395-93bb5bc507a0.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 246,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5ace534bdd491119301efdeb",
        "gender": "m",
        "name": "{null}",
        "slogan": "啊啊，bug惹。\n哔咔基本不在，侵删问题请直接联系QQ。",
        "title": "萌新",
        "verified": false,
        "exp": 71230,
        "level": 27,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "6dd92bc3-2071-4386-a787-118c7cfa1e4b.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 235,
        "character": "https://wikawika.xyz/characters/frame_knight_100_249.png?r=3"
      },
      {
        "_id": "590ca99adca05e0731407410",
        "gender": "m",
        "name": "不朽之尸",
        "slogan": "我开始慌了",
        "title": "TKDSミ张老尸",
        "verified": false,
        "exp": 74797,
        "level": 27,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "dfdee090-9468-48cc-bb1f-635e91a24fd6.jpg",
          "originalName": "avatar.jpg"
        },
        "comicsUploaded": 228,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      },
      {
        "_id": "5a6df27bdfab964088ceb30c",
        "gender": "f",
        "name": "克总的吸盘",
        "slogan": "来点翻译和嵌字吧！求求了，来点吧！😭\n\n看个原创商业耽美还要洁癖避雷的请速速离开我的世界🙏🙏←我对这种洁癖过敏，我也要“避雷”\n\n环壮/一织陆/千百/燐niki/宗咪/彩良/承花/帝韦伯/成御/赤安/咖喱/薰嗣/五夏五/虎伏/涉英/纯日和/椅苍/抹布/（除骨科之外的）乱伦就是zhui好的！（list有增加的趋势",
        "title": "荧光棒是坏文明！",
        "verified": false,
        "exp": 131659,
        "level": 36,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "74ebbf7c-3cd3-403c-839f-b093ca064ef1.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 222,
        "character": "https://pica-web.wakamoment.tk/images/halloween_f.png"
      },
      {
        "_id": "58896d2cf7c8533e979b016a",
        "gender": "m",
        "name": "silverAI",
        "slogan": "如果有错误请在评论区留言，我会尽快更正",
        "title": "萌新",
        "verified": false,
        "exp": 125940,
        "level": 35,
        "characters": [
          "knight"
        ],
        "role": "knight",
        "avatar": {
          "originalName": "avatar.jpg",
          "path": "9227b042-c548-499a-98ca-5da495460b2b.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "comicsUploaded": 221,
        "character": "https://pica-web.wakamoment.tk/images/halloween_m.png"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» users|[object]|true|none||none|
|»»» _id|string|true|none||none|
|»»» gender|string|true|none||none|
|»»» name|string|true|none||none|
|»»» slogan|string|true|none||none|
|»»» title|string|true|none||none|
|»»» verified|boolean|true|none||none|
|»»» exp|integer|true|none||none|
|»»» level|integer|true|none||none|
|»»» characters|[string]|true|none||none|
|»»» role|string|true|none||none|
|»»» avatar|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»» comicsUploaded|integer|true|none||none|
|»»» character|string|true|none||none|

## POST 漫画-高级搜索

POST /comics/advanced-search

不知道高级在哪....

> Body 请求参数

```json
{
  "categories": [
    "string"
  ],
  "keyword": "string",
  "sort": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|string| 否 |页码|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» categories|body|[string]¦null| 是 |分区|
|» keyword|body|string| 是 |搜索关键字，不能为空|
|» sort|body|string| 是 |排序|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comics": {
      "total": 4,
      "page": 1,
      "pages": 1,
      "docs": [
        {
          "updated_at": "2008-01-08T00:47:25.000Z",
          "thumb": {
            "originalName": "cover.jpg",
            "path": "tobeimg/m0Z5PRsK_DqYPC5yMeOulBwsZsRlN3t1klBdObSpWvg/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy85MmZkZGY1ZS04OWQ3LTQwYWUtYjMzNi04NjRlNzViNDEyODMuanBn.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "author": "[ブレキン。(榊歌丸)]",
          "description": "不知火舞的堕落",
          "chineseTeam": "未知",
          "created_at": "2008-01-08T00:47:25.000Z",
          "finished": false,
          "totalViews": 65187,
          "categories": [
            "同人",
            "短篇",
            "重口地帶",
            "強暴"
          ],
          "totalLikes": 252,
          "title": "舞姦 弐",
          "tags": [],
          "_id": "58218b725f6b9a4f93e02a99",
          "likesCount": 252
        },
        {
          "updated_at": "2014-08-23T14:46:55.000Z",
          "thumb": {
            "originalName": "cover.jpg",
            "path": "tobeimg/ALh0zxq6tl_hnBDiXnMr51S1LA6twzDEubisyyV_sl0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8zNmFmZjdmNi0xMmRjLTQ4YTUtOGIxMC04YjY4MTFlNGUwNzIuanBn.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "author": "忘了",
          "description": "不知火舞的本子，画风很好，故事情节满分，珍藏不看后悔！",
          "chineseTeam": "未知",
          "created_at": "2014-08-23T14:46:55.000Z",
          "finished": true,
          "totalViews": 893664,
          "categories": [
            "同人",
            "短篇",
            "強暴"
          ],
          "totalLikes": 5804,
          "title": "不知火舞斩2",
          "tags": [],
          "_id": "5821ab115f6b9a4f93f4659d",
          "likesCount": 5804
        },
        {
          "updated_at": "2018-05-08T04:21:57.170Z",
          "thumb": {
            "originalName": "61248120_p14_master1200.jpg",
            "path": "tobeimg/Y8AJntsm5dbqUXiANCqwhWiGCBy8QA6j6lZzWrNt8dA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8xY2IyMDdkMy05NmZhLTQ2ZTItYjQ0Yi05MTY1ZjY2YTRlODMuanBn.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "author": "乔治布鲁诺",
          "description": "真的是有点毁童年，毁你们女神（虽然我也喜欢舞），但是我本人是有点猎奇癖的，劝你们最好别看（滑稽）斩首截肢断臂什么的好zui恶hao心kan啊la\n绅士群加微信：rion7719自动进群",
          "created_at": "2018-05-07T14:48:55.927Z",
          "finished": false,
          "totalViews": 902771,
          "categories": [
            "全彩",
            "同人",
            "短篇",
            "CG雜圖",
            "SM",
            "重口地帶",
            "強暴",
            "非人類"
          ],
          "totalLikes": 2953,
          "title": "[3D]不知火舞的死期(琦玉老师乱入）重口慎入",
          "tags": [
            "乳汁",
            "巨乳",
            "乳交",
            "拳交",
            "拳皇ＫＯＦ",
            "拳皇ＫＯＦ: 不知火舞",
            "失禁",
            "非人類"
          ],
          "_id": "5af125e5c9934656efdb808f",
          "likesCount": 2953
        },
        {
          "updated_at": "2019-06-15T03:38:07.888Z",
          "thumb": {
            "originalName": "不知火舞 腸內洗淨.jpg",
            "path": "tobeimg/d254-fK5DK0kHM0PYvjsWx4J6Fy9MogiZIFt8LMgb_0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8zMGJhMDFiOS0wMDg1LTRkY2EtOTUxYS1hN2Q1Mjk2MGVlZjUuanBn.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "author": "戴绿帽的安迪（滑稽）和p站众画师",
          "description": "安迪的绿帽戴的稳稳的(持续更新)\n准备开始继续上传不知火舞的养眼美图，请大家继续关注\n绅士学习群+weixin：shionRION加好友自动拉你进去",
          "created_at": "2018-03-08T09:36:24.136Z",
          "finished": false,
          "totalViews": 2306227,
          "categories": [
            "短篇",
            "全彩",
            "同人",
            "CG雜圖",
            "SM",
            "重口地帶",
            "強暴",
            "人妻",
            "非人類",
            "NTR"
          ],
          "totalLikes": 18957,
          "title": "不知火舞婚前捕獲（内含3D）",
          "tags": [
            "脫糞",
            "KOF：不知火舞",
            "拳皇ＫＯＦ: 不知火舞",
            "SM",
            "灌腸",
            "性玩具",
            "NTR",
            "人妻",
            "3D",
            "非人類",
            "放尿",
            "觸手",
            "凌辱",
            "3P",
            "獸交",
            "獸人",
            "人獸交",
            "乳交",
            "群交",
            "口交"
          ],
          "_id": "5aa20fc0ea8c1023dd61ea8a",
          "likesCount": 18957
        }
      ],
      "limit": 20
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comics|object|true|none||none|
|»»» total|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» pages|integer|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» updated_at|string|true|none||none|
|»»»» thumb|object|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»»» author|string|true|none||none|
|»»»» description|string|true|none||none|
|»»»» chineseTeam|string|true|none||none|
|»»»» created_at|string|true|none||none|
|»»»» finished|boolean|true|none||none|
|»»»» totalViews|integer|true|none||none|
|»»»» categories|[string]|true|none||none|
|»»»» totalLikes|integer|true|none||none|
|»»»» title|string|true|none||none|
|»»»» tags|[string]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» likesCount|integer|true|none||none|
|»»» limit|integer|true|none||none|

## POST （取消）收藏本子

POST /comics/{comicId}/favourite

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "action": "un_favourite"
  }
}
```

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "action": "favourite"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» action|string|true|none||none|

## GET 随机本子

GET /comics/random

随机本子

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comics": [
      {
        "_id": "59b8186ac2e4251667c52fd0",
        "title": "(C88) 強面オトン提督の娘 (艦隊これくしょん -艦これ-)",
        "author": "パレス犬吠崎 (蘇募ロウ)",
        "pagesCount": 58,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "妹妹系",
          "艦隊收藏",
          "禁書目錄"
        ],
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "tobeimg/T7It30U8zSC68o-XzCN1eKL5GyHXA1DJZk7-4Br7bHk/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9jNTVmNDkyZC0xOGJmLTQ1ODQtOTE4MC0yMjc3Yjk1MDg5MmQuanBn.jpg",
          "originalName": "1.jpg"
        },
        "totalViews": 48395,
        "totalLikes": 767,
        "likesCount": 767
      },
      {
        "_id": "59b81876b10a2f4f542cea68",
        "title": "(C90) 強面オトン提督の娘3 (艦隊これくしょん -艦これ-)",
        "author": "パレス犬吠崎 (蘇募ロウ)",
        "pagesCount": 36,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "艦隊收藏",
          "禁書目錄"
        ],
        "thumb": {
          "originalName": "20170407_121418_0001.jpg",
          "path": "tobeimg/Q91n7swfaN5nEuBpqgw_C5jk5Xh0iG0Y3nORv54dh2c/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy83NzE3NzY0Ny0wZjc2LTQ4MGUtYTc2Zi0zNzg0ZWNkMDNhY2UuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 22019,
        "totalLikes": 400,
        "likesCount": 400
      },
      {
        "_id": "59b8a862b6ee8a169619fbab",
        "title": "(COMIC1☆9) fall into a trap キュートなシンデレラ2人のキメセクプロモーション (アイドルマスターシンデレラガールズ)",
        "author": "姫屋 (阿部いのり)",
        "pagesCount": 20,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "NTR"
        ],
        "thumb": {
          "originalName": "001.jpg",
          "path": "tobeimg/FvrrYiMXm269Q08pyAavmIdNWXRjQw3me7HZTbsAfa0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9lNjdjNTRlYy01ZmRhLTQyZDctYWQzYy1hY2M3MDhlMDVlY2EuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 89181,
        "totalLikes": 497,
        "likesCount": 497
      },
      {
        "_id": "59b8a88d5ef2bb165fe45799",
        "title": "(C86) 慰安戦艦姉妹 (艦隊これくしょん -艦これ-) ",
        "author": "姫屋 (阿部いのり)",
        "pagesCount": 32,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "艦隊收藏"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/wSz_QxFPQwOA_x20Xcbo9h1Mz6Fx63SRBtIDtZ9Irsg/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9hMmRmMGRhNi0wNDdmLTRjYTctODk4Ny0yMmU3YWU5OGQ1OGQuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 40179,
        "totalLikes": 316,
        "likesCount": 316
      },
      {
        "_id": "59b8a8b2c2e4251667c530ee",
        "title": "(C87) 独隷日誌～来日した海外艦を快楽中毒調教～ (艦隊これくしょん -艦これ-)",
        "author": "姫屋 (阿部いのり)",
        "pagesCount": 32,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "艦隊收藏"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/iVFK_Ri6NFqnA5fUoeDys6nA9JxC89EW7N_hUEqVN44/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9hMmIxMzZlNC1hMmUyLTRjMmQtYmI2OS1lOWY5Njg3N2M5NWYuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 115964,
        "totalLikes": 695,
        "likesCount": 695
      },
      {
        "_id": "59b8a8c85ef2bb165fe457bb",
        "title": "メイプルカラーズHHH クラス全員俺の嫁！",
        "author": "",
        "pagesCount": 199,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "CG雜圖"
        ],
        "thumb": {
          "originalName": "0001 [原始大小].png",
          "path": "tobeimg/TO0I0nieU1rwhsQP-im6yIiaF6C9vyEZadWnBpMSZII/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8xMGE1Y2I1MS00Nzk2LTRhM2MtYjNhYi1iMTBjODc5NWE4ZGEucG5n.png",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 24976,
        "totalLikes": 248,
        "likesCount": 248
      },
      {
        "_id": "59b8a910be593416ad70da86",
        "title": "A Diva of Healing (機動戦士ガンダムSEED DESTINY)",
        "author": "鈴木あどれす",
        "pagesCount": 110,
        "epsCount": 5,
        "finished": true,
        "categories": [
          "同人",
          "長篇"
        ],
        "thumb": {
          "originalName": "01.jpg",
          "path": "tobeimg/jYho51HwH7YHWNtzs5D7BkbDgLWuuDote6uSh3DfcHs/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8xMTkwZjM2OS1hYWY3LTRlZDAtYjI2Ni00YjI1OGI0OTA1YmQuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 1039258,
        "totalLikes": 1144,
        "likesCount": 1144
      },
      {
        "_id": "59b9099a6bed5a4f8cbcf2ad",
        "title": "ヌキ挿し自由のメイド穴",
        "author": "荒岸来歩",
        "pagesCount": 204,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇"
        ],
        "thumb": {
          "originalName": "001.jpg",
          "path": "tobeimg/6ofLX3ul4kQ1Coq5hoovBhfwrcrQjOBIcQhGznZzlYI/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9mMzM1ZTg1ZS01ZjI0LTQ4MGEtODA4Mi02MzU2MzhkOTg1MjAuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 129536,
        "totalLikes": 1111,
        "likesCount": 1111
      },
      {
        "_id": "59b909a85ef2bb165fe459cb",
        "title": "夏と箱",
        "author": "doumou",
        "pagesCount": 32,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇"
        ],
        "thumb": {
          "originalName": "001.jpg",
          "path": "tobeimg/WONlsMZ6pFVWgZkwTsL6GVM5uBMYb9nqRkZGLjjzm9Y/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9kOGEwM2VkYy1hNjFiLTRhNTYtOTczOS1mMGM0YWUwNmJmODMuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 62047,
        "totalLikes": 1320,
        "likesCount": 1320
      },
      {
        "_id": "59b909c2b6ee8a169619fcf6",
        "title": "取り立て上手な大家さん",
        "author": "REI's ROOM (REI)",
        "pagesCount": 24,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "短篇"
        ],
        "thumb": {
          "originalName": "01.jpg",
          "path": "tobeimg/I8tSbppTpXW2UmiBif4h0iPaL7kmjEvTjLN8NCkEZX8/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8yZjFjODFkNi00Y2Y0LTQwNjItYWQxZC1kMzhhZDgyNjdlMDguanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 49779,
        "totalLikes": 511,
        "likesCount": 511
      },
      {
        "_id": "59b909dab6ee8a169619fd10",
        "title": "冴えない男女(ふたり)の致しかた4 ",
        "author": "町田チェリーボーイズ (クロサワ)",
        "pagesCount": 24,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇"
        ],
        "thumb": {
          "originalName": "01.jpg",
          "path": "tobeimg/lrVPSMewExzz3M_hBl_1DouW1KLHvybOEsx0sRoRs2Y/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy83OGIwMDFmYS04OTFiLTQ5NDQtOTUxZC0zNWQ4YTVhZGM5YWEuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 69292,
        "totalLikes": 729,
        "likesCount": 729
      },
      {
        "_id": "59b909e85ef2bb165fe459ef",
        "title": "悦狂い！母は見世物 コスプレ！AV！宴会芸！ 寝取られ熟母夏子41歳",
        "author": "ワニデジタル",
        "pagesCount": 298,
        "epsCount": 2,
        "finished": false,
        "categories": [
          "全彩",
          "長篇",
          "CG雜圖",
          "人妻",
          "生肉"
        ],
        "thumb": {
          "originalName": "image_001.jpg",
          "path": "tobeimg/UGny09qmwBOEMPSDGQcN0_LxbFJb1dD17x6C7peizO0/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy83OGNkZmNhZi1iNTQzLTRhZDEtYWRkZC0wYThkMzYxYjllNmYuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 1096460,
        "totalLikes": 1699,
        "likesCount": 1699
      },
      {
        "_id": "59b90a05be593416ad70dc8b",
        "title": "たわわの感触3 (月曜日のたわわ)",
        "author": "雷神会 (はるきゲにあ)",
        "pagesCount": 28,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇"
        ],
        "thumb": {
          "originalName": "01.jpg",
          "path": "tobeimg/aJ3b1rEyyPHr0kXWduCpr6BzV-MMG74Cme3L1FMgBrA/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8yNTIxNzI0Yi1jZWRiLTQ1OGItYmI1OS1mMWZhYzQzMThiMjQuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "likesCount": 31
      },
      {
        "_id": "59b90a1797f4c960c3a2120d",
        "title": "Slave Princess",
        "author": "小山電脳技研",
        "pagesCount": 105,
        "epsCount": 1,
        "finished": false,
        "categories": [
          "全彩",
          "長篇",
          "CG雜圖",
          "生肉",
          "重口地帶",
          "非人類",
          "人妻"
        ],
        "thumb": {
          "originalName": "0001_Cover.jpg",
          "path": "tobeimg/ee-gc891FcMPA1tvGUict4jRJkqNASnQG9BnZhv7Whw/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy85MWM1N2I5ZC01YzVmLTQzNGItOWY3OS04NTg0NWY0Mjg1ZjEuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 266073,
        "totalLikes": 2155,
        "likesCount": 2155
      },
      {
        "_id": "59b90a243c977b4fa71bd3b9",
        "title": "歪んだ家族 ",
        "author": "いぶろー。",
        "pagesCount": 213,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇",
          "妹妹系"
        ],
        "thumb": {
          "originalName": "HF_001_副本1.jpg",
          "path": "tobeimg/_-wGzEyd2so_cE6SbP3NjdNVq_A_0eRhvGDpacY1QdI/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy81M2QyZjc3Yi0yNDkxLTRhMDItYWExZS01NTM3YTMwYzk5NTguanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 190892,
        "totalLikes": 1409,
        "likesCount": 1409
      },
      {
        "_id": "59b95dcf3c977b4fa71bd60e",
        "title": "(C91) idolize #3.5 (アイドルマスター シンデレラガールズ) ",
        "author": "40デニール (篠岡ほまれ)",
        "pagesCount": 25,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "足の恋"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/jzXi4dQ8MH1e-A7MAdVoD2_nIGB7hN3ubxQns6R6yJ4/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy83MTA3N2EwOS1jOGZjLTRiNGMtOWRmZC02NzcyOWJhOTUzNTguanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 318767,
        "totalLikes": 2412,
        "likesCount": 2412
      },
      {
        "_id": "59b95dd95ef2bb165fe45cd1",
        "title": "美淫感アナル～拡醒ねじこみ穴～ | 美淫感猥菊花 塞入擴張覺醒穴",
        "author": "Lorica",
        "pagesCount": 206,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇"
        ],
        "thumb": {
          "originalName": "IMG_0000.jpg",
          "path": "tobeimg/_NlDPlkNK5PlZ-wO7lGwFzuhyUMm5QEG3rmSHh4CgPo/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy8xNWNkYjk3Zi01MzU2LTRjM2ItOGU0ZS0yOGY1ODYzZThlOGUuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 402564,
        "totalLikes": 3660,
        "likesCount": 3660
      },
      {
        "_id": "59b95de5be593416ad70de1e",
        "title": "マゾ穴折檻～躾けられた女たち～",
        "author": "日陰ひなた",
        "pagesCount": 201,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "長篇"
        ],
        "thumb": {
          "originalName": "IMG_0000.jpg",
          "path": "tobeimg/s9qDKM8uPCLmOBpfBLIqWgI_UVKNYqNXaqJ70ktKTB4/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9lNjliNDRmMy0zMzI4LTQ2MDctOTgxMC0xYmVmNDE2ZDcwOTkuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 193810,
        "totalLikes": 1855,
        "likesCount": 1855
      },
      {
        "_id": "59b95df297f4c960c3a213d3",
        "title": "Canid Girls Rock (グランブルーファンタジー)",
        "author": "魚骨工造 (カポ)",
        "pagesCount": 18,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "碧藍幻想",
          "百合花園",
          "非人類"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/E6LVVJjHz01RLdker56Vyt-RKw5ALiaqwVrYTylOjKo/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy9jMWQxM2NmMC1lYzEwLTRlOGItYjVmMi1lZDg1NzMyZTY3YTAuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 78780,
        "totalLikes": 754,
        "likesCount": 754
      },
      {
        "_id": "59b95df73c977b4fa71bd62a",
        "title": "ずっと!SAOff SUMMER (ソードアート·オンライン)",
        "author": "Primal Gym (カワセセイキ)",
        "pagesCount": 24,
        "epsCount": 1,
        "finished": true,
        "categories": [
          "同人",
          "短篇",
          "妹妹系",
          "SAO 刀劍神域"
        ],
        "thumb": {
          "originalName": "1.jpg",
          "path": "tobeimg/62juslHx1VXp_bM9r2QW6l1fwC2Zfjp5CdLkEL_oiW8/rs:fill:300:400:0/g:sm/aHR0cHM6Ly9zdG9yYWdlMS5waWNhY29taWMuY29tL3N0YXRpYy81NmU1N2Q1OC00ODY0LTQ2NWYtOGI5ZC03YzRlOTRiY2NjNTUuanBn.jpg",
          "fileServer": "https://storage1.picacomic.com"
        },
        "totalViews": 302371,
        "totalLikes": 2614,
        "likesCount": 2614
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comics|[object]|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|
|»»» author|string|true|none||none|
|»»» pagesCount|integer|true|none||none|
|»»» epsCount|integer|true|none||none|
|»»» finished|boolean|true|none||none|
|»»» categories|[string]|true|none||none|
|»»» thumb|object|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» originalName|string|true|none||none|
|»»» totalViews|integer|true|none||none|
|»»» totalLikes|integer|true|none||none|
|»»» likesCount|integer|true|none||none|

## GET 获取本子的章节

GET /comics/{comicId}/eps

获取本子的章节

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|comicId|path|string| 是 |none|
|page|query|integer| 否 |分页|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "eps": {
      "docs": [
        {
          "_id": "58218b735f6b9a4f93e02a9b",
          "title": "第1集",
          "order": 1,
          "updated_at": "2016-11-08T08:23:15.215Z",
          "id": "58218b735f6b9a4f93e02a9b"
        }
      ],
      "total": 1,
      "limit": 40,
      "page": 1,
      "pages": 1
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» eps|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|false|none||none|
|»»»» title|string|false|none||none|
|»»»» order|integer|false|none||none|
|»»»» updated_at|string|false|none||none|
|»»»» id|string|false|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» pages|integer|true|none||none|

## GET 漫画

GET /comics

都是什么鬼Query参数，就几个字母是怎么回事！
2022-7-4在GitHub找到了参数的意思https://github.com/czp3009/picacomic-api/blob/3be60a142df6fc91e53b936859234a58575a4432/src/main/kotlin/com/hiczp/picacomic/api/service/comic/ComicService.kt
实在是搞不定

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|integer| 否 |页码|
|c|query|string| 否 |分区|
|t|query|array| 否 |标签|
|a|query|string| 否 |作者|
|f|query|string| 否 |是否完结|
|s|query|string| 否 |排序条件, 在某些分类不工作|
|ct|query|string| 否 |翻译|
|ca|query|string| 否 |上传者|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# categories

## GET 分区

GET /categories

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "categories": [
      {
        "title": "援助嗶咔",
        "thumb": {
          "originalName": "help.jpg",
          "path": "help.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "active": true,
        "link": "https://donate.wikawika.xyz"
      },
      {
        "title": "嗶咔小禮物",
        "thumb": {
          "originalName": "picacomic-gift.jpg",
          "path": "picacomic-gift.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "link": "https://gift-web.wikawika.xyz",
        "active": true
      },
      {
        "title": "小電影",
        "thumb": {
          "originalName": "av.jpg",
          "path": "av.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "link": "https://av.wikawika.xyz",
        "active": true
      },
      {
        "title": "小里番",
        "thumb": {
          "originalName": "h.jpg",
          "path": "h.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "link": "https://h.wikawika.xyz",
        "active": true
      },
      {
        "title": "嗶咔畫廊",
        "thumb": {
          "originalName": "picacomic-paint.jpg",
          "path": "picacomic-paint.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "link": "https://paint-web.wikawika.xyz",
        "active": true
      },
      {
        "title": "嗶咔鍋貼",
        "thumb": {
          "originalName": "picacomic-post.jpg",
          "path": "picacomic-post.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "link": "https://post-web.wikawika.xyz",
        "active": true
      },
      {
        "title": "嗶咔商店",
        "thumb": {
          "originalName": "picacomic-shop.jpg",
          "path": "picacomic-shop.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "link": "https://online-shop-web.wikawika.xyz",
        "active": true
      },
      {
        "title": "大家都在看",
        "thumb": {
          "originalName": "every-see.jpg",
          "path": "every-see.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": false,
        "active": true
      },
      {
        "title": "被褐懷玉",
        "thumb": {
          "originalName": "recommendation.jpg",
          "path": "tobs/718cbd78-8aa9-4c85-9a99-a43ec74a96ef.jpg",
          "fileServer": "https://storage-b.picacomic.com"
        },
        "isWeb": false,
        "active": true
      },
      {
        "title": "那年今天",
        "thumb": {
          "originalName": "old.jpg",
          "path": "old.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": false,
        "active": true
      },
      {
        "title": "官方都在看",
        "thumb": {
          "originalName": "promo.jpg",
          "path": "promo.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": false,
        "active": true
      },
      {
        "title": "嗶咔運動",
        "thumb": {
          "originalName": "picacomic-move-cat.jpg",
          "path": "picacomic-move-cat.jpg",
          "fileServer": "https://wikawika.xyz/static/"
        },
        "isWeb": true,
        "active": true,
        "link": "https://move-web.wikawika.xyz"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e9",
        "title": "嗶咔漢化",
        "description": "未知",
        "thumb": {
          "originalName": "translate.png",
          "path": "f541d9aa-e4fd-411d-9e76-c912ffc514d1.png",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d1",
        "title": "全彩",
        "description": "未知",
        "thumb": {
          "originalName": "全彩.jpg",
          "path": "8cd41a55-591c-424c-8261-e1d56d8b9425.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cd",
        "title": "長篇",
        "description": "未知",
        "thumb": {
          "originalName": "長篇.jpg",
          "path": "681081e7-9694-436a-97e4-898fc68a8f89.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6ca",
        "title": "同人",
        "description": "未知",
        "thumb": {
          "originalName": "同人.jpg",
          "path": "1a33f1be-90fa-4ac7-86d7-802da315732e.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6ce",
        "title": "短篇",
        "description": "未知",
        "thumb": {
          "originalName": "短篇.jpg",
          "path": "bd021022-8e19-49ff-8c62-6b29f31996f9.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "584ea1f45a44ac4f7dce3623",
        "title": "圓神領域",
        "description": "魔法少女小圓為主題的本子",
        "thumb": {
          "originalName": "cat_cirle.jpg",
          "path": "c7e86b6e-4d27-4d81-a083-4a774ceadf72.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "58542b601b8ef1eb33b57959",
        "title": "碧藍幻想",
        "description": "碧藍幻想的本子",
        "thumb": {
          "originalName": "blue.jpg",
          "path": "b8608481-6ec8-46a3-ad63-2f8dc5da4523.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e5",
        "title": "CG雜圖",
        "description": "未知",
        "thumb": {
          "originalName": "CG雜圖.jpg",
          "path": "b62b79b7-26af-4f81-95bf-d27ef33d60f3.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e8",
        "title": "英語 ENG",
        "description": "未知",
        "thumb": {
          "originalName": "英語 ENG.jpg",
          "path": "6621ae19-a792-4d0c-b480-ae3496a95de6.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e0",
        "title": "生肉",
        "description": "未知",
        "thumb": {
          "originalName": "生肉.jpg",
          "path": "c90a596c-4f63-4bdf-953d-392edcbb4889.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6de",
        "title": "純愛",
        "description": "未知",
        "thumb": {
          "originalName": "純愛.jpg",
          "path": "18fde59b-bee5-4177-bf1f-88c87c7c9d70.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d2",
        "title": "百合花園",
        "description": "未知",
        "thumb": {
          "originalName": "百合花園.jpg",
          "path": "de5f1ca3-840a-4ea4-b6c0-882f1d80bd2e.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e2",
        "title": "耽美花園",
        "description": "未知",
        "thumb": {
          "originalName": "1492872524635.jpg",
          "path": "dcfa0115-80c9-4233-97e3-1ad469c2c0df.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e4",
        "title": "偽娘哲學",
        "description": "未知",
        "thumb": {
          "originalName": "偽娘哲學.jpg",
          "path": "39119d6c-4808-4859-98df-4dda30b9da3b.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d3",
        "title": "後宮閃光",
        "description": "未知",
        "thumb": {
          "originalName": "後宮閃光.jpg",
          "path": "dec122af-84bf-4736-b8f0-d6533a2839f7.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d4",
        "title": "扶他樂園",
        "description": "未知",
        "thumb": {
          "originalName": "扶他樂園.jpg",
          "path": "73d8a102-1805-4b14-b258-a95c85b02b8a.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5abb3fd683111d2ad3eecfca",
        "title": "單行本",
        "thumb": {
          "originalName": "Loveland_001 (2).jpg",
          "path": "a29c241a-2af7-47f2-aae5-b640374b12ac.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6da",
        "title": "姐姐系",
        "description": "未知",
        "thumb": {
          "originalName": "姐姐系.jpg",
          "path": "91e551c5-a98f-4f41-b7a0-c125bd77c523.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6db",
        "title": "妹妹系",
        "description": "未知",
        "thumb": {
          "originalName": "妹妹系.jpg",
          "path": "098f612c-9d16-4848-9732-0305b66ed799.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cb",
        "title": "SM",
        "description": "未知",
        "thumb": {
          "originalName": "SM.jpg",
          "path": "41fc9bce-68f6-4b36-98cf-14ab3d3bd19e.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d0",
        "title": "性轉換",
        "description": "未知",
        "thumb": {
          "originalName": "性轉換.jpg",
          "path": "f5c70a00-538c-44b8-b692-d6c3b049e133.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6df",
        "title": "足の恋",
        "description": "未知",
        "thumb": {
          "originalName": "足の恋.jpg",
          "path": "ad3373c7-4974-45f5-b5d6-eb9490363314.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cc",
        "title": "人妻",
        "description": "未知",
        "thumb": {
          "originalName": "人妻.jpg",
          "path": "e3359724-603b-47d8-905f-c88c5d38c983.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d8",
        "title": "NTR",
        "description": "未知",
        "thumb": {
          "originalName": "NTR.jpg",
          "path": "e10cf018-e214-41fa-bf1c-376a6b7a24ea.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d9",
        "title": "強暴",
        "description": "未知",
        "thumb": {
          "originalName": "強暴.jpg",
          "path": "4c3a9fb0-3084-4abf-bbc9-8efa33554749.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d6",
        "title": "非人類",
        "description": "未知",
        "thumb": {
          "originalName": "非人類.jpg",
          "path": "b09840fe-8ca9-41ac-9e73-3dd68e426865.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cf",
        "title": "艦隊收藏",
        "description": "未知",
        "thumb": {
          "originalName": "艦隊收藏.jpg",
          "path": "1ed52b9e-8ac3-47ae-bafc-c31bfab9b3d5.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d7",
        "title": "Love Live",
        "description": "未知",
        "thumb": {
          "originalName": "Love Live.jpg",
          "path": "b2ae70d1-1c0e-415f-b3f8-0f6f17626387.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6dc",
        "title": "SAO 刀劍神域",
        "description": "未知",
        "thumb": {
          "originalName": "SAO 刀劍神域.jpg",
          "path": "f7c0ccc3-6baf-4823-b2b5-a7a83d426d4c.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e1",
        "title": "Fate",
        "description": "未知",
        "thumb": {
          "originalName": "Fate.jpg",
          "path": "44bf46b9-415e-490b-9b61-7916ef2cea53.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6dd",
        "title": "東方",
        "description": "未知",
        "thumb": {
          "originalName": "東方.jpg",
          "path": "c373bf9d-1003-453d-a791-f65dde937654.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "59041d54ccc747074b47dae4",
        "title": "WEBTOON",
        "description": "Webtoon 是一種始創於韓國的新概念網路漫畫，由「Web（網路）」及「Cartoon（漫畫、卡通）」組成，只需向上下滑動就能閱讀，不需翻頁，是一種專為電腦及行動裝置而設的漫畫。",
        "thumb": {
          "originalName": "52a81f09-32a0-422b-bba3-207eb4d22520.jpg",
          "path": "60c01af5-e9cd-4888-bf5c-89fb60a97cc7.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e3",
        "title": "禁書目錄",
        "description": "未知",
        "thumb": {
          "originalName": "禁書目錄.jpg",
          "path": "c4314a3f-2644-473f-9b13-d78c8d857933.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5bd66e7e8ff47f7c46cf999d",
        "title": "歐美",
        "description": "歐美",
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "0486b618-ccbb-4c77-a141-06351079eb9f.jpg",
          "originalName": "67edd79c63e037afcd6309c25ad312a1.jpg"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e6",
        "title": "Cosplay",
        "description": "未知",
        "thumb": {
          "originalName": "Cosplay.jpg",
          "path": "24ee03b1-ad3d-4c6b-9f0f-83cc95365006.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d5",
        "title": "重口地帶",
        "description": "未知",
        "thumb": {
          "originalName": "重口地帶.jpg",
          "path": "4540db04-ebbe-4834-a77a-7b7995b5f784.jpg",
          "fileServer": "https://storage1.picacomic.com"
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» categories|[object]|true|none||none|
|»»» title|string|true|none||none|
|»»» thumb|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»» isWeb|boolean|true|none||none|
|»»» active|boolean|true|none||none|
|»»» link|string|true|none||none|
|»»» _id|string|true|none||none|
|»»» description|string|true|none||none|

# users

## GET 哔咔通知

GET /users/notifications

比如：有人给你点赞啊，回复你啊

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|string| 否 |分页|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "notifications": {
      "docs": [],
      "total": 0,
      "limit": 10,
      "page": 1,
      "pages": 1
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» notifications|object|true|none||none|
|»»» docs|[string]|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» pages|integer|true|none||none|

## PUT 更新用户的头像

PUT /users/avatar

暂不只头像图片长宽限制，图片需要Base64编码，且需要数据头

> Body 请求参数

```json
{
  "avatar": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» avatar|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 400,
  "error": "1002",
  "message": "validation error",
  "detail": "avatar length must be less than or equal to 689493 characters long"
}
```

```json
{
  "code": 500,
  "error": "ENOSPC: no space left on device, write",
  "message": "--",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 我的评论

GET /users/my-comments

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|string| 否 |页码|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comments": {
      "docs": [
        {
          "_id": "62c3fb4c45fc283cdcb14ce9",
          "content": "et id consectetur",
          "_comic": {
            "_id": "58218b725f6b9a4f93e02a99",
            "title": "舞姦 弐"
          },
          "totalComments": 0,
          "hide": false,
          "created_at": "2022-07-05T08:50:20.349Z",
          "id": "62c3fb4c45fc283cdcb14ce9",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "60bc90ff1837bc6942207bd4",
          "content": "你好",
          "_comic": {
            "_id": "5821876b5f6b9a4f93dd50eb",
            "title": "觸乳"
          },
          "hide": false,
          "created_at": "2021-06-06T09:10:23.222Z",
          "id": "60bc90ff1837bc6942207bd4",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "603aed59c019f9bf57d8585d",
          "content": "你好",
          "_comic": {
            "_id": "5ef23efe746b331df52c8851",
            "title": "合体！抜けない！？～交尾したまま日常性活～ [中国翻訳] "
          },
          "hide": false,
          "created_at": "2021-02-28T01:09:45.510Z",
          "id": "603aed59c019f9bf57d8585d",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        },
        {
          "_id": "603aecdeef502e634909a452",
          "content": "你好",
          "_comic": {
            "_id": "5ef23efe746b331df52c8851",
            "title": "合体！抜けない！？～交尾したまま日常性活～ [中国翻訳] "
          },
          "hide": false,
          "created_at": "2021-02-28T01:07:42.931Z",
          "id": "603aecdeef502e634909a452",
          "likesCount": 0,
          "commentsCount": 0,
          "isLiked": false
        }
      ],
      "total": 4,
      "limit": 20,
      "page": "1",
      "pages": 1
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comments|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» content|string|true|none||none|
|»»»» _comic|object|true|none||none|
|»»»»» _id|string|true|none||none|
|»»»»» title|string|true|none||none|
|»»»» totalComments|integer|false|none||none|
|»»»» hide|boolean|true|none||none|
|»»»» created_at|string|true|none||none|
|»»»» id|string|true|none||none|
|»»»» likesCount|integer|true|none||none|
|»»»» commentsCount|integer|true|none||none|
|»»»» isLiked|boolean|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|string|true|none||none|
|»»» pages|integer|true|none||none|

## POST (取消)拉黑某人

POST /users/{userId}/dirty

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|userId|path|string| 是 |要拉黑的人的用户ID|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "dirty": true
  }
}
```

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "dirty": false
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» dirty|boolean|true|none||none|

## GET 用户信息

GET /users/profile

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## PUT 修改自我介绍

PUT /users/profile

> Body 请求参数

```json
{
  "slogan": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» slogan|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|

## GET 获取指定用户信息

GET /users/{userId}/profile

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|userId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "user": {
      "_id": "5e2bece8d606e72a7f38402f",
      "gender": "m",
      "name": "黯淡武官",
      "slogan": "22222222222",
      "title": "萌新",
      "verified": false,
      "exp": 560,
      "level": 2,
      "avatar": {
        "originalName": "avatar.jpg",
        "path": "f6d5a28f-4b32-4c4b-8ac5-c396cbea0eb6.jpg",
        "fileServer": "https://storage1.picacomic.com"
      }
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» user|object|true|none||none|
|»»» _id|string|true|none||none|
|»»» gender|string|true|none||none|
|»»» name|string|true|none||none|
|»»» slogan|string|true|none||none|
|»»» title|string|true|none||none|
|»»» verified|boolean|true|none||none|
|»»» exp|integer|true|none||none|
|»»» level|integer|true|none||none|
|»»» avatar|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|

## PUT 修改头衔

PUT /users/{userId}/title

无法请求，怀疑哔咔已经弃用，或者用ip限制

> Body 请求参数

```json
{
  "title": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|userId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» title|body|string| 是 |哔咔的头衔|

> 返回示例

> 成功

```json
{
  "code": 400,
  "error": "1015",
  "message": "invalid request",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## GET 获取收藏列表

GET /users/favourite

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|s|query|string| 否 |排序,可选：ua(默认) dd(新到旧) da(旧到新) ld(爱心最多) vd(绅士指数最多)|
|page|query|integer| 否 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comics": {
      "pages": 6,
      "total": 116,
      "docs": [
        {
          "_id": "5c3b684c49be9f13b64caf9d",
          "title": "放課後の体育倉庫2",
          "author": "紺色くらぶ (あさん)",
          "pagesCount": 24,
          "epsCount": 1,
          "finished": false,
          "categories": [
            "全彩",
            "短篇",
            "SM"
          ],
          "thumb": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "69bbd203-f8fd-4d8c-afa5-4dfe31708edf.jpg",
            "originalName": "001.jpg"
          },
          "totalViews": 341592,
          "totalLikes": 4312,
          "likesCount": 4312
        },
        {
          "_id": "5c388a891edbd91f42577bc7",
          "title": "美柑監禁陵辱 (To LOVEる -とらぶる-)",
          "author": "ふみひろ",
          "pagesCount": 9,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "全彩",
            "同人",
            "短篇",
            "SM",
            "強暴"
          ],
          "thumb": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "b9c88d22-0746-4bc2-9acb-afaf6626610c.jpg",
            "originalName": "001.jpg"
          },
          "totalViews": 542714,
          "totalLikes": 5383,
          "likesCount": 5383
        },
        {
          "_id": "5ac1a953bc0ace1e6c18d079",
          "title": "玩具 ",
          "author": "aki99",
          "pagesCount": 100,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "全彩",
            "同人",
            "CG雜圖",
            "妹妹系"
          ],
          "thumb": {
            "originalName": "1.jpg",
            "path": "4d43a71d-b34a-4e54-ac09-8cf24b630612.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "totalLikes": 74936,
          "totalViews": 4177402,
          "likesCount": 74936
        },
        {
          "_id": "62ab4372074fd3702c773885",
          "title": "[Pixiv] zds (14094820)",
          "author": "zds",
          "totalViews": 29596,
          "totalLikes": 224,
          "pagesCount": 91,
          "epsCount": 1,
          "finished": false,
          "categories": [
            "全彩",
            "同人",
            "CG雜圖"
          ],
          "thumb": {
            "originalName": "82710104_p0.jpg",
            "path": "tobs/edade1f2-1e4b-4157-a795-d7aa0620a34a.jpg",
            "fileServer": "https://storage-b.picacomic.com"
          },
          "likesCount": 224
        },
        {
          "_id": "58f750a440e91f077315f763",
          "title": "緊縛調教婦女監禁施設",
          "author": "黒りりの部屋 (lilish)",
          "pagesCount": 221,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "長篇",
            "全彩",
            "CG雜圖",
            "妹妹系"
          ],
          "thumb": {
            "originalName": "0001.jpg",
            "path": "2017e04d-d0e8-4b4f-ac17-5ec52a24eac3.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "totalViews": 957281,
          "totalLikes": 9630,
          "likesCount": 9630
        },
        {
          "_id": "5ee50f99e562b824af100518",
          "title": "(C95)戦艦 ウォースパイト 尋問調書 (艦隊これくしょん -艦これ-)",
          "author": "もなかうどん (モニカノ)",
          "totalViews": 215606,
          "totalLikes": 3114,
          "pagesCount": 23,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "短篇",
            "同人",
            "全彩",
            "艦隊收藏",
            "SM"
          ],
          "thumb": {
            "originalName": "000.jpg",
            "path": "48a156e5-3c0e-4bae-9484-35014f7b6aab.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 3114
        },
        {
          "_id": "61f0157c5f4a1b6a46020e70",
          "title": "姦落の風紀委員長（汉化）",
          "author": "Atelier Curlicue",
          "totalViews": 1137304,
          "totalLikes": 3884,
          "pagesCount": 81,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "全彩",
            "長篇",
            "強暴",
            "CG雜圖"
          ],
          "thumb": {
            "originalName": "00_0.png",
            "path": "34e11c0e-0d88-4128-b428-f46d88e01fa5.png",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 3884
        },
        {
          "_id": "61f153ee6d3cdf378d5c80e1",
          "title": "[re:]Rape",
          "author": "ホロナミンZ (ホロナミン)",
          "totalViews": 570525,
          "totalLikes": 5038,
          "pagesCount": 59,
          "epsCount": 1,
          "finished": false,
          "categories": [
            "強暴",
            "短篇"
          ],
          "thumb": {
            "originalName": "scan_0001.jpg",
            "path": "a6970564-8975-4338-ab09-6e08c090e3d9.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 5038
        },
        {
          "_id": "61eeb2bdd7ae416a54a5ae54",
          "title": "(C99)  駆逐艦 村雨 尋問調書 (艦隊これくしょん -艦これ-) [中国翻訳]",
          "author": "もなかうどん (モニカノ)",
          "totalViews": 153016,
          "totalLikes": 2427,
          "pagesCount": 20,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "全彩",
            "短篇",
            "同人",
            "艦隊收藏",
            "SM",
            "非人類"
          ],
          "thumb": {
            "originalName": "01_001.jpg",
            "path": "1d58b80c-b80e-4f8a-825b-6ec2b7464561.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 2427
        },
        {
          "_id": "61fcd4a0cced93501a8e5fdc",
          "title": "ちょびっとアブノーマルなロリっ娘クラブ",
          "author": "陰毛チョレギサラダ (陰ちょれ)",
          "totalViews": 13853,
          "totalLikes": 157,
          "pagesCount": 26,
          "epsCount": 1,
          "finished": false,
          "categories": [
            "短篇",
            "生肉"
          ],
          "thumb": {
            "originalName": "_001.jpg",
            "path": "202f0b6c-6f6b-440b-9d7d-c1fc89d1f797.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 157
        },
        {
          "_id": "5cfb9ae4c938292951d6821e",
          "title": "突発性勃起症候群～自慰不全を添えて～ [中国翻訳]",
          "author": "かわはぎ亭",
          "pagesCount": 93,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "純愛",
            "長篇"
          ],
          "thumb": {
            "originalName": "000_.jpg",
            "path": "d857b725-a657-4744-96f7-84b14dec5216.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "totalViews": 730495,
          "totalLikes": 7034,
          "likesCount": 7034
        },
        {
          "_id": "6101a185b2ce8a24cbee088a",
          "title": "牝牛ミルクタンク (Granblue Fantasy) [中国翻訳]",
          "author": "NA●SI",
          "totalViews": 55831,
          "totalLikes": 374,
          "pagesCount": 36,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "全彩",
            "短篇",
            "同人",
            "CG雜圖",
            "碧藍幻想"
          ],
          "thumb": {
            "originalName": "01_1.jpg",
            "path": "3cbffc29-d725-4613-9cd2-001853c0c64d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 374
        },
        {
          "_id": "5f96f7ef00de9a1d14b293a4",
          "title": "[Pixiv] Yuri-Yumi (9175524)",
          "author": "Yuri-Yumi",
          "totalViews": 345461,
          "totalLikes": 2553,
          "pagesCount": 79,
          "epsCount": 1,
          "finished": false,
          "categories": [
            "全彩",
            "同人",
            "CG雜圖"
          ],
          "thumb": {
            "originalName": "71239890_p0_Tribute_from_Embla.jpg",
            "path": "e36bf947-31d5-43fb-9798-94c28d9d3087.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 2553
        },
        {
          "_id": "5c9f0bebf5222946dbce00b8",
          "title": "通販少女 -妹といっしょ。 episode 2-",
          "author": "milkberry (如月みゆ)",
          "pagesCount": 28,
          "epsCount": 1,
          "finished": false,
          "categories": [
            "全彩",
            "短篇",
            "生肉"
          ],
          "thumb": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "492d854d-ed59-47e3-8a50-3c2ac8f3c10f.jpg",
            "originalName": "001.jpg"
          },
          "totalViews": 67651,
          "totalLikes": 911,
          "likesCount": 911
        },
        {
          "_id": "5c9f0c11471d9246e1a4b546",
          "title": "skmzx5",
          "author": "milkberry (如月みゆ)",
          "pagesCount": 55,
          "epsCount": 2,
          "finished": false,
          "categories": [
            "全彩",
            "短篇"
          ],
          "thumb": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "84c55152-b6ac-46d8-9e06-edcfe962add0.jpg",
            "originalName": "01_01.jpg"
          },
          "totalViews": 120900,
          "totalLikes": 1646,
          "likesCount": 1646
        },
        {
          "_id": "5ca23e4e6298271c0a759d5c",
          "title": "skmzx3",
          "author": "milkberry (如月みゆ)",
          "pagesCount": 25,
          "epsCount": 1,
          "finished": false,
          "categories": [
            "全彩",
            "短篇"
          ],
          "thumb": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "72191858-9add-43e2-a17c-5fbca85d9979.jpg",
            "originalName": "00000000.jpg"
          },
          "totalViews": 233141,
          "totalLikes": 2517,
          "likesCount": 2517
        },
        {
          "_id": "5c209149ebb4a71a74544bab",
          "title": "(C91) 放課後のないしょ",
          "author": "milkberry (如月みゆ)",
          "pagesCount": 25,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "全彩",
            "短篇"
          ],
          "thumb": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "55b6c774-fb88-45ea-83ee-ea59953a39ff.jpg",
            "originalName": "20170721_02506.jpg"
          },
          "totalViews": 341872,
          "totalLikes": 5202,
          "likesCount": 5202
        },
        {
          "_id": "5cff52f547124a60a078dc5b",
          "title": "JC催眠メス犬化計画",
          "author": "milkberry、たまかけ屋 (如月みゆ、たまかけ)",
          "pagesCount": 45,
          "epsCount": 2,
          "finished": false,
          "categories": [
            "全彩",
            "短篇",
            "SM"
          ],
          "thumb": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "4eba0d9c-8523-4e6b-85e8-dd3281db99e1.jpg",
            "originalName": "000.jpg"
          },
          "totalLikes": 11213,
          "totalViews": 721878,
          "likesCount": 11213
        },
        {
          "_id": "5fa179d97193765a84d6127c",
          "title": "(秋葉原超同人祭) 種付けおじさんと被虐JC●●二穴責め調教",
          "author": "milkberry (如月みゆ)",
          "totalViews": 675919,
          "totalLikes": 13200,
          "pagesCount": 28,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "短篇",
            "全彩",
            "SM",
            "妹妹系"
          ],
          "thumb": {
            "originalName": "000.jpg",
            "path": "f787574e-4142-48ac-997b-bcb3a5e10a14.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 13200
        },
        {
          "_id": "5dd8163dafbdaf673373a53d",
          "title": "虐待用性奴隷の妹。 [中国翻訳]",
          "author": "春夏秋冬",
          "totalViews": 1018110,
          "totalLikes": 5564,
          "pagesCount": 50,
          "epsCount": 1,
          "finished": true,
          "categories": [
            "短篇",
            "全彩",
            "CG雜圖",
            "妹妹系",
            "SM"
          ],
          "thumb": {
            "originalName": "000.jpg",
            "path": "e1843693-3588-468f-a8a8-032d578b5e09.jpg",
            "fileServer": "https://storage1.picacomic.com"
          },
          "likesCount": 5564
        }
      ],
      "page": 1,
      "limit": 20
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comics|object|true|none||none|
|»»» pages|integer|true|none||none|
|»»» total|integer|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» title|string|true|none||none|
|»»»» author|string|true|none||none|
|»»»» pagesCount|integer|true|none||none|
|»»»» epsCount|integer|true|none||none|
|»»»» finished|boolean|true|none||none|
|»»»» categories|[string]|true|none||none|
|»»»» thumb|object|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»» totalViews|integer|true|none||none|
|»»»» totalLikes|integer|true|none||none|
|»»»» likesCount|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» limit|integer|true|none||none|

## POST 打卡

POST /users/punch-in

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "res": {
      "status": "ok",
      "punchInLastDay": "2022-07-05"
    }
  }
}
```

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "res": {
      "status": "fail"
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» res|object|true|none||none|
|»»» status|string|true|none||none|
|»»» punchInLastDay|string|true|none||none|

## PUT 重新设定忘记密码的问题和答案

PUT /users/update-qa

重新设定忘记密码的问题和答案

> Body 请求参数

```json
{
  "question1": "string",
  "question2": "string",
  "question3": "string",
  "answer1": "string",
  "answer2": "string",
  "answer3": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» question1|body|string| 是 |none|
|» question2|body|string| 是 |none|
|» question3|body|string| 是 |none|
|» answer1|body|string| 是 |none|
|» answer2|body|string| 是 |none|
|» answer3|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|

## PUT 修改昵称

PUT /users/update-id

> Body 请求参数

```json
{
  "email": "string",
  "name": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» email|body|string| 是 |哔咔账号|
|» name|body|string| 是 |新昵称|

> 返回示例

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## PUT 修改密码

PUT /users/password

修改哔咔登录密码

> Body 请求参数

```json
{
  "new_password": "string",
  "old_password": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» new_password|body|string| 是 |新密码|
|» old_password|body|string| 是 |旧密码|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|

# init

## GET 初始化

GET /init

可以等到一下有用的信息

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|platform|query|string| 否 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "isPunched": true,
    "latestApplication": {
      "_id": "5dc58b151e103c60e7663b12",
      "downloadUrl": "https://download.wikawika.xyz/apps/2.2.1.3.3.4_collections.apk",
      "updateContent": "【一般更新】\n\n1・新增漫畫推薦欄\n\n2・修改部份版本閃退問題\n\n後備下載連結\nhttps://download.wikawika.xyz/apps/2.2.1.3.3.4_collections.apk",
      "version": "2.2.1.3.3.4",
      "updated_at": "2019-11-08T15:38:45.706Z",
      "created_at": "2019-11-08T15:34:45.163Z",
      "apk": {
        "originalName": "2.2.1.3.3.4_collections.apk",
        "path": "4da05b12-3534-4b4d-b9bf-804de301d2e0.apk",
        "fileServer": "https://storage1.picacomic.com"
      }
    },
    "imageServer": "https://s3.picacomic.com/static/",
    "apiLevel": 22,
    "minApiLevel": 22,
    "categories": [
      {
        "_id": "5821859b5f6b9a4f93dbf6e9",
        "title": "嗶咔漢化"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d1",
        "title": "全彩"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cd",
        "title": "長篇"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6ca",
        "title": "同人"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6ce",
        "title": "短篇"
      },
      {
        "_id": "584ea1f45a44ac4f7dce3623",
        "title": "圓神領域"
      },
      {
        "_id": "58542b601b8ef1eb33b57959",
        "title": "碧藍幻想"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e5",
        "title": "CG雜圖"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e8",
        "title": "英語 ENG"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e0",
        "title": "生肉"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6de",
        "title": "純愛"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d2",
        "title": "百合花園"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e2",
        "title": "耽美花園"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e4",
        "title": "偽娘哲學"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d3",
        "title": "後宮閃光"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d4",
        "title": "扶他樂園"
      },
      {
        "_id": "5abb3fd683111d2ad3eecfca",
        "title": "單行本"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6da",
        "title": "姐姐系"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6db",
        "title": "妹妹系"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cb",
        "title": "SM"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d0",
        "title": "性轉換"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6df",
        "title": "足の恋"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cc",
        "title": "人妻"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d8",
        "title": "NTR"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d9",
        "title": "強暴"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d6",
        "title": "非人類"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6cf",
        "title": "艦隊收藏"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d7",
        "title": "Love Live"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6dc",
        "title": "SAO 刀劍神域"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e1",
        "title": "Fate"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6dd",
        "title": "東方"
      },
      {
        "_id": "59041d54ccc747074b47dae4",
        "title": "WEBTOON"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e3",
        "title": "禁書目錄"
      },
      {
        "_id": "5bd66e7e8ff47f7c46cf999d",
        "title": "歐美"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6e6",
        "title": "Cosplay"
      },
      {
        "_id": "5821859b5f6b9a4f93dbf6d5",
        "title": "重口地帶"
      }
    ],
    "notification": null,
    "isIdUpdated": true
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» isPunched|boolean|true|none||none|
|»» latestApplication|object|true|none||none|
|»»» _id|string|true|none||none|
|»»» downloadUrl|string|true|none||none|
|»»» updateContent|string|true|none||none|
|»»» version|string|true|none||none|
|»»» updated_at|string|true|none||none|
|»»» created_at|string|true|none||none|
|»»» apk|object|true|none||none|
|»»»» originalName|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» fileServer|string|true|none||none|
|»» imageServer|string|true|none||none|
|»» apiLevel|integer|true|none||none|
|»» minApiLevel|integer|true|none||none|
|»» categories|[object]|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|
|»» notification|null|true|none||none|
|»» isIdUpdated|boolean|true|none||none|

# collections

## GET 推荐

GET /collections

哔咔首页的 本子妹推薦(New) 本子母推薦(貧乳)

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "collections": [
      {
        "title": "本子妹推薦(New)",
        "comics": [
          {
            "_id": "5d712eed1adf787c3a55126f",
            "title": " シスアナ2 [中国翻訳] [DL版]",
            "author": "In The Sky (中乃空)",
            "totalViews": 355147,
            "totalLikes": 5998,
            "pagesCount": 35,
            "epsCount": 1,
            "finished": true,
            "categories": [
              "短篇",
              "妹妹系"
            ],
            "thumb": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "f6fe0976-e618-45c0-9a03-ed0a282d188e.jpg",
              "originalName": "01_001.jpg"
            }
          },
          {
            "_id": "5ea3a16eb724bb488487b8e1",
            "title": "本当にいた!!時間停止おじさん",
            "author": "スパイシーラブスヘブン (かみ田)",
            "totalViews": 333132,
            "totalLikes": 3300,
            "pagesCount": 53,
            "epsCount": 2,
            "finished": false,
            "categories": [
              "短篇",
              "強暴"
            ],
            "thumb": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "2950d4c2-5b39-45c7-afe1-5b63ed0dbc18.jpg",
              "originalName": "000.jpg"
            }
          },
          {
            "_id": "62bfe487b0d3dc60dfeaa8e4",
            "title": " 璃月の特殊审讯",
            "author": "Ricky",
            "totalViews": 53634,
            "totalLikes": 927,
            "pagesCount": 13,
            "epsCount": 1,
            "finished": true,
            "categories": [
              "全彩",
              "短篇",
              "同人",
              "純愛",
              "後宮閃光"
            ],
            "thumb": {
              "originalName": "99423469_p0.jpg",
              "path": "tobs/eac1de5e-2c15-4dc5-bc6e-af659050676a.jpg",
              "fileServer": "https://storage-b.picacomic.com"
            }
          },
          {
            "_id": "62c1c4b82f2e9338c6595e90",
            "title": "友情劣情百合発情",
            "author": "たまランド (たまの父)",
            "totalViews": 13766,
            "totalLikes": 392,
            "pagesCount": 41,
            "epsCount": 1,
            "finished": true,
            "categories": [
              "短篇",
              "百合花園",
              "生肉"
            ],
            "thumb": {
              "originalName": "02.jpg",
              "path": "tobs/d37a68e5-fec2-41cb-ae02-6e03e75b532c.jpg",
              "fileServer": "https://storage-b.picacomic.com"
            }
          }
        ]
      },
      {
        "title": "本子母推薦(貧乳)",
        "comics": [
          {
            "_id": "5ea3a16eb724bb488487b8e1",
            "title": "本当にいた!!時間停止おじさん",
            "author": "スパイシーラブスヘブン (かみ田)",
            "totalViews": 333132,
            "totalLikes": 3300,
            "pagesCount": 53,
            "epsCount": 2,
            "finished": false,
            "categories": [
              "短篇",
              "強暴"
            ],
            "thumb": {
              "fileServer": "https://storage1.picacomic.com",
              "path": "2950d4c2-5b39-45c7-afe1-5b63ed0dbc18.jpg",
              "originalName": "000.jpg"
            }
          },
          {
            "_id": "5eac0c4ad01b8847faeb07ef",
            "title": "(C97)妹とはじめました [中国翻訳]",
            "author": "たまかけ屋 (たまかけ)",
            "totalViews": 156741,
            "totalLikes": 2677,
            "pagesCount": 37,
            "epsCount": 1,
            "finished": true,
            "categories": [
              "短篇",
              "純愛",
              "妹妹系",
              "全彩"
            ],
            "thumb": {
              "originalName": "000.jpg",
              "path": "fc19fda1-a0f3-4c4a-a661-628997c61469.jpg",
              "fileServer": "https://storage1.picacomic.com"
            }
          },
          {
            "_id": "625fe32d2fbc8219d79f1370",
            "title": "(C99)  先生の赤ちゃんミルクはアリスの人工子宮で温めます! (ブルーアーカイブ) [中国翻訳]",
            "author": "Fatima Cigarette (滝まくら)",
            "totalViews": 81900,
            "totalLikes": 716,
            "pagesCount": 20,
            "epsCount": 1,
            "finished": true,
            "categories": [
              "短篇",
              "同人",
              "純愛",
              "妹妹系"
            ],
            "thumb": {
              "originalName": "000.jpg",
              "path": "tobs/5e423e45-9ee3-487f-bbfb-e119e2dd5747.jpg",
              "fileServer": "https://storage-b.picacomic.com"
            }
          },
          {
            "_id": "62c1c4b82f2e9338c6595e90",
            "title": "友情劣情百合発情",
            "author": "たまランド (たまの父)",
            "totalViews": 13766,
            "totalLikes": 392,
            "pagesCount": 41,
            "epsCount": 1,
            "finished": true,
            "categories": [
              "短篇",
              "百合花園",
              "生肉"
            ],
            "thumb": {
              "originalName": "02.jpg",
              "path": "tobs/d37a68e5-fec2-41cb-ae02-6e03e75b532c.jpg",
              "fileServer": "https://storage-b.picacomic.com"
            }
          }
        ]
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# keywords

## GET 搜索关键字（大家都在搜）

GET /keywords

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "keywords": [
      "3D",
      "精靈",
      "蘿莉",
      "NTR",
      "全彩",
      "原神",
      "強暴",
      "觸手",
      "調教",
      "阿嘿顏",
      "懷孕",
      "人獸交",
      "正太",
      "人妻",
      "開迷你車"
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» keywords|[string]|true|none||none|

# banners

## GET 横幅（广告）

GET /banners

就是哔咔首页上的广告

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "banners": [
      {
        "_id": "601d3abdcfeaee28f8d8cb72",
        "title": "拯救嗶咔，點擊！",
        "shortDescription": "逆王傳說: 入侵女兒國",
        "_game": "601d3abdcfeaee28f8d8cb72",
        "type": "game",
        "thumb": {
          "fileServer": "https://ad-channel.wikawika.xyz",
          "path": "dQdRUB_0HFSn8j9QOeoa9.jpg",
          "originalName": "banner_game.gif"
        }
      },
      {
        "_id": "qkwejqkwe",
        "title": "拯救嗶咔，點擊廣告！",
        "shortDescription": "完美嫩乳!",
        "type": "web",
        "link": "https://ad-channel.wikawika.xyz/redirect/zone_3",
        "thumb": {
          "fileServer": "https://ad-channel.wikawika.xyz",
          "path": "3zwRd3_qE0oLS2ZiyL36p.jpg",
          "originalName": "image.jpg"
        }
      },
      {
        "_id": "dsfsdf",
        "title": "拯救嗶咔，點擊廣告！",
        "shortDescription": "😘 ",
        "type": "ads",
        "link": "https://ad-channel.wikawika.xyz/android/home_banner",
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "369ca47f-e015-4acf-b2e3-cb4800c876f7.jpg",
          "originalName": "image.jpg"
        }
      },
      {
        "_id": "dsfsdf1",
        "title": "拯救嗶咔，點擊廣告！",
        "shortDescription": "😘 ",
        "type": "ads",
        "link": "https://ad-channel.wikawika.xyz/android/home_banner_2",
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "369ca47f-e015-4acf-b2e3-cb4800c876f7.jpg",
          "originalName": "image.jpg"
        }
      },
      {
        "_id": "fjg1",
        "title": "拯救嗶咔，點擊廣告！",
        "shortDescription": "點就對了!",
        "type": "web",
        "link": "https://ad-channel.wikawika.xyz/redirect/zone_4",
        "thumb": {
          "fileServer": "https://ad-channel.wikawika.xyz",
          "path": "ANECmINT-izcsF208QM2y.jpg",
          "originalName": "image.jpg"
        }
      },
      {
        "_id": "toBe3",
        "title": "拯救嗶咔，點擊廣告！",
        "shortDescription": "😘 ",
        "type": "ads",
        "link": "https://ad-channel.wikawika.xyz/android/home_banner_4",
        "thumb": {
          "fileServer": "https://storage1.picacomic.com",
          "path": "369ca47f-e015-4acf-b2e3-cb4800c876f7.jpg",
          "originalName": "image.jpg"
        }
      },
      {
        "_id": "toBe4",
        "title": "拯救嗶咔，點擊廣告！",
        "shortDescription": "來征服我吧!",
        "type": "web",
        "link": "https://ad-channel.wikawika.xyz/redirect/zone_5",
        "thumb": {
          "fileServer": "https://ad-channel.wikawika.xyz",
          "path": "bI8uZ7Pdycuet_IBuh64O.jpg",
          "originalName": "image.jpg"
        }
      },
      {
        "_id": "toBe5",
        "title": "拯救嗶咔，點擊廣告！",
        "shortDescription": "",
        "type": "web",
        "link": "https://ad-channel.wikawika.xyz/redirect/zone_27",
        "thumb": {
          "fileServer": "https://ad-channel.wikawika.xyz",
          "path": "i4zcMez4tJPktTflcRwgq.jpg",
          "originalName": "image.jpg"
        }
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» banners|[object]|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|
|»»» shortDescription|string|true|none||none|
|»»» _game|string|false|none||none|
|»»» type|string|true|none||none|
|»»» thumb|object|true|none||none|
|»»»» fileServer|string|true|none||none|
|»»»» path|string|true|none||none|
|»»»» originalName|string|true|none||none|
|»»» link|string|true|none||none|

# chat

## GET 聊天室

GET /chat

哔咔的聊天室，没啥用

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "chatList": [
      {
        "title": "嗶咔日常交流廣場",
        "description": "這是一個讓大家聊日常的聊天廣場，歡迎大家加入聊天，讓我們一起聊日常吧！",
        "url": "https://chat-public.wikawika.xyz",
        "avatar": "https://pica-pica.wikawika.xyz/images/chat_normal.jpg?v=2"
      },
      {
        "title": "嗶咔學習教室",
        "description": "這是一個讓大家互相學習的地方，在這個地方你能學到天文、地理、生物、科學等等的知識，歡迎大家一起學習！這個教室還有很多小遊戲，讓你得到很多樂趣樂趣喔！還有一些秘密功能，讓你可以自己發揮！",
        "url": "https://chat-old.wikawika.xyz",
        "avatar": "https://pica-pica.wikawika.xyz/images/chat_game.jpg?v=2"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» chatList|[object]|true|none||none|
|»»» title|string|true|none||none|
|»»» description|string|true|none||none|
|»»» url|string|true|none||none|
|»»» avatar|string|true|none||none|

# pica-apps

## GET 哔咔的小程序

GET /pica-apps

在哔咔分区上面的那些小程序

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "apps": [
      {
        "title": "嗶咔包養",
        "url": "https://donate.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/support-app.jpg",
        "showTitleBar": false,
        "description": "透過 BitCoin 支援嗶咔漫畫"
      },
      {
        "title": "嗶咔商店",
        "url": "https://online-shop-web.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/picacomic-shop.jpg",
        "showTitleBar": false,
        "description": "嗶咔商店，買買買!"
      },
      {
        "title": "嗶咔鍋貼",
        "url": "https://post-web.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/picacomic-post.jpg",
        "showTitleBar": false,
        "description": "嗶咔鍋貼，一起讓騎士們分享生活和快樂的地方"
      },
      {
        "title": "嗶咔小電影",
        "url": "https://av.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/movie-app.jpg",
        "showTitleBar": false,
        "description": "精彩小電影讓你看到飽嗎？！"
      },
      {
        "title": "嗶咔小里番",
        "url": "https://h.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/h-app.jpg",
        "showTitleBar": false,
        "description": "里番之家"
      },
      {
        "title": "嗶咔小黃油",
        "url": "https://game.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/game-app.jpg",
        "showTitleBar": false,
        "description": "電腦小黃油介紹"
      },
      {
        "title": "嗶咔小禮物",
        "url": "https://gift-web.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/picacomic-gift.jpg",
        "showTitleBar": false,
        "description": "福利盡在嗶咔小禮物"
      },
      {
        "title": "嗶咔畫廊",
        "url": "https://paint-web.wikawika.xyz",
        "icon": "https://pica-pica.wikawika.xyz/images/picacomic-paint.jpg",
        "showTitleBar": false,
        "description": "由著名畫帥繪畫的嗶咔相關作品"
      }
    ]
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» apps|[object]|true|none||none|
|»»» title|string|true|none||none|
|»»» url|string|true|none||none|
|»»» icon|string|true|none||none|
|»»» showTitleBar|boolean|true|none||none|
|»»» description|string|true|none||none|

# applications

## GET 哔咔更新信息

GET /applications

应该是哔咔的更新信息

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|platform|query|string| 否 |none|
|page|query|integer| 否 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "applications": {
      "docs": [
        {
          "_id": "5dc58b151e103c60e7663b12",
          "downloadUrl": "https://download.wikawika.xyz/apps/2.2.1.3.3.4_collections.apk",
          "updateContent": "【一般更新】\n\n1・新增漫畫推薦欄\n\n2・修改部份版本閃退問題\n\n後備下載連結\nhttps://download.wikawika.xyz/apps/2.2.1.3.3.4_collections.apk",
          "version": "2.2.1.3.3.4",
          "created_at": "2019-11-08T15:34:45.163Z",
          "apk": {
            "originalName": "2.2.1.3.3.4_collections.apk",
            "path": "4da05b12-3534-4b4d-b9bf-804de301d2e0.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5daffa0ff07d0f4d8ac08037",
          "version": "2.2.1.2.3.3",
          "updateContent": "【\b強制更新】\n\n由於服務器君的問題，因此要強制更新一次。\n\n後備連結：\nhttps://app.wakamoment.tk/apps/2.2.1.2.3.3.apk\nhttps://download.woyeahgo.tk/apps/2.2.1.2.3.3.apk\nhttp://www.cnpicacomic.com",
          "downloadUrl": "https://download.woyeahgo.tk/apps/2.2.1.2.3.3.apk",
          "created_at": "2019-10-23T06:58:23.552Z",
          "apk": {
            "originalName": "2.2.1.2.3.3.apk",
            "path": "dcfc8bae-d536-419e-ace8-40bccb79ccfe.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d6f7b519081d2399eed61ac",
          "version": "2.2.1.0.1.2",
          "updateContent": "【\b嗶咔帳號更新】\n\n由於私隱及安全問題，嗶咔推出「一次性」更新用戶帳號及名稱。\n更新後，用戶「必需」更改登入帳號（郵件），用戶可以選擇性更改匿稱一次。\n\n更新內容：\n\n1．一次性更改「帳號」及「匿稱」\n\n2．更改「忘記密碼」流程\n\n3．修改「進階搜尋」排序顯示錯誤\n\n4．修改留言功能\n\n\n\n無法下載新版本的可到以下連結：\nhttps://app.wakamoment.tk/apps/2.2.1.0.1.2_updateID_renewfix.apk\n",
          "downloadUrl": "https://app.wakamoment.tk/apps/2.2.1.0.1.2_updateID_renewfix.apk",
          "created_at": "2019-09-04T08:52:33.900Z",
          "apk": {
            "originalName": "2.2.1.0.1.2_updateID_renewfix.apk",
            "path": "b289459f-5adf-46f0-a8db-7eb79619c1a7.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5d3b0a8420500f552a788ee3",
          "version": "2.2.0.0.1.1",
          "updateContent": "【重大更新】\n\n為了迎接 3.0 的來臨，未來會慢慢下放新功能。\n\n\n新功能：\n\n1．進階搜尋功能加入排序及分類\n\n2．漫畫列表加入排序\n\n3．新增「看了這本子的人也在看」\n\n4．新增「留言舉報」功能\n\n5．新增「通知」功能（在首頁右上角開始）\n\n\n嗶咔會繼續不定時更新版本，多謝各位支持。\n\n如無法下載，可按以下連結更新：\nhttps://app.wakamoment.tk/apps/2.2.0.0.1.1.apk\n",
          "downloadUrl": "https://app.wakamoment.tk/apps/2.2.0.0.1.1.apk",
          "created_at": "2019-07-26T14:13:24.090Z",
          "apk": {
            "originalName": "2.2.0.0.1.1_new_final.apk",
            "path": "dc904633-5561-4c91-ae4c-2ac6c5a6cb5c.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5cde6843952e365282e84f1b",
          "version": "2.1.0.8",
          "updateContent": "更年期到了，由於垃圾服務器君的失誤，引致分流2和分流3無法正常使用，需要更新解決。\n\n\n更新內容：\n\n1．修復分流\n\n2．更新分類\n\n3．改善小電視及小電影\n\n\n無法更新的，請使用後備下載連結：\nhttps://app.wakamoment.tk/apps/2.1.0.8_update_web.apk\n\n嗶咔3.0 如期進行中，有生之年將會推出，請密切期待。",
          "downloadUrl": "https://app.wakamoment.tk/apps/2.1.0.8_update_web.apk",
          "created_at": "2019-05-17T07:52:35.912Z",
          "apk": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "db23042b-fc34-4030-86fc-d3c62e8f9447.apk",
            "originalName": "2.1.0.8_update_web.apk"
          }
        },
        {
          "_id": "5b6ac4782c04e24caad1b069",
          "version": "2.1.0.7",
          "updateContent": "3.0 的開發如火如荼，\n\n2.0的更新也進入尾聲\b。\n\n為了 3.0 的來臨，開發團隊會在2.0慢慢加入新功能進行測試。\n\n\n更新內容：\n\n1・ 嗶咔萌約（新的測試聊天功能）\n\n2・自定小程式（可同時開啟聊天室／小程式）\n\n\n3.0 功能預告：\n\n「進階搜尋」和「模糊搜尋」是必然會有的\n\n收藏可以有資料夾，還有⋯⋯",
          "downloadUrl": "https://app.wakamoment.tk/apps/2.1.0.7_anonymous_chat.apk",
          "created_at": "2018-08-08T10:22:48.829Z",
          "apk": {
            "fileServer": "https://storage1.picacomic.com",
            "path": "c0efd7a9-b598-46dd-ae7b-95af30e54d15.apk",
            "originalName": "2.1.0.7_anonymous_chat.apk"
          }
        },
        {
          "_id": "5abd144dbdb6de2362ebc7d2",
          "version": "2.1.0.5",
          "updateContent": "是時候更新了。\n更新什麼？\n\n1・新增「嗶咔小程式」\n\n2・新增聊天室「文字顏色修正」功能\n\n\n無法更新的，請前往：\nhttps://wakamoment.tk/apps/2.1.0.5_pica.apk\n",
          "downloadUrl": "https://app.wakamoment.tk/apps/2.1.0.5_pica.apk",
          "created_at": "2018-03-29T16:29:01.376Z",
          "apk": {
            "originalName": "2.1.0.5_pica.apk",
            "path": "6ebc940a-962f-4ebc-80ba-4a3e77149a40.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5a8152b262ed6d09d3aa4de2",
          "version": "2.1.0.4",
          "updateContent": "新春節快樂。\n\n由於服務器君的失誤，現在已經修復下載功能。\n\n\n更新內容：\n\n1. 加入新分流。\n\n2. 更新下載功能。\n\n無法下載安卓的，請到：\nhttps://wakamoment.tk/2.1.0.4_picacg.apk\n\n\n\nIOS已經上線，需要要紳士們，可搜尋「WAIFU」。\n【注意】請利用非中國區域下載，不然是找不到的。",
          "downloadUrl": "https://app.wakamoment.tk/2.1.0.4_picacg.apk",
          "created_at": "2018-02-12T08:39:14.536Z",
          "apk": {
            "originalName": "2.1.0.4_update_channel.apk",
            "path": "4a7a995b-445c-4fa4-9e08-1b3f30fa482d.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5a4f3079e037b012b92cf689",
          "version": "2.1.0.3",
          "updateContent": "由於服務器君的失誤，大部份舊版本的用戶都不能連接新版本。\n下載新版本而不能連接的紳士們，請連接\n\n＞＞＞  分流【 2 】  ＜＜＜\n\n\n更新內容：\n\n1. 修改支持嗶咔\n\n2. 服務器黑科技加速功能\n\n3. 加入分流系統\n\n\n無法下載的，請到：\nhttps://app.wakamoment.tk/2.1.0.3_picacg_2.apk",
          "downloadUrl": "https://app.wakamoment.tk/2.1.0.3_picacg_2.apk",
          "created_at": "2018-01-05T07:59:53.008Z",
          "apk": {
            "originalName": "2.1.0.3_picacg_2.apk",
            "path": "581fa5bc-4cd1-4f2d-8005-e3d45f65c068.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "5965e6ad83a9544bd84656b3",
          "version": "2.1.0.2",
          "updateContent": "如不能載圖，可下載本版本。\n\n更新內容：\n\n1. 改善部份無法載圖問題\n\n2. 修改「聊天室」功能\n\n3. 新增「聊天室」\n\n\n\n\n如不能下載更新版本，可試以下方法：\n\n1. 使用其他「瀏覽器」打開\n\n2. 點擊「鏡像下載」\n\n3. 前往「https://picacomic.com」下載\n\n4. 前往「http://cn.picacomiccn.com」下載",
          "downloadUrl": "http://cn.picacomiccn.com/down/PicaComic_beta_test_2.1.0.2.apk",
          "created_at": "2017-07-12T09:06:53.066Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.1.0.2.apk",
            "path": "92a10039-7158-4d80-b771-f17942f265da.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "595e66a8bdae5e511c0c936a",
          "version": "2.1.0.1",
          "downloadUrl": "http://cn.picacomiccn.com/down/PicaComic_beta_test_2.1.0.1.apk",
          "updateContent": "【重大更新】－ 是次版本必須更新\n（v2.1.0.0或以上）\n\n【v2.1.0.1 修改更新提示問題】\n\n如不能下載更新版本，可試以下方法：\n\n1. 使用其他「瀏覽器」打開\n\n2. 點擊「鏡像下載」\n\n3. 前往「https://picacomic.com」下載\n\n4. 前往「http://cn.picacomiccn.com」下載\n\n\n\n更新內容：（v2.1.0.0）\n\n1. 改善安全「性」\n\n2. 配合「黑」科技加速裝置，載圖速度上升（-123% ~25%）\n註：因人而異\n\n3. 新增「WETOON」封印\n\n4. 新增「封印」提示",
          "created_at": "2017-07-06T16:34:48.765Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.1.0.1.apk",
            "path": "69b5b092-dccc-4b6e-99bb-5427cccd627c.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "595e13c8c2dc3b26546b5d2d",
          "version": "2.1.0.0",
          "updateContent": "【如果你更新了，還出現這個更新訊息，請把它無視，我們會盡快修正問題】\n\n【重大更新】－ 是次版本必須更新\n\n如不能下載更新版本，可試以下方法：\n\n1. 使用其他「瀏覽器」打開\n\n2. 點擊「鏡像下載」\n\n3. 前往「https://picacomic.com」下載\n\n4. 前往「http://cn.picacomiccn.com」下載\n\n\n\n更新內容：\n\n1. 改善安全「性」\n\n2. 配合「黑」科技加速裝置，載圖速度上升（-23% ~256%）\n註：因人而異\n\n3. 新增「WETOON」封印\n\n4. 新增「封印」提示",
          "downloadUrl": "http://cn.picacomiccn.com/down/PicaComic_beta_test_2.1.0.0.apk",
          "created_at": "2017-07-06T10:41:12.581Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.1.0.0.apk",
            "path": "68adeb92-2379-4fa8-9257-64bc683c9a9c.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "59417a74a083bf10108dc6f3",
          "version": "2.0.3.18",
          "updateContent": "【繼續嗶咔小更新】\n\n距離3.0還有一段路要走，繼續更新2.0吧。\n\n\n\n更新內容：\n\n1. 加入修改「個人介紹」功能\n\n2. 加入查看「個人介紹」功能\n\n3. 修改聊天室介面\n\n4. 加入「稱號」\n\n5. 修復「偉論」跳頁的問題\n\n\n官方網站：\nhttp://www.picacomic.com",
          "created_at": "2017-06-14T18:03:32.673Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.18.apk",
            "path": "919bd163-6ebb-4f67-a164-55a9e21b5071.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "593a74964a4c825e97456781",
          "version": "2.0.3.17",
          "updateContent": "【繼續嗶咔小更新】\n\n由於 2.0.3.16 不支援安卓系統5.0以下的手機，所以馬上做了新的更新版。\n\n\n\n更新內容（2.0.3.17）：\n\n1. 修正「主題顏色」問題\n\n2. 加入「置頂偉論」\n\n\n\n更新內容（2.0.3.16）：\n\n1. 新增「主題顏色」（安卓系統5.0以上）\n\n2. 重新加入「嗶咔留言板」\n\n3. 優化「分類頁面」的返回操作\n\n\n\n紳士們可到官網下載：\nhttps://www.picacomic.com\n\n中國官網：\nhttp://cn.picacomiccn.com",
          "downloadUrl": "http://cn.picacomiccn.com/PicaComic_beta_test_2.0.3.17.apk",
          "created_at": "2017-06-09T10:12:38.144Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.17.apk",
            "path": "48ef42db-b804-4608-9e24-9924d355a503.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "59312ba5c0103f66242c92b1",
          "version": "2.0.3.15",
          "updateContent": "【安卓嗶咔】努力修問題中：\n\n更新內容：\n\n1. 部份漫畫無法進入內容頁問題\n（因為部份騎士沒有上傳頭像喔～）\n\n2. 修改「更多章節」問題\n\n3. 修改排行榜「返回」問題\n\n4. 修改「漫畫瀏覽器」下一章沒有回頂的問題\n\n5. 修改「漫畫瀏覽器」上一章和下一章的按鍵出現時間\n（修改後，2秒後會自動隱藏，但可以按的～）",
          "downloadUrl": "http://cn.picacomiccn.com/PicaComic_beta_test_2.0.3.15.apk",
          "created_at": "2017-06-02T09:11:01.915Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.15.apk",
            "path": "2321e2df-1609-404f-8b42-8940500b99a8.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "592c2365d82fc06827bb004c",
          "version": "2.0.3.14",
          "updateContent": "【很久沒有更新了】\n\n\n更新內容：\n\n1. 修改上傳騎士顯示方式（漫畫介紹）\n\n2. 修正EP顯示問題（漫畫介紹）\n\n3. 修正遊戲列表顯示問題\n\n4. 修改公告顯示條件\n\n5. 隱藏「無法\b取得亮度權限」\n\n6. 修正按作者搜尋導致玩壞嗶咔娘的問題",
          "downloadUrl": "http://www.picacomiccn.com/PicaComic_beta_test_2.0.3.14.apk",
          "created_at": "2017-05-29T13:34:29.623Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.14.apk",
            "path": "03ba5c54-a90c-440b-8e2a-0dbf76e3c73d.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58aff1769362b932f3316865",
          "version": "2.0.3.13",
          "updateContent": "嗶咔新版本，將更名為「仲夏版」。\n重生・下載・旺盛成長。\n\n\n更新內容－下載功能的三不：\n1. 下載功能「不能」修改目的地\n2. 下載功能「不會」提示下載缺頁的情況\n3. 下載功能「不能」同時下載\n\n下載功能還未完善，請等候日後更新。\n\n\n\n紳士們可到官網下載：\nhttps://www.picacomic.com\n\n中國官網：\nhttp://cn.picacomiccn.com",
          "downloadUrl": "http://www.picacomiccn.com/PicaComic_beta_test_2.0.3.13.apk",
          "created_at": "2017-02-24T08:40:22.756Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.13.apk",
            "path": "0b469c27-e490-40a0-b88e-6c17b0e9e9bc.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "586ccf6c5b1a2f7e69c814d4",
          "version": "2.0.3.11",
          "updateContent": "【是次版本，更新效能】\n\n下載功能，還是沒有的。再等一下，再等多一下！\n\n\n\n更新內容：\n\n1. 提升部份列表效能\n\n2. 提升部份載入漫畫效能\n\n3. 修改「流量提示」出現方式\n\n4. 調教一下聊天室廣告君\n\n\n紳士們可到官網下載：\nhttps://www.picacomic.com\n\n中國官網：\nhttp://cn.picacomiccn.com\n\n\n\nIOS版本已正式上架（App Store），各位紳士可到官網下載。",
          "downloadUrl": "http://cn.picacomiccn.com/PicaComic_beta_test_2.0.3.11.apk",
          "created_at": "2017-01-04T10:33:16.445Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.11.apk",
            "path": "9595f118-d8bc-4437-aaa6-7464681722b5.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "586b627f9a78f54116397291",
          "updateContent": "【是次版本，只修改後台聊天室】\n\n下載功能，將於未來推出，請各位耐心等候。\n\n\n更新內容：\n1. 修改介面（後台聊天室）\n2. 修改通知柵顯示（後台聊天室）\n3. 新增「改變大小」（後台聊天室）\n4. 新增「回覆」「＠」功能（後台聊天室）\n\n注意事項：\n後台聊天室只能收發文字。\n\n\n紳士們可到官網下載：\nhttps://www.picacomic.com\n\n中國官網：\nhttp://cn.picacomiccn.com\n\n\n\nIOS版本已正式上架（App Store），各位紳士可到官網下載。",
          "version": "2.0.3.10",
          "downloadUrl": "http://cn.picacomiccn.com/PicaComic_beta_test_2.0.3.10.apk",
          "created_at": "2017-01-03T08:36:15.603Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.10.apk",
            "path": "baafaaf8-add1-466b-b6b9-4b71adbc26ce.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "585ac86d4255134ec04f585b",
          "version": "2.0.3.9",
          "updateContent": "【修正 2.0.3.8 問題】\n\n1. 修正部份留言閃退問題\n\n2. 修正沒有顯示「最近觀看」及「已收藏」問題\n\n3. 修正聊天室點頭像閃退問題\n\n\n【2.0.3.8版更新內容】\n\n1. 改善漫畫閱讀器頁數問題\n\n2. 改善排名榜返回問題\n\n3. 新增流量使用提示\n\n4. 新增最熱門關鍵字\n\n5. 修正「跳頁」功能問題\n\n6. 「愛嗶咔・請聊天」更名為「嗶咔聊天室」\n\n7. 改善語言顯示（聊天室）\n\n8. 新增「隱藏頭像」功能（聊天室）\n\n9. 新增「修改頭像」功能（聊天室）\n\n10. 新增後台版聊天室（純文字測試版）\n\n11. 新增「圖片質素設定」（設定頁面）\n\n12. 修改部份圖片顯示方式\n\n13. 修改「讚」漫畫顯示問題\n\n\n下載功能，將於明年推出，請各位耐心等候。\n\n紳士們可到官網下載：\nhttps://www.picacomic.com\n\n中國官網：\nhttp://cn.picacomiccn.com",
          "downloadUrl": "http://www.picacomiccn.com/PicaComic_beta_test_2.0.3.9.apk",
          "created_at": "2016-12-21T18:22:37.948Z",
          "apk": {
            "originalName": "PicaComic_beta_test_2.0.3.9.apk",
            "path": "371fd62d-6f56-4082-938c-c6109b1a83fa.apk",
            "fileServer": "https://storage1.picacomic.com"
          }
        }
      ],
      "total": 30,
      "limit": 20,
      "page": 1,
      "pages": 2
    },
    "apiLevel": 22,
    "minApiLevel": 22
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» applications|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» downloadUrl|string|true|none||none|
|»»»» updateContent|string|true|none||none|
|»»»» version|string|true|none||none|
|»»»» created_at|string|true|none||none|
|»»»» apk|object|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» pages|integer|true|none||none|
|»» apiLevel|integer|true|none||none|
|»» minApiLevel|integer|true|none||none|

# announcements

## GET 哔咔公告

GET /announcements

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|page|query|integer| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# eps

## GET 获取章节图片

GET /eps/{epsId}/pages

获取章节内的图片

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|epsId|path|string| 是 |none|
|page|query|integer| 否 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "pages": {
      "docs": [
        {
          "_id": "58218b735f6b9a4f93e02a9d",
          "media": {
            "originalName": "1.jpg",
            "path": "9d73109c-e311-4a4c-a69c-4e7f7b9c735d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02a9f",
          "media": {
            "originalName": "2.jpg",
            "path": "f9cfe31d-358b-4850-a518-c923f946affa.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aa1",
          "media": {
            "originalName": "3.jpg",
            "path": "45738767-f848-44d7-9959-2eaf3d59dd82.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aa3",
          "media": {
            "originalName": "4.jpg",
            "path": "4a087cac-0eeb-43c7-a288-7b458953d30f.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aa5",
          "media": {
            "originalName": "5.jpg",
            "path": "d14b82dc-80c3-4e04-98c6-3e9a03fdd246.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aa7",
          "media": {
            "originalName": "6.jpg",
            "path": "8100c281-d863-4179-9de3-32f69abfcba5.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aa9",
          "media": {
            "originalName": "7.jpg",
            "path": "f42d0e9b-c723-40fe-93e6-cef84d13745f.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aab",
          "media": {
            "originalName": "8.jpg",
            "path": "1e980e2e-630c-4c34-9549-e1bc970361d2.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aad",
          "media": {
            "originalName": "9.jpg",
            "path": "fc96269f-d3b7-441e-955d-9e107983c38d.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02aaf",
          "media": {
            "originalName": "10.jpg",
            "path": "10c53c53-7129-4f22-bb81-5fe1afa6f1ff.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02ab1",
          "media": {
            "originalName": "11.jpg",
            "path": "dd36443c-f33e-461d-96d5-2aa52fc21d69.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02ab3",
          "media": {
            "originalName": "12.jpg",
            "path": "991bf71e-22f8-45ea-b420-d7a1b59ab494.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02ab5",
          "media": {
            "originalName": "13.jpg",
            "path": "21603051-6a55-4185-a279-8b98bfd08235.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02ab7",
          "media": {
            "originalName": "14.jpg",
            "path": "ab5c2172-4979-4e01-81c2-d1d6f50a2158.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02ab9",
          "media": {
            "originalName": "15.jpg",
            "path": "00030dd0-c8df-44e1-97e3-ce7bb53623d5.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02abb",
          "media": {
            "originalName": "16.jpg",
            "path": "6d82f062-6b72-40d6-acf2-da5bfad71d3b.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02abd",
          "media": {
            "originalName": "17.jpg",
            "path": "d8fa3e78-edc6-4ec8-8a42-db023bc3fbca.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02abf",
          "media": {
            "originalName": "18.jpg",
            "path": "577b1e9d-d918-468a-bea9-23f8812f3bd9.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02ac1",
          "media": {
            "originalName": "19.jpg",
            "path": "762ad4e5-856a-4f25-bbf4-8ce74220515e.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        },
        {
          "_id": "58218b735f6b9a4f93e02ac3",
          "media": {
            "originalName": "20.jpg",
            "path": "f233c0b1-0006-418c-88c8-3605f76762db.jpg",
            "fileServer": "https://storage1.picacomic.com"
          }
        }
      ],
      "total": 20,
      "limit": 40,
      "page": 1,
      "pages": 1
    },
    "ep": {
      "_id": "58218b735f6b9a4f93e02a9b",
      "title": "第1集"
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» pages|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» media|object|true|none||none|
|»»»»» originalName|string|true|none||none|
|»»»»» path|string|true|none||none|
|»»»»» fileServer|string|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|integer|true|none||none|
|»»» pages|integer|true|none||none|
|»» ep|object|true|none||none|
|»»» _id|string|true|none||none|
|»»» title|string|true|none||none|

# comments

## POST 回复评论

POST /comments/{commentId}

> Body 请求参数

```json
{
  "content": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|commentId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» content|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success"
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|

## POST 置顶评论

POST /comments/{commentId}/top

无法使用，提示未经授权（QAQ我记得以前还是可以指定的）

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|commentId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 400,
  "error": "1005",
  "message": "unauthorized",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## POST 隐藏评论

POST /comments/{commentId}/hide

无法使用，报错为为啥未经授权

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|commentId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 400,
  "error": "1005",
  "message": "unauthorized",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## POST (取消)点赞评论

POST /comments/{commentId}/like

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|commentId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "action": "like"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» action|string|true|none||none|

## GET 获取回复评论

GET /comments/{commentId}/childrens

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|commentId|path|string| 是 |none|
|page|query|integer| 否 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comments": {
      "docs": [],
      "total": 0,
      "limit": 5,
      "page": "1",
      "pages": 1
    }
  }
}
```

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "comments": {
      "docs": [
        {
          "_id": "62c4dd0866c852c227784fe4",
          "content": "试试八点半",
          "_user": {
            "_id": "5e2bece8d606e72a7f38402f",
            "gender": "m",
            "name": "黯淡武官",
            "title": "萌新",
            "verified": false,
            "exp": 570,
            "level": 2,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "f6d5a28f-4b32-4c4b-8ac5-c396cbea0eb6.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "slogan": "22222222222"
          },
          "_parent": "62c3fb4c45fc283cdcb14ce9",
          "_comic": "58218b725f6b9a4f93e02a99",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-07-06T00:53:28.201Z",
          "id": "62c4dd0866c852c227784fe4",
          "likesCount": 0,
          "isLiked": false
        },
        {
          "_id": "62c4dcfdae74b49f7f57c3ed",
          "content": "还上不上班",
          "_user": {
            "_id": "5e2bece8d606e72a7f38402f",
            "gender": "m",
            "name": "黯淡武官",
            "title": "萌新",
            "verified": false,
            "exp": 570,
            "level": 2,
            "characters": [],
            "role": "member",
            "avatar": {
              "originalName": "avatar.jpg",
              "path": "f6d5a28f-4b32-4c4b-8ac5-c396cbea0eb6.jpg",
              "fileServer": "https://storage1.picacomic.com"
            },
            "slogan": "22222222222"
          },
          "_parent": "62c3fb4c45fc283cdcb14ce9",
          "_comic": "58218b725f6b9a4f93e02a99",
          "totalComments": 0,
          "isTop": false,
          "hide": false,
          "created_at": "2022-07-06T00:53:17.273Z",
          "id": "62c4dcfdae74b49f7f57c3ed",
          "likesCount": 0,
          "isLiked": false
        }
      ],
      "total": 2,
      "limit": 5,
      "page": "1",
      "pages": 1
    }
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» comments|object|true|none||none|
|»»» docs|[object]|true|none||none|
|»»»» _id|string|true|none||none|
|»»»» content|string|true|none||none|
|»»»» _user|object|true|none||none|
|»»»»» _id|string|true|none||none|
|»»»»» gender|string|true|none||none|
|»»»»» name|string|true|none||none|
|»»»»» title|string|true|none||none|
|»»»»» verified|boolean|true|none||none|
|»»»»» exp|integer|true|none||none|
|»»»»» level|integer|true|none||none|
|»»»»» characters|[string]|true|none||none|
|»»»»» role|string|true|none||none|
|»»»»» avatar|object|true|none||none|
|»»»»»» originalName|string|true|none||none|
|»»»»»» path|string|true|none||none|
|»»»»»» fileServer|string|true|none||none|
|»»»»» slogan|string|true|none||none|
|»»»» _parent|string|true|none||none|
|»»»» _comic|string|true|none||none|
|»»»» totalComments|integer|true|none||none|
|»»»» isTop|boolean|true|none||none|
|»»»» hide|boolean|true|none||none|
|»»»» created_at|string|true|none||none|
|»»»» id|string|true|none||none|
|»»»» likesCount|integer|true|none||none|
|»»»» isLiked|boolean|true|none||none|
|»»» total|integer|true|none||none|
|»»» limit|integer|true|none||none|
|»»» page|string|true|none||none|
|»»» pages|integer|true|none||none|

## POST 举报评论

POST /comments/{commentId}/report

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|commentId|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

> 成功

```json
{
  "code": 200,
  "message": "success",
  "data": {
    "commentId": "62c4dde045339c9f8d06878d",
    "message": "成功舉報評論"
  }
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

状态码 **200**

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|» code|integer|true|none||none|
|» message|string|true|none||none|
|» data|object|true|none||none|
|»» commentId|string|true|none||none|
|»» message|string|true|none||none|

# utils

## POST 阻止用户

POST /utils/block-user

已废弃

> Body 请求参数

```json
{
  "userId": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» userId|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 404,
  "error": "1007",
  "message": "not found",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## POST 调整经验值

POST /utils/adjust-exp

> Body 请求参数

```json
{
  "exp": 0,
  "userId": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» exp|body|integer| 是 |none|
|» userId|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 404,
  "error": "1007",
  "message": "not found",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

## POST 删除评论

POST /utils/remove-comment

哔咔已经废弃此接口

> Body 请求参数

```json
{
  "userId": "string"
}
```

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|
|body|body|object| 否 |none|
|» userId|body|string| 是 |none|

> 返回示例

> 成功

```json
{
  "code": 401,
  "error": "1007",
  "message": "not found",
  "detail": ":("
}
```

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# image

## GET 哔咔图片

GET /static/{path}

### 请求参数

|名称|位置|类型|必选|说明|
|---|---|---|---|---|
|path|path|string| 是 |none|
|api-key|header|string| 是 |api密钥|
|accept|header|string| 是 |应该是协议|
|app-channel|header|string| 是 |分流服务器，可选值: 1 2  3|
|time|header|string| 是 |当前时间戳只要前十位，由公共脚本"生成签名"填充|
|nonce|header|string| 是 |UUID去掉-，由公共脚本"生成签名"填充|
|app-version|header|string| 是 |app版本|
|app-uuid|header|string| 是 |uuid，但是软件包内就是这个字符串|
|image-quality|header|string| 是 |哔咔图片质量，可选值：original low medium high|
|app-platform|header|string| 是 |app平台|
|app-build-version|header|string| 是 |版本|
|User-Agent|header|string| 是 |这个必须是这个|
|Content-Type|header|string| 是 |body格式|
|signature|header|string| 是 |哔咔的请求签名，，由公共脚本"生成签名"填充|
|authorization|header|string| 否 |哔咔的token，除了/auth/*不需要外，其余都要，用login分组的后置操作获取不用管|

> 返回示例

### 返回结果

|状态码|状态码含义|说明|数据模型|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|成功|Inline|

### 返回数据结构

# 数据模型

<h2 id="tocS_用户-基础">用户-基础</h2>

<a id="schema用户-基础"></a>
<a id="schema_用户-基础"></a>
<a id="tocS用户-基础"></a>
<a id="tocs用户-基础"></a>

```json
{
  "avatar": {
    "fileServer": "string",
    "originalName": "string",
    "path": "string"
  },
  "character": "string",
  "exp": 0,
  "gender": "string",
  "level": 0,
  "name": "string",
  "_id": "string",
  "verified": "string"
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|avatar|object|true|none||none|
|» fileServer|string|true|none||none|
|» originalName|string|true|none||none|
|» path|string|true|none||none|
|character|string|true|none||none|
|exp|integer|true|none||none|
|gender|string|true|none||none|
|level|integer|true|none||none|
|name|string|true|none||none|
|_id|string|true|none||none|
|verified|string|true|none||none|

<h2 id="tocS_基础返回">基础返回</h2>

<a id="schema基础返回"></a>
<a id="schema_基础返回"></a>
<a id="tocS基础返回"></a>
<a id="tocs基础返回"></a>

```json
{
  "code": 0,
  "message": "string",
  "data": {}
}

```

### 属性

|名称|类型|必选|约束|中文名|说明|
|---|---|---|---|---|---|
|code|integer|true|none||none|
|message|string|true|none||none|
|data|object|true|none||none|

