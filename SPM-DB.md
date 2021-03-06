 # SPM Database Design

## buyer

- id int11
- username varchar
- password varchar
- realname varchar 
- phone varchar
- email varchar
- address varchar
- status tinyint
- create_time timestamp（数据库自行控制，下同）
- update_time timestamp（数据库自行控制，下同）

##seller 

- id
- shopname
- password
- realname
- phone
- email
- address
- status
- create_time
- update_time

## admin

- id
- username
- password
- email
- phone
- status
- create_time
- update_time

## category 类别

- id 
- parent_id 父分类id，默认0
- name 类别名

## product 商品主表（SPU）

- id
- shop_id  //shop id
- category_id //类别id
- price     // 商品价格
- name 商品名
- pic 商品图片
- attribute_list 属性选项，例如：`{"memory":["4G", "8G"], "color":["red","black", "white"]}`
- description 商品描述
- create_time
- update_time
- status 商品状态 0 表示正常 1表示下架

## product_specs 商品详情表（指定规格商品SKU）

- id
- product_id
- detail 详细属性，例如: `{"memory": "4G", "color": "red"}`
- stock 库存
- price 单价 decimal(8,2)
- create_time
- update_time

##商品属性key表

- id
- category_id
- attribute_key 属性key名称，例如：内存，颜色，尺码

##attribute_value a

- id
- attribute_id 属性key的id
- attribute_value

## shopcart购物车

- id
- buyer_id 用户id
- product_id 泛指商品id
- specs_id 特指商品id
- amount 该商品数量
- create_time
- update_time

## order_master 订单主表

- id
- buyer_id
- receiver_name 收货人姓名
- receiver_address 收货地址
- money 总金额 decimal(8,2)
- status 订单状态（0已下单/1已发货/2已收货/3已评价/4退货中/5退货成功）
- pay_status 支付状态 （0未支付/1已支付）
- receive_time 收货时间
- create_time （在这里可作为下单时间使用）
- update_time

## order_detail 订单详情表

- id
- master_id
- product_id
- product_name
- amount 
- price
- create_time
- update_time
## product_collect 商品收藏表
- id
- buyer_id
- product_id
- create_time
- update_time

## shop_collect 店铺收藏表
- id
- buyer_id
- shop_id
- create_time
- update_time

## shop 商家表
- id
- seller_id
- shop_name
- shop_desc 商家简介
- status 商铺状态 0 表示正在受理中 1 表示受理成功 2 表示受理失败
- create_time   开店日期
- update_time

## advertisement 广告表
- id
- name
- link 广告链接地址
- pic 广告图片
- content 内容
- start_time 广告开始时间
- end_time 广告结束时间
- create_time 创建时间
- update_time 更新时间
- deleted 逻辑删除

## comment 评论表

- id
- buyer_id
- product_id
- order_detail_id
- content
- Create_time
- Update_time