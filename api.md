**代收下单**

​           请求方式  :post 

​           header:

|     参数名      |  必选  |   类型   |        说明         |
| :----------: | :--: | :----: | :---------------: |
| Content-Type |  是   | string | application/json; |

```json
{
    "merchantCode": "S820210617152106000023",
    "method": "KING",
    "currency": "BRL",
    "orderNum": "23918283918293",
    "productDetail": "Buy Bus",
    "payMoney": "10",
    "name": "test",
  	"email": "test@email.com",
    "notifyUrl": "https://www.my.test.com",
    "dateTime": "20200712205101",
  	"phone": "1238192839"
}
```

参数说明

| 序号   | 参数名           | 参数名称  | 类型     | 是否必填 | 说明                                |
| ---- | ------------- | ----- | ------ | ---- | --------------------------------- |
| 1    | merchantCode  | 商户编号  | String | 是    | 商户号                               |
| 2    | method        | 支付渠道  | String | 是    | 支付渠道 默认KING                       |
| 3    | currency      | 币种    | String | 是    | 默认 BRL 巴西                         |
| 4    | orderNum      | 商户订单号 | String | 是    | 订单号 保证唯一                          |
| 5    | productDetail | 商品详情  | String | 是    | 商品详情                              |
| 6    | payMoney      | 支付金额  | String | 是    | 支付金额                              |
| 7    | name          | 客户名字  | String | 是    | 客户名称                              |
| 8    | email         | 邮箱    | String | 是    | 客户邮箱                              |
| 9    | notifyUrl     | 回调地址  | String | 是    | 支付成功后，平台主动通知商家系统，商家系统必须指定接收通知的地址。 |
| 10   | dateTime      | 时间戳   | String | 是    | 时间戳 格式 yyyyMMddHHmmss             |
| 11   | phone         | 电话号码  | String | 是    | 电话号码                              |
| 12   | ext           | 透传参数  | String | 是    | 传透参数，异步通知原样返回                     |
| 13   | sign          | 签名    | String | 是    | 详情见数字签名                           |

返回参数说明

```json
{
  "platRespCode": "SUCCESS",
  "platRespMessage": "success",
  "platOrderNum": "BCA_1234567890",
  "orderNum": "T202007183457183",
  "method": "KING",
  "name": "Asmana",
  "email": "user@akikpay.com",
  "payMoney": 10000,
  "payFee": 3000,
  "productDetail": "iPhone11",
  "url": "https:test.com",
  "platSign": "MIGfMA0GCSqGSI...w1ypbiy7VhIoFJbgSYSSHdC"
}
```

| 序号   | 参数名             | 参数名称   | 类型     | 是否必填 | 说明                                       |
| ---- | --------------- | ------ | ------ | ---- | ---------------------------------------- |
| 1    | platRespCode    | 平台返回码  | String | 是    | "SUCCESS" "FAIL" "UNKNOWN" "NOTEXIST" "ERROR" 四种状态 |
| 2    | platRespMessage | 平台返回信息 | String | 否    | 错误信息                                     |
| 3    | platOrderNum    | 平台订单号  | String | 否    | 平台订单号                                    |
| 4    | orderNum        | 订单号    | String | 否    | 订单号                                      |
| 5    | method          | 支付渠道   | String | 否    | 支付渠道                                     |
| 6    | name            | 名字     | String | 否    | 客户名字                                     |
| 7    | email           | 邮箱     | String | 否    | 邮箱                                       |
| 8    | payMoney        | 支付金额   | String | 否    | 支付金额                                     |
| 9    | payFee          | 支付费用   | String | 否    | 支付费用                                     |
| 10   | productDetail   | 商品详情   | String | 否    | 商品详情                                     |
| 11   | url             | 支付地址   | String | 否    | 支付地址                                     |
| 12   | platSign        | 平台签名   | String | 否    | 平台签名                                     |



  #####        代付下单  

   请求方式  :post 

