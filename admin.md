## admin注册
```
POST /admin/register
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

## admin登录
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

## 查看新申请的店铺
```
GET /admin/personal/appliedShops
```

参数

```
无参数
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": { [ // Shop实体数组 ] }
}
```
字段解释

```
xxx: xxxxxx
```

## 通过申请
```
POST /admin/personal/approve/{shopId}
```

参数(包含在路径)

```
shopId integer
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

## 拒绝申请
```
POST /admin/personal/reject/{shopId}
```

参数(包含在路径)

```
shopId integer
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
## 搜索店铺
```
GET /admin/personal/search/{shopId}
```

参数(包含在路径)

```
shopId integer
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": { // Shop实体 }
}
```
字段解释

```
xxx: xxxxxx
```

## 关闭店铺
```
POST /admin/personal/close/{shopId}
```

参数(包含在路径)

```
shopId integer
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

## 搜索订单
```
GET /admin/personal/order/search/{orderId}
```

参数(包含在路径)

```
orderId integer
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": { // orderVO实体 }
}
```
字段解释

```
xxx: xxxxxx
```

OrderVO实体：

    private Integer id;
    private Integer buyerId;
    private String receiverName;    //收货人姓名
    private Double money;   //金钱
    private Integer status; //订单状态
    private Integer payStatus;  //支付状态
    private Integer productId;
    private String productName;
    private Integer amount;
    private Double price;
    @JsonFormat(shape = JsonFormat.Shape.STRING, pattern = "yyyy-MM-dd HH:mm:ss")
    private LocalDateTime receiveTime;  //收货时间
    @JsonFormat(shape = JsonFormat.Shape.STRING, pattern = "yyyy-MM-dd HH:mm:ss")
    private LocalDateTime createTime;   //创建时间
    @JsonFormat(shape = JsonFormat.Shape.STRING, pattern = "yyyy-MM-dd HH:mm:ss")
    private LocalDateTime updateTime;   //更新时间

## 搜索用户
```
GET /admin/personal/customer/search/{username}
```

参数(包含在路径)

```
username string
```

返回

```
{
    "code": 0,
    "msg": "success",
    "data": { // Buyer实体 }
}
```
字段解释

```
xxx: xxxxxx
```
## 货物下架
```
POST /admin/personal/product/off/{productId}
```

参数(包含在路径)

```
productId integer
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

## 黑名单
```
POST /admin/personal/customer/block/{userId} personal/seller/block/{sellerId}
```

参数(包含在路径)

```
userId integer
sellerId integer
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


