## 买家注册
```
POST /buyer/register
```

参数

```
email string
username string
password string
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": "Welcome, xxx"
}
```
字段解释

```
xxx: xxxxxx
```

## 买家登录
```
POST /buyer/login
```

参数

```
username string
password string
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": ""
}
```
字段解释

```
xxx: xxxxxx
```

## 所有商品

```
GET /product/products
```

参数

```
pageNo int 页码 optional
pageSize int 每页大小 optional
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "content": [
            {
                "id": 1,
                "shopId": 1,
                "categoryId": 1,
                "name": "Apple Iphone XS Max",
                "pic": "www.baidu.com",
                "attributeList": "{"内存":["64G", "128G"], "颜色":["金色","深空银色", "银色"]}",
                "description": "very good",
                "status": 0,
                "createTime": "2018-12-08 15:43:57",
                "updateTime": "2018-12-08 15:44:55"
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 1,
        "size": 10,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```

字段解释

```
id 商品id
categoryId 类别id
attributeList 属性项列表
```



## 单个商品详情

```
GET /product/{productId}
```

参数

```
无
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "id": 1,
        "shopId": 1,
        "categoryId": 1,
        "name": "Apple Iphone XS Max",
        "pic": "www.baidu.com",
        "attributeList": "{"内存":["64G", "128G"], "颜色":["金色","深空银色", "银色"]}",
        "description": "very good",
        "status": 0,
        "createTime": "2018-12-08 15:43:57",
        "updateTime": "2018-12-08 15:44:55"
    }
}
```

字段解释

```
同上“所有商品”
```

## 搜索商品

```
GET /product/search
```

参数

```
key string optional
pageNo int optional
pageSize int optional
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "content": [
            {
                "id": 1,
                "shopId": 1,
                "categoryId": 1,
                "name": "Apple Iphone XS Max",
                "pic": "www.baidu.com",
                "attributeList": "{"内存":["64G", "128G"], "颜色":["金色","深空银色", "银色"]}",
                "description": "very good",
                "status": 0,
                "createTime": "2018-12-08 15:43:57",
                "updateTime": "2018-12-08 15:44:55"
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 1,
        "size": 10,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```

## 收藏商品

```
GET /buyer/collectProd/{productId}
```

参数

```
无
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": 2 // 这里为collectId 即商品收藏项的唯一id
}
```

## 收藏店铺

```
GET /buyer/collectShop/{shopId}
```

参数

```
无
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": 2 // 这里为collectId 即店铺收藏项的唯一id
}
```

## 查看我收藏的商品 

```
GET /buyer/collectProd
```

参数

```
pageNo int optional
pageSize int optional
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "content": [
            {
                "id": 1,
                "shopId": 1,
                "categoryId": 1,
                "name": "Apple Iphone XS Max",
                "pic": "www.baidu.com",
                "attributeList": "{"内存":["64G", "128G"], "颜色":["金色","深空银色", "银色"]}",
                "description": "very good",
                "status": 0,
                "createTime": "2018-12-08 15:43:57",
                "updateTime": "2018-12-08 15:44:55"
            }
        ],
        "last": true,
        "totalPages": 1,
        "totalElements": 1,
        "size": 10,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```

## 查看我收藏的店铺 

```
GET /buyer/collectShop
```

参数

```
pageNo int optional
pageSize int optional
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": {
        "content": [
            {
                "id": 1,
                "sellerId": 1,
                "shopName": "Apple",
                "shopDesc": "gay gay wang",
                "phone": "123123132",
                "email": "1187@qq.com",
                "status": 0,
                "createTime": "2018-12-08 15:46:41",
                "updateTime": "2018-12-08 15:47:08"
            }
        ],
        "last": true,
        "totalElements": 1,
        "totalPages": 1,
        "size": 10,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 1
    }
}
```







## 取消收藏商品

```
DELETE /buyer/collectProd/{collectId}  // 此处collectId为收藏表的主键
```

参数

```
无
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": null
}
```

## 取消收藏店铺

```
DELETE /buyer/collectShop/{collectId} // 此处collectId为收藏表的主键
```

参数

```
无
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": null
}
```















