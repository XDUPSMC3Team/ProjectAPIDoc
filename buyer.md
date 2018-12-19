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
        "updateTime": "2018-12-08 15:44:55",
        "collectId": 2
    }
}
```

字段解释

```
同上“所有商品”
collectId 只有用buyer身份访问此接口才会有
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



## 按分类查看商品

```
GET /product/byCategory/{categoryId}
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
                "id": 25,
                "shopId": 1,
                "categoryId": 3,
                "name": "iPhone 8",
                "pic": "http://119.23.75.180/2018/12/18/40b57cea-7f3d-4fbe-a414-6d4e85cc5f6b.png",
                "attributeList": "{\"Color\":[\"red\",\"gold\"],\"Memory\":[\"64G\",\"128G\"],\"Payment\":[\"WeChat\",\"Alipay\"]}",
                "description": "iPhone 8",
                "status": 0,
                "createTime": "2018-12-18 22:22:01",
                "updateTime": "2018-12-18 22:22:01"
            },
            {
                "id": 23,
                "shopId": 1,
                "categoryId": 3,
                "name": "MacBook Pro",
                "pic": "http://119.23.75.180/2018/12/13/9ac4fffa-e7fc-4a9b-b702-8c9627be3938.png",
                "attributeList": "{\"Color\":[\"silver\"],\"Memory\":[\"128G\",\"512G\",\"1TB\"],\"Payment\":[\"Wechat\",\"Alipay\"]}",
                "description": "MacBook Pro",
                "status": 0,
                "createTime": "2018-12-13 01:33:32",
                "updateTime": "2018-12-13 01:33:32"
            },
        ],
        "last": false,
        "totalElements": 14,
        "totalPages": 2,
        "size": 10,
        "number": 0,
        "sort": [
            {
                "direction": "DESC",
                "property": "id",
                "ignoreCase": false,
                "nullHandling": "NATIVE",
                "ascending": false,
                "descending": true
            }
        ],
        "first": true,
        "numberOfElements": 10
    }
}
```















