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
无
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": [
        {
            "id": 28,
            "shopId": 4,
            "shopName": null,
            "shopDesc": null,
            "categoryId": 3,
            "name": "iphonex",
            "pic": "http://119.23.75.180/2018/12/20/59f4c4ab-241a-497e-a0eb-c3a4c2846a8b.jpg",
            "attributeList": "{\"Color\":[\"red\",\"blue\"],\"Memory\":[\"64G\",\"128G\"]}",
            "description": "iphonex",
            "status": 0,
            "createTime": "2018-12-20 21:36:35",
            "updateTime": "2018-12-20 21:36:35",
            "collectId": 24
        }
    ]
}
```

## 查看我收藏的店铺 

```
GET /buyer/collectShop
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
    "data": [
        {
            "id": 1,
            "sellerId": 2,
            "shopName": "Apple",
            "shopDesc": "Apple",
            "phone": "4006668800",
            "email": "1187697635@qq.com",
            "status": 1,
            "collectId": 1,
            "products": [],
            "createTime": "2018-12-12 23:43:33",
            "updateTime": "2018-12-12 23:43:33"
        }
    ]
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



## 添加商品到购物车

```
POST /buyer/addCart
```

参数

```
specsId int required //选择商品具体属性后，返回了价格、库存，也就是特定型号id
amount int required
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": null
}
```

## 查看购物车

```
GET /buyer/viewCart
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
    "data": [
        {
            "id": 3,
            "productId": 14,
            "specsId": 25,
            "name": "PS4",
            "detail": "{\"Color\":\"black\",\"Memory\":\"512GB\",\"Payment\":\"Alipay\"}",
            "price": 2600,
            "amount": 2,
            "createTime": "2018-12-19 20:41:56",
            "updateTime": "2018-12-19 20:41:56"
        }
    ]
}
```

参数说明

```
此处的id，在之后update和delete中作为cartId使用，即购物车条目ID
```

## 更新购物车中某商品的数量

```
GET /buyer/updateCart/{cartId}
```

参数

```
amount int required (>=1)
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": null
}
```

## 从购物车中移除商品

```
DELETE /buyer/deleteCart/{cartId}
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

## 查看个人资料

```
GET /buyer/profile
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
        "id": 4,
        "username": "wxj",
        "password": null,
        "realName": null,
        "phone": null,
        "email": "331242812@qq.com",
        "address": null,
        "status": 0,
        "createTime": "2018-12-19 17:40:30",
        "updateTime": "2018-12-19 17:40:30"
    }
}
```

## 修改个人资料

```
POST /buyer/profile
```

参数

```
realname string optional
phone string optional
email string optional
address string optional
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": null
}
```

## 直接下单

```
POST /buyer/order
```

参数

```
specsId int required
amount int required
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": 1  // 这里为生成的订单ID
}
```

## 从购物车中下单

## 查看订单列表

```
GET /buyer/order
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
    "data": [
        {
            "id": 1,
            "shopId": 1,
            "money": 24000,
            "status": 0,
            "payStatus": 1,
            "orderDetailList": [
                {
                    "productId": 25,
                    "productName": "iPhone 8",
                    "price": 8000,
                    "amount": 3
                }
            ],
            "receiveTime": null,
            "createTime": "2018-12-20 13:57:25",
            "updateTime": "2018-12-20 13:57:25"
        }
    ]
}
```

字段解释

```
- status 订单状态（-1已取消/0已下单/1已发货/2已收货/3已评价/4退货中/5退货成功）
- pay_status 支付状态 （0未支付/1已支付）
```

## 查看订单详情

```
GET /buyer/order/{orderId}
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
        "shopName": "Apple",
        "receiverName": "wxj",
        "address": "America",
        "money": 24000,
        "status": 0,
        "payStatus": 1,
        "orderDetailList": [
            {
                "productId": 25,
                "productName": "iPhone 8",
                "price": 8000,
                "amount": 3
            }
        ],
        "receiveTime": null,
        "createTime": "2018-12-20 13:57:25",
        "updateTime": "2018-12-20 13:57:25"
    }
}
```

字段解释

```
- status 订单状态（-1已取消/0已下单/1已发货/2已收货/3已评价/4退货中/5退货成功）
- pay_status 支付状态 （0未支付/1已支付）
```

## 支付订单

```
PUT /buyer/order/{orderId}/pay
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

## 取消订单

```
PUT /buyer/order/{orderId}/cancel
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

## 确认收货

```
PUT /buyer/order/{orderId}/confirm
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



## 商铺列表

