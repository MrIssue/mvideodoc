# 前台API文档



* [专题相关](#topic)

### 环境

|env | url |
|:----:|:---:|
|test|https://syreal.cn|

### <span id='topic'>专题相关</span>

>#### 获取所有专题

`GET /topics/{id?}`

##### 请求参数
|参数|说明|字段类型|是否必填|
|:---:|:---:|:---:|:---:|
|id|专题id,存在时为获取某个专题详情|int|否|

##### 返回参数

|参数|说明|字段类型|是否必填|
|:---:|:---:|:---:|:---:|
|id|专题ID|int|Y|
|name|专题名称|string|Y|
|description|专题介绍|string|N|
|sort|专题权重|int|Y
|video_num|专题下视频数量|int|Y|
|subtopics|子专题|array|

存在ID，videos参数：

|参数|说明|字段类型|是否必填|
|:---:|:---:|:---:|:---:|
|id|视频ID|int|Y|
|user_id|上传用户ID|int|Y|
|topic_id|专题ID|int|Y|
|subtopic_id|子专题ID|int|Y|
|title|视频标题|string|Y|
|description|视频描述|string|Y|
|url|视频链接|string|Y|
|pic|视频快照链接|string|Y|
|time|视频时长|单位:s|Y|
|play_counts|播放次数|int|Y|
|comment_couts|评论数量|int|Y|
|keywords|关键词|array|Y|
|labels|标签|array|Y|



```json
不存在id:
{
    "code": 200,
    "data": [
        {
            "id": 1,
            "name": "电视剧",
            "description": "各种电视剧",
            "sort": 88,
            "status": 2,
            "video_num": 0,
            "deleted_at": null,
            "created_at": "2018-12-29 02:19:37",
            "updated_at": "2018-12-29 02:19:37",
            "subtopics": [
                {
                    "id": 1,
                    "topic_id": 1,
                    "name": "子专题",
                    "description": "子专题介绍",
                    "sort": 99,
                    "status": 1,
                    "video_num": 0,
                    "deleted_at": null,
                    "created_at": "2018-12-29 02:19:37",
                    "updated_at": "2018-12-29 02:19:37"
                }
            ]
        },
        {
            "id": 2,
            "name": "电视剧",
            "description": "各种电视剧",
            "sort": 88,
            "status": 2,
            "video_num": 0,
            "deleted_at": null,
            "created_at": "2018-12-29 02:19:52",
            "updated_at": "2018-12-29 02:19:52",
            "subtopics": [
                {
                    "id": 2,
                    "topic_id": 2,
                    "name": "子专题",
                    "description": "子专题介绍",
                    "sort": 99,
                    "status": 1,
                    "video_num": 0,
                    "deleted_at": null,
                    "created_at": "2018-12-29 02:19:52",
                    "updated_at": "2018-12-29 02:19:52"
                }
            ]
        }
    ],
    "msg": ""
}
存在id:
{
    "code": 200,
    "data": {
        "id": 1,
        "name": "电视剧",
        "description": "各种电视剧",
        "sort": 88,
        "status": 2,
        "video_num": 0,
        "deleted_at": null,
        "created_at": "2018-12-29 02:19:37",
        "updated_at": "2018-12-29 02:19:37",
        "subtopics": [
            {
                "id": 1,
                "topic_id": 1,
                "name": "子专题",
                "description": "子专题介绍",
                "sort": 99,
                "status": 1,
                "video_num": 0,
                "deleted_at": null,
                "created_at": "2018-12-29 02:19:37",
                "updated_at": "2018-12-29 02:19:37"
            }
        ],
        "videos": []
    },
    "msg": ""
}
```

### <span id='video'>视频相关</span>

>#### 获取视频详情
`GET /videos/{id}`

##### 请求参数

|参数|说明|字段类型|是否必填|
|:---:|:---:|:---:|:---:|
|id|视频id|int|Y|

##### 返回参数

|参数|说明|字段类型|是否必填|
|:---:|:---:|:---:|:---:|
|id|视频id|int|Y|
|user_id|上传用户id|int|Y|
|topic_id|主专题id|int|Y|
|subtopic_id|子专题ID|int|Y|
|title|视频标题|string|Y|
|description|视频介绍|string|N|
|url|视频链接|string|Y|
|pic|视频封面链接|string|Y|
|time|视频时长|单位:s|Y|
|play_counts|播放次数|int|Y|
|comment_couts|评论数量|int|Y|
|keywords|关键词|array|Y|
|labels|标签|array|Y|
|created_at|上传时间|datetime|Y|
|updated_at|更新时间|datetime|Y|


```json
{
    "code": 200,
    "data": {
        "id": 1,
        "user_id": 1,
        "topic_id": 1,
        "subtopic_id": 1,
        "title": "Saepe et est.",
        "description": "ZZ53ZnesBojrrnO9",
        "url": "http://cormier.com/a-libero-ducimus-rerum-facere-neque.html",
        "pic": "http://howe.com/blanditiis-nostrum-dolor-eveniet-nulla-eius.html",
        "time": 14366,
        "play_counts": 745,
        "comment_counts": 88226171,
        "keywords": [
            "Mrs.",
            "Miss"
        ],
        "labels": [
            "Arvilla Hermiston II",
            "Gayle Reichert"
        ],
        "created_at": "2019-01-03 08:00:52",
        "updated_at": "2019-01-03 08:00:52"
    },
    "msg": ""
}
```
