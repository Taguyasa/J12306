# J12306抢票助手
12306抢票程序JAVA版，自动登录-验证-查票-购票/自动候补。只需简单的配置即可运行进行快捷抢票。

### 使用说明
##### 引入jar依赖
* 手动添加项目lib文件夹中的依赖包
##### 配置文件config.yml
```
# 请修改相关配置

# 12306账号密码配置（暂时没用到）
j12306:
  user: 182xxxx
  password: 123456

  ticket:
    queryspeed: 2 # 刷票速度。默认2秒
    alternate: true # 开启自动候补

  # 通知配置
  notice:
    # 电子邮件配置
    email:
      sender:
        from: hutool@yeah.net   # 发件人（必须正确，否则发送失败）
        host: smtp.yeah.net    # 邮件服务器的SMTP地址，可选，默认为smtp.<发件人邮箱后缀>
        port: 25    # 邮件服务器的SMTP端口，可选，默认25
        user: hutool    # 用户名
        pass: qlw2e3    # 密码（注意，某些邮箱需要为SMTP服务单独设置密码，详情查看相关帮助）
      receiver: 1481397688@qq.com   # 接收人邮箱
```

##### 配置抢票信息
* Main.java中，直接配置用户名密码及乘车相关信息即可
##### 开始抢票
* 直接运行Main函数开始抢票。就是这么简单粗暴！

##### 程序运行log
```
[2019-09-22 12:42:33] [INFO] com.kalvin.J12306.api.Login: 进入12306登录页，状态码：200
[2019-09-22 12:42:36] [INFO] com.kalvin.J12306.AI.Easy12306AI: 验证码：3,4
[2019-09-22 12:42:37] [INFO] com.kalvin.J12306.api.Login: 验证码通过，开始密码登录
[2019-09-22 12:42:37] [INFO] com.kalvin.J12306.api.Login: 登录成功
[2019-09-22 12:42:40] [INFO] com.kalvin.J12306.api.Ticket: 进入查询车票页面，开始查票...
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D2804，出发时间：07:06，到达时间：08:10，座席：一等座1、二等座12、无座有
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D1849，出发时间：07:23，到达时间：08:37，座席：一等座4、二等座有、无座无
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D7551，出发时间：09:23，到达时间：11:02，座席：一等座有、二等座有、无座有
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D2962，出发时间：09:35，到达时间：10:41，座席：一等座8、二等座14、无座有
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D2812，出发时间：10:05，到达时间：11:11，座席：一等座无、二等座2、无座无
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D1822，出发时间：11:00，到达时间：12:06，座席：一等座3、二等座无、无座无
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D2948，出发时间：11:34，到达时间：12:42，座席：一等座无、二等座无、无座有
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D2834，出发时间：15:15，到达时间：16:27，座席：一等座2、二等座2、无座有
[2019-09-22 12:42:42] [INFO] com.kalvin.J12306.Go12306: 可预订车票信息：发车日期：2019-09-26，车次：D2980，出发时间：17:19，到达时间：18:25，座席：一等座2、二等座20、无座有
[2019-09-22 12:42:46] [INFO] com.kalvin.J12306.api.CheckOrderInfo: 车票提交通过，正在尝试排队...
[2019-09-22 12:42:46] [INFO] com.kalvin.J12306.api.GetQueueCount: 排队成功，你当前排在6位，当前余票还有101张
[2019-09-22 12:42:46] [INFO] com.kalvin.J12306.api.ConfirmSingleForQueue: 不需要订单验证码，直接提交
[2019-09-22 12:42:46] [INFO] com.kalvin.J12306.api.ConfirmSingleForQueue: 开始正式下单...
[2019-09-22 12:42:48] [INFO] com.kalvin.J12306.api.QueryOrderWaitTime: 下单ing...正在第1次排队ing...
[2019-09-22 12:42:48] [INFO] com.kalvin.J12306.api.QueryOrderWaitTime: 订票成功！
[2019-09-22 12:42:48] [INFO] com.kalvin.J12306.api.QueryOrderWaitTime: 恭喜您订票成功，订单号为：EF71508610, 请立即打开浏览器登录12306，访问‘未完成订单’，在30分钟内完成支付!
[2019-09-22 12:42:48] [INFO] com.kalvin.J12306.api.QueryOrderWaitTime: 以邮件方式通知抢票人
[2019-09-22 12:42:48] [INFO] com.kalvin.J12306.Go12306: 抢票程序结束：STOP
```
### 问题反馈
如有疑问，可在项目上issues！