|     参数名      |  必选  |   类型   |        说明         |
| :----------: | :--: | :----: | :---------------: |
| Content-Type |  是   | String | application/json; |

```json
{
    "dateTime": "20210820150610",
    "merchantCode": "S820210617152106000000",
    "method": "KINGPAY",
    "orderNum": "PW7829446767992",
    "description": "cash withdrawals ",
    "feeType": "1",
    "number": "15456687798",
    "money": "11",
    "name": "Tom",
    "notifyUrl": "https://www.google.cn/notifyUrl",
    "currency": "BRL",
    "sign": "ZjLZ6RB....rL9TE1IE7F8ekA4IQmg=="
}
```

请求参数说明



| 序号   | 参数名          | 参数名称    | 类型     | 是否必填 | 说明                                |
| ---- | ------------ | ------- | ------ | ---- | --------------------------------- |
| 1    | merchantCode | 商户编号    | String | 是    | 商户号,详见3.1获取正式商户号                  |
| 2    | method       | 支付渠道    | String | 是    | 支付渠道  KINGPAY                     |
| 3    | currency     | 币种      | String | 是    | BRL  巴西                           |
| 4    | orderNum     | 商户订单号   | String | 是    | 订单号 保证唯一                          |
| 5    | description  | 描述      | String | 是    | 订单描述                              |
| 6    | feeType      | 手续费收取方式 | String | 是    | 自定义                               |
| 7    | name         | 客户名字    | String | 是    | 客户名称                              |
| 8    | number       | 收款人账号   | String | 是    | 收款人账号                             |
| 9    | notifyUrl    | 回调地址    | String | 是    | 支付成功后，平台主动通知商家系统，商家系统必须指定接收通知的地址。 |
| 10   | dateTime     | 时间戳     | String | 是    | 时间戳 格式 yyyyMMddHHmmss             |
| 11   | sign         | 签名      | String | 是    | 详情见数字签名                           |
| 12   | money        | 转账金额    | String | 是    | 两位小数,如: 12.11                     |
|      |              |         |        |      |                                   |





返回参数说明

```json
{
    "fee": "0",
    "orderNum": "PW8829446767992",
    "description": "cash withdrawals ",
    "platRespCode": "SUCCESS",
    "feeType": "1",
    "platOrderNum": "W0620210831092919000002",
    "number": "15456687798",
    "money": "11",
    "statusMsg": "Apply",
    "name": "Tom",
    "platSign": "Yhi1y6P3bX3H5i6WRM1UTkTQL.....lc6aZkh0+Np1ckabSByPX3ks3DplsowynE=",
    "platRespMessage": "Request success",
    "status": "0"
}
```

| 序号   | 参数名             | 参数名称    | 类型     | 是否必填 | 说明                                       |
| ---- | --------------- | ------- | ------ | ---- | ---------------------------------------- |
| 1    | platRespCode    | 返回码     | String | 是    | "SUCCESS" "FAIL" "UNKNOWN" "NOTEXIST" "ERROR" 四种状态 |
| 2    | platRespMessage | 返回信息    | String | 是    | 错误信息 成功返回"success"                       |
| 3    | platOrderNum    | 平台订单号   | String | 否    | 平台订单号                                    |
| 4    | orderNum        | 订单号     | String | 否    | 订单号                                      |
| 5    | name            | 名称      | String | 否    | 姓名                                       |
| 6    | number          | 号码      | String | 否    | 银行账号                                     |
| 7    | status          | 交易状态    | String | 否    | 0-初始态(待接单) 1-已接单(处理中) 2-处理成功 3-撤销成功 4-处理失败 5-代付中 |
| 8    | money           | 提现金额    | String | 否    | 提现金额                                     |
| 9    | fee             | 费用      | String | 否    | 费用                                       |
| 10   | notifyUrl       | 回调地址    | String | 否    | 回调地址                                     |
| 11   | feeType         | 手续费收取方式 | String | 否    | 自定义                                      |
| 12   | platSign        | 平台签名    | String | 否    | 平台签名                                     |











