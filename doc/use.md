# 使用文档(以微信公众账号支付为例)
## 视频教程
1. [best-pay-sdk的使用](http://v.youku.com/v_show/id_XMjg5MjM4ODIyNA==.html)
2. [支付调试补充](http://v.youku.com/v_show/id_XMjk1OTg2Mzk5Ng==.html)
3. [借用授权并支付](http://v.youku.com/v_show/id_XMjk1OTg2NTEzNg==.html)

## 文字教程
1. 配置

    ```
    //微信公众账号支付配置
    WxPayH5Config wxPayH5Config = new WxPayH5Config();
    wxPayH5Config.setAppId("xxxxx");
    wxPayH5Config.setAppSecret("xxxxxxxx");
    wxPayH5Config.setMchId("xxxxxx");
    wxPayH5Config.setMchKey("xxxxxxx");
    wxPayH5Config.setNotifyUrl("http://xxxxx");
            
    //支付类, 所有方法都在这个类里
    BestPayServiceImpl bestPayService = new BestPayServiceImpl();
    bestPayService.setWxPayH5Config(wxPayH5Config);
    ```

    
1. 发起支付

        PayRequest payRequest = new PayRequest();
        payRequest.setPayTypeEnum(BestPayTypeEnum.WXPAY_H5);
        payRequest.setOrderId("123456");
        payRequest.setOrderName("微信公众账号支付订单");
        payRequest.setOrderAmount(0.01);
        payRequest.setOpenid("openid_xxxxxx");
        bestPayService.pay(payRequest);
    
1. 异步回调

    ```
    bestPayService.asyncNotify();
    ```


