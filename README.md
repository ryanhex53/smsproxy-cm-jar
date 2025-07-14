# 慈铭体检阿里云短信

## 介绍
通过阿里云短信服务发送体检通知短信和查报告的验证码，并将`已发送`、`已收到`、`发送错误`真实反应到业务系统中

## 使用方法
1. 在阿里云控制台开通短信服务
2. 在阿里云控制台创建短信签名和模板
3. 在阿里云控制台获取 AccessKeyId 和 AccessKeySecret，并设置到环境变量中
   - `ALISMS_ACCESS_KEY_ID`
   - `ALISMS_ACCESS_KEY_SECRET`
4. 设置签名变量`ALISMS_SIGN_NAME`
5. 设置验证码的模板变量`ALISMS_DEFAULT_TEMP_CODE`

## 其他环境变量说明
- `DB_HOST` 数据库主机地址
- `DB_NAME` 数据库名称
- `DB_USER` 数据库用户名
- `DB_PASSWORD` 数据库密码

## 运行模式设置
- 默认模式，只进行报告查询的注册验证码转发，默认运行在`8061`端口，不会连接数据库，不会进行体检系统的短信转发。如果要使用其他端口，可以设置运行参数`--server.port=NNN`；
- 设置运行参数`--spring.profiles.active=db`进入体检数据库运行模式，将会连接数据库，并进行体检系统的短信转发。

## 依赖的数据库表结构
表名`T_MSG_SENDTASK`,列`STATUS`,`CONTENT`
