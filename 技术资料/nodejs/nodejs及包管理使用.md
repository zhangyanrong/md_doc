#### nodejs及包管理使用
* 一、安装node和npm
    1. brew install node

* 二、安装express
    1. npm install -g express
    2. npm install -g express-generator      express版本4以上需要安装
    3. npm install -g node-dev    安装node-dev
    4. npm run dev			启动后每次修改会自动重启

* 三、npm账号
    1. 官网注册账号:nick_zyr  cy1986....
    2. token: 86efa005-ad89-40d9-99ff-dcd4a6c2b3f8
    3. 在命令行输入然后登录:npm login
    
* 四、nodejs升级版本
    1. npm install -g n
        * 全局安装n
    2. n stable 
        * 升级到最新稳定版
    3. n lastest
        * 升级到最新版
    4. n v7.10.0
        * 升级到定制版
    5. n 7.10.0
        * 切换使用版本
* 五、查看npm相关包的版本信息
    1. npm view <package> versions
        * 这种方式可以查看npm服务器上所有的package版本信息
    2. npm view <package> version
        * 这种方式只能查看package的最新的版本是哪一个
    1. npm ls <package> 
        * 查看本地安装的package的版本(不包括全局安装的package)
    3. npm ls <package> -g
        * 查看本地安装的package的版本(全局安装的package)