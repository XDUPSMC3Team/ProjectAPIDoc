## 登出
```
GET /logout
```

参数

```
无
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": ""
}
```
## 图片上传

```
POST /pic/upload
```
参数
```
file: (file 对象)  // 上传的图片
```

返回
```
{
    "code": 0,
    "msg": "success",
    "data": "119.23.75.180/2018/12/06/3ce0dc69-551d-4ec4-b654-86a1fea432c8.jpeg"
}
```
## 根据 detail 查询 productSpecs

```
get /product/productSpecs/{productId}/detail
```
参数
```
detail:"{"颜色":"金色","内存":"64G","购买方式":"官方标配"}"
```

返回
```
{
    "code": 0,
    "msg": "success",
    "data": {
        "id": 1,
        "productId": 1,
        "detail": "{\"颜色\":\"金色\",\"内存\":\"64G\",\"购买方式\":\"官方标配\"}",
        "stock": 5,
        "price": 9599,
        "createTime": "2018-12-08 15:41:19",
        "updateTime": "2018-12-08 15:43:43"
    }
}
```
