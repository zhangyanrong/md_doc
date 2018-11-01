* 查看命令
    1. Npm list  // 查看本地已安装模块清单
    2. npm list [packageName] // 查看本地已安装模块版本
    3. npm info [packageName] //查看模块的详细信息 包括各版本号等
    4. npm view [packageName] version // 查看模块远程最新版本
    5. npm view [packageName] versions // 查看模块远程所有版本
* 安装
    1. npm install [packageName] //安装模块
    2. npm install [packageName]@xxx.xx //安装模块的指定版本
    3. npm install [packageName]  -g //全局安装模块
    4. npm install [packageName] --save 安装好后写入package.json的dependencies中（生产环境依赖）
    5. npm install [packageName] --save-dev 安装好后写入package.json的devDepencies中（开发环境依赖）
* 卸载
    1. npm uninstall [packageName] // 删除模块
    2. npm uninstall [packageName] -g //卸载全局模块
    3. npm uninstall [packageName] --save  // 删除模块，同时删除模块留在package.json中dependencies下的对应信息
    4. npm uninstall [packageName] --save-dev  // 删除模块，同时删除模块留在package.json中devDependencies下的对应信