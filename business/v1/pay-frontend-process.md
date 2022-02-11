## 小程序
1. 用户提交订单后，可使用余额加微信支付。
2. 如果当用户使用的余额等于应支付金额时，则视为纯余额支付。其他情况为混合支付。
3. 纯余额支付与混合支付请求的接口地址都是`api/shopping/order/charge`。
4. 当为纯余额支付时，请求接口成功后直接跳转到支付成功页面，不需要吊起系统的支付。
5. 当为混合支付时，接口返回charge对象，吊起微信支付。当用户取消支付时，跳转到订单详情页面。
6. 当用户再次进入支付页面时，根据请求`api/order/xxx`接口返回的balance_paid字段判断之前是否使用过余额支付，如果这个值为0就代表没有使用过余额支付，任可使用余额支付。否则就是使用过余额支付，页面上显示余额支付的金额，并且剩下的钱只能通过微信支付。
7. 


## H5
1. 只是接口地址请求不同，H5接口地址为`api/shopping/order/charge`
2. 支付逻辑由后端处理
3. 是否使用余额支付过跟小程序的第六点相同