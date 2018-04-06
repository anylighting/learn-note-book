


### 1.镜像地址

>
>* cnpm: http://registry.cnpmjs.org
>* 淘宝镜像: https://registry.npm.taobao.org
>

### 2.操作方法
1. 用命令配置
>
>* npm config set registry https://registry.npm.taobao.org 
>* npm info underscore （这个只是为了检验上面的设置命令是否成功，若成功，会返回[指定包]的信息）

2. 修改配置文件
>* 修改配置文件~/.npmrc （win系统在C:\Users\用户名.npmrc） 加入下面内容
>* registry = https://registry.npm.taobao.org
