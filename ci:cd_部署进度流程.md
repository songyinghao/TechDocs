#CI/CD 部署进度流程

---

###前期准备工作(3 days)

* 通读rancher文档,以及自动化构建工具
* 确定测试数据`桩`的开发
* 确定队列交互形式(RabbitMq,队列传输模式)
* 确定事件源存储

###需要开发工作

####环境自动化(2 days)

**开发服务器环境自动化部署脚本**

* 使用ansbile自动化部署开发环境rancher server 和 rancher agnet
* 部署阿里云监控工具

**开发电脑自动化环境部署脚本**

* 使用ansible通过docker源compose文件部署开发电脑环境

**开发服务器不停机升级环境**

* 编写自动化脚本对服务器rancher环境进行升级,以不影响业务正常运行为前提

####docker 生产环境优化(1.5 days)

* `direct-lv` 替换原来默认的 `loop-lvm`,并编写自动化脚本.[链接](https://docs.docker.com/engine/userguide/storagedriver/device-mapper-driver/, "https://docs.docker.com/engine/userguide/storagedriver/device-mapper-driver/") 

####开发服务器SQl AND No-SQl(2 days)

* 部署数据库Mysql,编写自动化脚本
* 部署memcached * 3,编写自动化脚本
* 部署Mongo,编写自动化脚本
* 编译php7 针对Mongo扩展

####开发服务器队列(1 day)

* 部署rabbitMq,编写自动化脚本
* 需要确认高可用部署方式(生产环境会需要使用)

####优化微服务框架(3 days)

* 给框架编写事件驱动流模式
* 编写命令模式
* json-api格式输出优化

####Mock数据生成器(2 days)

* 还未确定Mock数据生成器是否使用PHP编写,主要用于在初期解耦和前端的开发.可以让前端后端并行开发.

####修改框架支持view层现实(4 days) ?

* 为框架编写显示层
* 为框架编写适配器(针对rest)
* 为框架编写防腐层(针对rest)
* 前端自动化测试工具

####PHP自动化工具部署(1 day)

* phpcs(代码风格检测)
* phpcpd(代码耦合性检测)
* phpunit(单元测试)
* behat(行为驱动测试)
* phpmd(代码复杂度分析工具)
* faker(自动生成测试数据)
* mink(端到端测试)

####Jenkins(5 days),较为麻烦

* 编写jenkins2.0构建流水线
* 测试环境自动化集成测试
* 测试环境自动化代码风格检测
* 输出结果呈现
* 代码蓝绿发布

###演示流程

####自动化环境部署

自动化部署代码开发环境,在阿里云服务器测试(因为,本地网络访问github会时不时遇见域名无法解析)

####蓝绿部署

代码部署后可以迅速回滚,以及发布.

####代码自动化发布

* 从开发电脑(阿里云主机)git不发代码,运行自动化测试,自动化检测,自动化部署到生产(服务器)

####数据前端服务器可以从后端服务器接口获取到数据

* 数据发布,访问正常