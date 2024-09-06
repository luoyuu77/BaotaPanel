# 宝塔Windows历史版本存档
由于宝塔官方的历史版本下载链接失效，故收集了一波历史版本以供使用,可通过降级到历史版本绕过强制绑定手机号以及免费使用专业版插件

# 版本说明




# 使用方法
[宝塔回退7.4.5之前版本教程](https://blog.csdn.net/saygoodbyeyo/article/details/132534437)

[宝塔回退7.7.0版本，修改js绕过登陆限制](https://blog.csdn.net/saygoodbyeyo/article/details/132540562)

[宝塔免费使用专业版插件教程](https://blog.csdn.net/saygoodbyeyo/article/details/132542724)

### 安装宝塔

先使用宝塔官方的安装程序安装最新版宝塔
* 下载地址：http://download.bt.cn/win/panel/BtSoft.zip

### 降级版本
实用cmd命令行工具执行下面命令
```
wget https://raw.githubusercontent.com/luoyuu77/BaotaPanel/main/win/panel/data/setup.py -O C:/update.py && "C:\Program Files\python\python.exe" C:/update.py update_panel 7.2.0
```
最后重启一下面板

# 注意事项

* 宝塔降级后会出现密码不正确的情况，修改密码即可（bt 5）
* 降级成功后建议将宝塔修改为离线模式，进入宝塔面板，选择面板设置 -> 离线模式即可

# 宝塔降级常见问题

* Q：降级后显示宝塔无法启动，但无任何报错

  S：需要将markupsafe==2.0.1添加到panel目录下的requirements.txt文件中并执行
```
/www/server/panel/pyenv/bin/pip3 install -r requirements.txt
```
安装python库后重启面板即可

* Q：降级后登录宝塔面板时提示密码错误

  S：需要在终端修改宝塔密码

* Q：降级后登录宝塔面板时无法显示验证码图片或无法下载文件

  S：需要将/www/server/panel/BTPanel/\_\_init\_\_.py文件中的send_file函数中的cache_timeout参数名改为max_age
