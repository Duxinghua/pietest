
用户登录 API
====================================


流程
-------------------

登录 --> 服务器获取登录二维码 --> 服务器获取二维码状态 --> 比特派 APP 用户扫描登录 -->  登录成功获取用户信息



登录获取二维码
-------------------

        **请求 API **:
            * ``url`` */api/v1/open/third/party/login/qr*
            * ``method`` *POST*
            * ``content-type`` *application/json*

        **参数**:
            * ``appkey`` *(String)* - 参数类型, *(App 标识)*

        **返回值**
            * ``time`` *时间戳*
            * ``hkey`` *QR标识*
            * ``qr_info``
            * ``qr_url``




获取二维码状态
--------------------------

        **请求  API **
            * ``url`` */api/v1/open/third/party/login/query/{hkey}*
            * ``method`` *GET*
            * ``content-type`` *application/json*

        **参数**
            * ``hkey`` *QR标识*

        **返回值**
            * ``hkey`` *QR标识*
            * ``status`` *登录状态值 0:初始化 1:扫描 2:登录 3:超时*




获取用户信息
-----------------------

        **请求 API**
            * ``url`` */api/v1/open/third/party/login/query/{hkey}*
            * ``method`` *POST*
            * ``content-type`` *application/json*

        **参数**
            * ``appkey`` *(String)* -参数类型,*(App 标识)*

        **返回值**
            * ``hkey`` *QR标识*
            * ``status`` *登录状态值 0:初始化 1:扫描 2:登录 3:超时*
            * ``token``
            * ``bitid``