```
GET /shop/shops
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
        "content": [
            {
                "id": 1,
                "sellerId": 2,
                "shopName": "Apple",
                "shopDesc": "Apple",
                "phone": "4006668800",
                "email": "1187697635@qq.com",
                "status": 1,
                "createTime": "2018-12-12 23:43:33",
                "updateTime": "2018-12-12 23:43:33"
            },
            {
                "id": 2,
                "sellerId": 3,
                "shopName": "Sony",
                "shopDesc": "Sony",
                "phone": "123456",
                "email": "1329176648@qq.com",
                "status": 1,
                "createTime": "2018-12-12 23:51:17",
                "updateTime": "2018-12-12 23:51:17"
            },
            {
                "id": 3,
                "sellerId": 4,
                "shopName": "HUAWEI",
                "shopDesc": "HUAWEI",
                "phone": "123456",
                "email": "1430612146@qq.com",
                "status": 1,
                "createTime": "2018-12-12 23:52:03",
                "updateTime": "2018-12-12 23:52:03"
            },
            {
                "id": 4,
                "sellerId": 5,
                "shopName": "Electronic product",
                "shopDesc": "Electronic product",
                "phone": "123",
                "email": "331242812@qq.com",
                "status": 1,
                "createTime": "2018-12-12 23:53:40",
                "updateTime": "2018-12-12 23:53:40"
            },
            {
                "id": 5,
                "sellerId": 6,
                "shopName": "OPPO",
                "shopDesc": "OPPO",
                "phone": "123",
                "email": "772043237@qq.com",
                "status": 1,
                "createTime": "2018-12-12 23:54:22",
                "updateTime": "2018-12-12 23:54:22"
            },
            {
                "id": 6,
                "sellerId": 7,
                "shopName": "Samsung",
                "shopDesc": "Samsung",
                "phone": "123455",
                "email": "NeXT-XLC@outlook.com",
                "status": 1,
                "createTime": "2018-12-12 23:55:32",
                "updateTime": "2018-12-12 23:55:32"
            },
            {
                "id": 7,
                "sellerId": 8,
                "shopName": "Razer",
                "shopDesc": "Razer",
                "phone": "1234555566",
                "email": "595357438@qq.com",
                "status": 1,
                "createTime": "2018-12-12 23:58:17",
                "updateTime": "2018-12-12 23:58:17"
            },
            {
                "id": 8,
                "sellerId": 9,
                "shopName": "Vivo",
                "shopDesc": "Vivo",
                "phone": "1234",
                "email": "12314",
                "status": 0,
                "createTime": "2018-12-18 22:25:45",
                "updateTime": "2018-12-18 22:25:45"
            }
        ],
        "last": true,
        "totalElements": 8,
        "totalPages": 1,
        "size": 10,
        "number": 0,
        "sort": null,
        "first": true,
        "numberOfElements": 8
    }
}
```

## 商铺详情

```
GET /shop/{shopId}
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
        "sellerId": 2,
        "shopName": "Apple",
        "shopDesc": "Apple",
        "phone": "4006668800",
        "email": "1187697635@qq.com",
        "status": 1,
        "collectId": 0,
        "products": [
            {
                "id": 20,
                "shopId": 1,
                "categoryId": 3,
                "name": "iPad",
                "pic": "http://119.23.75.180/2018/12/13/11c35cd7-411d-4e18-85e1-1a9f3b3c6576.png",
                "attributeList": "{\"Color\":[\"gold\",\"black\"],\"Memory\":[\"64G\",\"128G\"],\"Payment\":[\"Wechat\",\"Alipay\"]}",
                "description": "iPad",
                "status": 0,
                "createTime": "2018-12-13 01:29:22",
                "updateTime": "2018-12-13 01:29:22"
            },
            {
                "id": 21,
                "shopId": 1,
                "categoryId": 3,
                "name": "iPod Touch",
                "pic": "http://119.23.75.180/2018/12/13/1793d936-ba88-40dd-b6f4-4117ef07dbe9.png",
                "attributeList": "{\"Color\":[\"gold\",\"blue\",\"red\"],\"Memory\":[\"64G\",\"128G\"],\"Payment\":[\"Wechat\",\"Alipay\"]}",
                "description": "iPod Touch",
                "status": 0,
                "createTime": "2018-12-13 01:30:41",
                "updateTime": "2018-12-13 01:30:41"
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
            }
        ],
        "createTime": "2018-12-12 23:43:33",
        "updateTime": "2018-12-12 23:43:33"
    }
}
```





































































