
## 项目地址：https://code.dogs.ren/docs
- 打开网址如果白屏的话需要科学上网
## 项目群：241546470
- 项目介绍：集成多平台（战网、微软、Steam）服务的工具服务器！
- 提供登录、授权、信息查询等功能，更多的平台正在开发中。并且支持免费定制！
- 使用凭据进群联系获取，目前免费使用全接口！

## 战网（Battle）模块接口
路由文件： product/battle/router.py

### 1. 战网登录接口
- 路径 ： POST /battle/login
- 功能 ：战网账号登录（支持微软邮箱自动取验证码登录）
- 参数 ：
  - cid （必选）：客户端ID
  - email （必选）：用户名
  - pass_ （必选）：密码
  - epass （可选）：邮箱密码
  - imap （可选）：IMAP连接信息
### 2. 战网查询游戏概况接口
- 路径 ： GET /battle/games/status
- 功能 ：查询战网账号关联的游戏概况
- 参数 ：
  - cid （必选）：客户端ID
### 3. 战网查询连接概况接口
- 路径 ： GET /battle/connect/status
- 功能 ：查询战网账号的连接状态概况
- 参数 ：
  - cid （必选）：客户端ID
### 4. 战网查询XGP会员绑定状态接口
- 路径 ： GET /battle/connect/xgp/bind/status
- 功能 ：查询战网账号与XGP会员的绑定状态
- 参数 ：
  - cid （必选）：客户端ID
### 5. 战网绑定XGP会员接口
- 路径 ： GET /battle/connect/xgp/bind
- 功能 ：绑定战网账号与XGP会员
- 参数 ：
  - cid （必选）：客户端ID
  - email （必选）：XGP用户名
  - pass_ （必选）：XGP密码
### 6. 战网取消XGP绑定接口
- 路径 ： GET /battle/connect/xgp/unbind
- 功能 ：取消战网账号与XGP会员的绑定
- 参数 ：
  - cid （必选）：客户端ID

----------------------------------------------

## 微软（Microsoft）模块接口
路由文件： product/microsoft/router.py

### 1. 微软登录接口
- 路径 ： GET /microsoft/login
- 功能 ：微软账号登录
- 参数 ：
  - cid （必选）：客户端ID
  - username （必选）：用户名
  - password （必选）：密码
### 2. 微软授权接口
- 路径 ： GET /microsoft/auth
- 功能 ：微软账号授权（用于第三方应用访问）
- 参数 ：
  - cid （必选）：客户端ID
  - auth_page_url （必选）：授权页面URL
### 3. 微软获取最新邮件接口
- 路径 ： GET /microsoft/emails
- 功能 ：获取微软邮箱的最新邮件（支持按主题模式匹配）
- 参数 ：
  - cid （必选）：客户端ID

----------------------------------------------

## Steam模块接口
路由文件： product/steam/router.py

### 1. Steam登录接口
- 路径 ： POST /steam/login
- 功能 ：Steam账号登录（支持微软邮箱自动取验证码登录）
- 参数 ：
  - cid （必选）：客户端ID
  - user （必选）：用户名
  - pass_ （必选）：密码
  - email （可选）：邮箱地址
  - epass （可选）：邮箱密码
  - imap （可选）：IMAP连接信息
### 2. Steam设置随机头像接口
- 路径 ： GET /steam/profile/set_random_avatar
- 功能 ：为Steam账号设置随机头像
- 参数 ：
  - cid （必选）：客户端ID