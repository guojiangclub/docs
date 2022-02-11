# 发送公众号模板消息

为了统一标准，日后公众号发送模板消息都使用以下方式

## 通过第三方平台

请注意查看 ibrand/common 包，调用第三方平台的接口需要通过该包的方式进行实现。

请见源码：[Client::class](https://github.com/ibrandcc/common/blob/master/src/Platform/Client.php) 中的 `sendTemplateMessage($appid, $message)` 方法

使用范例如下：

```php
          $message=[
              'template_id' => 'CZm0SGw1dIS5MMWzCjzoeLMJ5ijr6vdS6Dj9jq6I9lE',
              'url' => '',
              'touser' =>$open_id,
              'data' =>
                  [ 'first' => '你有一个学员付款成功',
                      'keyword1' => $order->sn,
                      'keyword2' => $payment,
                      'keyword3' => $order->display_total,
                      'keyword4' =>$userName,
                      'remark' => $order->title,]
          ];

          return platform_application()->sendTemplateMessage($app_id,$message);
          
```

> 因为目前所有的客户都有授权公众号给公司的第三方平台，因此目前建议使用这种方式来发送模板消息。


## 通过 Easywechat

// 待完善。


