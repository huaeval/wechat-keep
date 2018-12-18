# 公众号绑定，用于留存用户
## 一、二维码入口
### 1.1
> 1. 带参数的二维[**参考链接**](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1443433542)
> 2. 二维码有数量或效期限制
> 3. 效期30天二维码无显示
> 4. 无效期限制限制10万条
### 1.2
> 1. 如果用户还未关注公众号，则用户可以关注公众号，**关注后微信会将带场景值关注事件推送给开发者**。
> 2. 如果用户已经关注公众号，在用户扫描后会自动进入会话，**微信也会将带场景值扫描事件推送给开发者[1]**。
> 3. [1]同样响应关注事件[**参考地址**](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1421140454)
## 二、响应关注事件
### 2.1
> 1. [**参考地址**](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1421140454)
> 2. 用户 **扫码关注之后[2]** 或者 **扫码之后[3]** 响应事件获取参数 **EventKey**
> 3. 获取响应类型，处理参数结果,绑定用户到服务器[4]。返回给关注者[5]
> 4. [2][3] 1.2具体说明.[4]方便下次主动推送消息 .[5]直接返回文本消息。
> 5. 这里可以获取openid可以发送模版消息，是否可以发送模版消息？
## 三、发送模版消息
### 3.1
> 1. 发送模版消息[**参考地址**](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1433751277)
> 2. 模板消息仅用于公众号向用户发送重要的服务通知，只能用于符合其要求的服务场景中，如信用卡刷卡通知，商品购买成功通知等。不支持广告等营销类消息以及其它所有可能对用户造成骚扰的消息
> 3. 所有服务号都可以在功能->添加功能插件处看到申请模板消息功能的入口，但只有认证后的服务号才可以申请模板消息的使用权限并获得该权限；
> 4. 需要选择公众账号服务所处的2个行业，每月可更改1次所选行业；
> 5. 在所选择行业的模板库中选用已有的模板进行调用；
> 6. 每个账号可以同时使用25个模板。
> 7. 当前每个账号的模板消息的日调用上限为10万次，单个模板没有特殊限制。【2014年11月18日将接口调用频率从默认的日1万次提升为日10万次，可在MP登录后的开发者中心查看】。当账号粉丝数超过10W/100W/1000W时，模板消息的日调用上限会相应提升，以公众号MP后台开发者中心页面中标明的数字为准。
### 3.2
> 1. 消息可以打开小程序
> 2. 消息可以打开url
### 3.3
> 1. 如果是关注事件发送模版消息，事件本身有需要发送模板需要的openid
> 2. 如果不是关注事件，主动发送需要**获取服务器关联的信息[1]** 
> 3. [1]关注事件应该绑定用户信息

## 四、实现条件
> 1. 发送消息-模板消息接口（发送业务通知）需要**微信认证服务号** [参考链接](https://mp.weixin.qq.com/wiki?t=resource/res_main&id=mp1433401084)

---
# 小程序模版消息留存用户

> TODO
