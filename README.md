## cordova-plugin-unionpay

 感谢 Santino-Wu/cordova-plugin-unionpay 的原始版本，不过已经失效，做了些改动支持当前最新的银联支付。<br>
 Android, IOS 下测试通过。
 
安装
----

* 生产环境<br>
ionic cordova plugin add https://github.com/email10000/cordova-plugin-unionpay.git --variable UNIONPAYMODE=00

* 开发环境<br>
ionic cordova plugin add https://github.com/email10000/cordova-plugin-unionpay.git --variable UNIONPAYMODE=01

删除
----
ionic cordova plugin remove cordova-plugin-unionpay

例子
----
* ionic 客户端<br>

~~~
   /* 在ts 文件头部声明window变量 */ 
   declare let window:any;
   ...
   @IonicPage()
   ...
  // tn是从server 端生成的银联 "transaction number"
  window.unionpay.pay(tn, function(res){
    // 返回值1 支付成功
    if (res == '1') {
      ...
    // 返回值0 支付取消
    } else if(res == '0') {
      ...
    // 其他支付失败
    } else {
      ...
    }
  }, function (err){
    console.log(err);
  });
~~~
* server 端<br>
   ... （略）
