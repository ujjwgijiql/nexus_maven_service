__1. 进入nexus页面__    
    http://localhost:8081/    
&nbsp;    
__2. 使用管理员用户登录：__    
    用户名：admin    
    密码：admin123    
&nbsp;    
__3. 新建仓库__    
    这里需要解释一下我们需要的仓库类型:
  * 我们需要一个代理仓库从网上下载安装包，    
  * 需要一个release仓库保存已经发布的上线的安装包，    
  * 还需要一个snapshot用来保存快照的私仓。    
  * 最后，这些私仓需要一个统一的访问入口，就是私仓组。    
&nbsp;    
__3.1. proxy repository__    
    在Repository Tab点击【Add】->【Proxy Repository】    
    使用的外部私仓是阿里的仓库http://maven.aliyun.com/nexus/content/groups/public    
  ![proxy_repository](https://github.com/zhang-jh/nexus_maven_service/blob/master/images/proxy_repository.png)    
&nbsp;    
__3.2. release repository__    
    
