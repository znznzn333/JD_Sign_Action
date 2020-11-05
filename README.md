# 基于github action的京东自动化签到

## 介绍

> 使用NobyDa “京东多合一签到脚本”为基础，移植到github actions自动化执行。 

## 触发方式
* 点亮`Star`
* 凌晨4点定时执行
*  自定义：.github/workflows/work.yaml 编辑
* 修复未自动运行Bug--修改过除 .workflow/ 下的任意文件（https://github.com/ZHDeveloper/JD_Sign_Action/issues/3#issuecomment-687539436）

## 使用用法
* 点击右上角 `Fork` 项目；
* `Settings` -> `Secrets` 中添加京东Cookie、Server酱SCKEY；
	- `JD_COOKIE`：账号1Cookie
	- `JD_DUAL_COOKIE`：账号2Cookie(选填)
	- `PUSH_KEY`：Server酱SCKEY
* 点击`Star`，任务会自动执行，运行进度和结果可以在`Actions`页面查看；
* 当任务运行完成时，会将运行结果和错误信息打包到`Artifacts`，可自行下载查看；
* 如果配置了Server酱，运行结果会推送到微信；

## 获取京东cookie
### cookie有效期：一个月

方法一：
* 使用项目中的Chrome插件：`JDCookie`；
* Chrome中拓展程序开启`开发者模式`；
* 点击`加载已解压的拓展程序`，选择`JDCookie`目录；
* 登录[领京豆](https://bean.m.jd.com/)；
* 点击`JDCookie`即可拷贝京东cookie；

方法二（推荐）
* 京东页面登录成功后，按F12，选择右侧工具栏中的 console 然后在下放输入 copy(document.cookie) 它会拷贝当前的 cookie， 然后在一个文本编辑器中或其他可编辑的窗口中粘贴即可
  ![方法二](https://raw.githubusercontent.com/Crazyguy2020/JD_Sign_Action/master/方法三.jpg)


方法三：
* 图文教程(https://www.bilibili.com/read/cv7597205)
* 1.电脑浏览器打开京东网址： https://m.jd.com/ 
* 2.右下角点击“我的”，登陆账号，会弹出二维码，在二维码右上方点击“直接登陆”就可以了,登陆完后，按f12
* 3.然后点击右上方里面的“network”，点击灰色的（如图所示），然后重新点击“我的”* 然后找到“log.gif?t=wg_wx.******”开头的点击进去
* 4.点击之后，下拉，找到cookie，然后复制就可以了，这个很长，记得cookie这一栏都复制了(cookie:  后面一串）
* 5.完工
  ![步骤一](https://raw.githubusercontent.com/Crazyguy2020/JD_Sign_Action/master/1.webp)
  ![步骤二](https://raw.githubusercontent.com/Crazyguy2020/JD_Sign_Action/master/2.webp)

## 获取Server酱SCKEY

* github 授权登录[Server酱](http://sc.ftqq.com/3.version)官网；
* 菜单栏`微信推送`扫描绑定微信；
* 菜单栏`发送消息`拷贝SCKEY；



## 效果截图

![WechatIMG3](./images/WechatIMG3.jpeg)

![WechatIMG4](./images/WechatIMG4.jpeg)


## 参考项目
* [NobyDa/Script/JD-DailyBonus](https://github.com/NobyDa/Script/blob/master/JD-DailyBonus/JD_DailyBonus.js)
* [ruicky/jd-sign-bot](https://github.com/ruicky/jd_sign_bot)
* [jerrykuku/luci-app-jd-dailybonus](https://github.com/jerrykuku/luci-app-jd-dailybonus)
