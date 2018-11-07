### 微北洋调试用代理

- 终端或 cmd 界面配置 adb 环境变量

- 手机安装 debug 版微北洋，打开并登录，使用数据线连接电脑

- 终端或 cmd 界面执行 `adb forward tcp:10080 tcp:10086`

- 使用 Postman 等调试工具调试，地址输入 `http://127.0.0.1:10080/` 后面加上要调试的接口地址 (去掉 https://)，如 (括号内为编译代码分支)

  (Oct.16th branch `master`/ `refactor` 分支)

  `http://127.0.0.1:10080/api/v1/app/message`

  (Oct.16th branch`exam`)

  ` http://127.0.0.1:10080/open.twtstudio.com/api/v1/app/message`

  具体看 `app.java.com.twt.service.push.DebugProxyServer` 文件中 39 行 `handle` 方法中 `baseUrl` 变量。

  其余和调试原接口时操作一样，发出的请求包就是自动带微北洋登录 Header 的。


