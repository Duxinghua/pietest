比特派 APP 支付
=======================

流程
---------------

登录获取二维码 --> 服务器获取支付二维码 --> 服务器获取二维码支付状态  --> 支付成功 --> 回调通知


获取支付二维码
---------------

        **请求 API **:
            * ``url`` */api/v1/open/third/party/{coin_code}/pay/qr/create*
            * ``method`` *POST*
            * ``content-type`` *application/json*

        **参数**:
            * ``appkey`` *(String)* -参数类型, *(App 标识)*
            * ``transfer_id`` *(String)* -参数类型, *订单号*
            * ``amount`` *(String)* - 参数类型, *金额*


        **返回值**
            * ``time`` *时间戳*
            * ``qr_info``
            * ``qr_url``





获取支付二维码状态
-------------------------


        **请求 API **:
            * ``url`` */api/v1/open/third/party/pay/qr/query*
            * ``method`` *GET*
            * ``content-type`` *application/json*

        **参数**:
            * ``appkey`` *(String)* - 参数类型, *(App 标识)*
            * ``transfer_id`` *(String)* -参数类型, *订单号*


        **返回值**
            * ``transfer_id`` *(String)* -参数类型, *订单号*
            * ``status`` *订单状态值  0初始化   1扫描支付   2支付成功  3支付超时*





比特派 Bitpie 支付成功回调
--------------------------------------------------


        **请求 API **:
            * ``url`` */api/pay/callback*
            * ``method`` *POST*
            * ``content-type`` *application/json*

        **参数**:
            * ``transfer_id`` *(String)* -参数类型, *订单号*
            * ``nonce_string`` *(String)* -参数类型, *签名验证随机值*
            * ``sign_string`` *(String)* -参数类型, *签名验证随机值*
            * ``amount`` *(String)* -参数类型, *币数*
            * ``coin_code`` *(String)* -参数类型, *币种代码,例 BTC*
            * ``user_asset_flow_id`` *(String)* -参数类型, *比特派 Bitpie 交易流水号*
            * ``balance`` *(String)* -参数类型, *[true|false] 默认 true*
            * ``timestamp`` *(String)* -参数类型, *交易时间,毫秒级时间戳,没有小数点,纯数字*


        **返回值**
            * ``result`` *(String)* -参数类型, *[true|false]*





唤起支付
------------------------------


        **请求 API **:
            * ``url`` *bitpie://piebank/pay?order_id={transfer_id}&amount={amount}&coin_code={coin_code}&app_name={app_name}*


        **参数**:
            * ``transfer_id`` *(String)* -参数类型, *订单号*
            * ``amount`` *(String)* -参数类型, *币数*
            * ``coin_code`` *(String)* -参数类型, *币种代码,例 BTC*
            * ``app_name`` *(String)* -参数类型
