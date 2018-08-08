比特派 Bitpie 转账
=================================


转账
--------------


      **API**
         * ``url`` */api/v1/open/third/party/transfer*
         * ``method`` *POST*
         * ``content-type`` *application/json*


      **参数**
         * ``app_key`` *(String)* -参数类型
         * ``user_id`` *(String)* -参数类型, *用户 bitid*
         * ``coin_code`` *(String)* -参数类型, *币种代码*
         * ``amount`` *(String)* -参数类型, *币种数量*
         * ``transfer_id`` *(String)* -参数类型, *订单号*
         * ``sign_string`` *(String)* -参数类型
         * ``nonce_string`` *(String)* -参数类型
         * ``timestamp`` *(String)* -参数类型


      **返回值**
         * ``status`` * 0000 成功,12208 重复*
         * ``coin_code`` *币种代码*
         * ``balance``
         * ``user_asset_flow_id`` *流水号*



转账查询
---------------------


      **API**
         * ``url`` */api/v1/open/third/party/app/{app_key}/flow/{transfer_ids}*
         * ``method`` *GET*
         * ``content-type`` *application/json*


      **参数**
         * ``app_key`` *(String)* -参数类型
         * ``transfers_id`` *(String)* -参数类型, *订单号*
