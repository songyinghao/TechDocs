#To DO List

---

####20150822

* rancher 文档

####20160823

* 共用代码`Common`模块的抽象类,制作成`composer`包,可以协同各个服务模块调用(`done`)
* 把`composer`包所有框架服务区分开`dev`和`production`,为了减少`production`不必要的代码量(`done`)

####20160824

* 整理`ppt`需求(`done`)
* 整理框架的`json-api`第三方扩展,样例代码(`done`),文档(`not done`)
* 整理`command`->`commandHandler`->`domain`(`代码设计done`)
->`event`(`not done`)

####20160825

* 自动化`rancher`
* `rancher`更新方案

####20160826

* 处理报价方案(`done`)
* `ansible`自动化部署`rancher server`(`done`)

####20160827

* `ansible`自动化部署`rancher agent`和向服务端`注册`(`done`)
* 框架使用`faker`自动化生成测试数据(根据配置文件生成数据库桩文件)

####20160829

* 框架文档补充(`done`)
* `faker`自动生成测试数据库功能(`done`),替换原来每次固定手写,`重写phpunit文件`,改为自动生成规范数据在数据表内.

####20160830 

* `mongo 3.2` 镜像(`done`),更新在`docker-compose.yml`内.
* `rock mongo` mongo数据库管理工具(`done`),更新在`docker-compose.yml`内.
* `mongo-php-7` 框架支持(`done`).

#####20160831

* rancher 文档(`翻译一些核心内容`,`done`)
* 事件源存储(未定)
* jenkins 文档, 阅读了一部分
* 配置分离(开发,沙箱,生产环境 对所有项目可以实现配置隔离) (`etcd`, `confd`)(`etcd`单独服务器部署`done`,`etcd`未部署在集群内)

#####20160901 - 20160902

* rancher 文档 (`done`),更新方案
* 事件 - 队列 - 代码 (`not done`)
* docker 修改存储方案 (Logical Volume)(`done`,`文档`)
* 数据卷容器(`开发中`)

####待处理

* `pdepend` [https://pdepend.org/documentation/getting-started.html](https://pdepend.org/documentation/getting-started.html "https://pdepend.org/documentation/getting-started.html")
* `phpmd` [https://phpmd.org/documentation/index.html](https://phpmd.org/documentation/index.html "https://phpmd.org/documentation/index.html")
* `后续工作`: 主要用于容量测试,测试我们一台机器可以最大跑多少数据.后续可以在做开发版本的时候优化.可以统一优化到镜像内.
	* `php.ini`配置优化. 
	* `nginx`配置优化
	* `phpfpm 进程池`配置优化
* `生产环境在运行PHP服务器上开启huge page`.(不急)
	
	


