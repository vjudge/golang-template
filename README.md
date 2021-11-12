# golang-seed
go 工程化项目

## Go 工程目录介绍

### /cmd
项目主要的应用程序
* 不要在该目录中放太多代码
* 每个应用程序的目录名，和项目可执行文件名字匹配
* 项目 main 函数一般比较小，可以在其中导入或者调用 /internal 和 /pkg 目录中的代码


### /internal
私有的应用程序代码库，不希望被其他人导入的代码
* Go 编译器强制执行
* 在项目的目录树中，任意位置都可以有 /internal 目录


### /pkg
外部应用程序可以使用的库代码
* 将代码放在这里前，一定要三思而行
* 其他项目将会导入这些库来保证项目可以正常运行


### /vendor
应用程序的依赖关系
* 执行go mod vendor命令将会在项目中创建/vendor目录
* 如果使用的不是Go1.14 版本，在执行 go build 进行编译时，需要添加 -mod=vendor 命令行选项，它不是默认选项


### /api
OpenAPI/Swagger规范，JSON模式文件，协议定义文件


### /web
Web应用程序特定的组件
* 静态Web资源
* 服务器端模板
* 单页应用(Single-Page App，SPA)


### /configs
配置文件模板或默认配置
* 将 confd 或者 consul-template 文件放在这里


### /init
系统初始化(systemd、upstart、sysv)和进程管理(runit、supervisord)配置


### /scripts
用于执行各种构建，安装，分析等操作的脚本


### /build
打包和持续集成
* 将云(AMI)，容器(Docker)，操作系统(deb，rpm，pkg)软件包配置和脚本放在 /build/package 目录中
* 将 CI(travis、circle、drone)配置文件和脚本放在 build/ci 目录中


### /deploy (也可以是: /deployments)
IaaS，PaaS，系统和容器编排部署配置和模板


### /test
外部测试应用程序和测试数据，随时根据需要构建 /test 目录
* 对于较大的项目，有数据子目录更好
* Go 会忽略以 . 或 _ 开头的目录或文件，可以比较灵活的来命名该目录下的文件


### /tools
项目支持的工具


### /docs
项目开发设计文档和用户文档


### /examples
应用程序或公共库的示例


### /third_party
外部辅助工具，fork 的代码和第三方工具


### /githooks
git 的钩子


### /assets
项目中使用的其他资源。(如图像，文件，logo等)


### /website
放置项目的网站数据


### 不应该出现的目录
* /src



## Go 项目介绍

### golang-seed
初始化go项目


### 功能特性
初始化好的项目，可直接开始开发


### 软件技术
框架: gin + redis + mysql


### 项目构建


### 项目运行




### go mod
```shell
go mod init golang-seed
```




##### 参考项目: https://github.com/golang-standards/project-layout
