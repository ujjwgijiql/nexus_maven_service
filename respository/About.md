# About respository     
## 作用    
指定私服的中央地址、将自己的Maven项目指定到私服地址、从私服下载中央库的项目索引、从私服仓库下载依赖组件、将第三方项目jar上传到私服供其他项目组使用。   
有些公司都不提供外网给项目组人员，因此就不能使用maven访问远程的仓库地址，所以很有必要在局域网里找一台有外网权限的机器，搭建nexus私服，然后开发人员连到这台私服上，这样的话就可以通过这台搭建了nexus私服的电脑访问maven的远程仓库。
如果某个IP地址恶意的下载中央仓库内容，例如全公司100台机器使用同一个IP反复下载，这个IP（甚至是IP段）会进入黑名单，因此稍有规模的使用Maven时，应该用Nexus架设私服。总归主要是两点：    
1、自己maven私服更容易维护，公司开发从maven私服迁出jar到本地仓库更快    
2、有些公司未开放外网给开发人员   
&nbsp;   
## respository Type
* proxy：是远程仓库的代理。最典型的就是Maven官方中央仓库、JBoss仓库等等。    
         比如说在nexus中配置了一个central repository的proxy，当用户向这个proxy请求一个artifact，这个proxy就会先在本地查找，如果找不到的话，就会从远程仓库下载，然后返回给用户，相当于起到一个中转的作用；
* Hosted：是宿主仓库，用户可以把自己的一些构件，deploy到hosted中，也可以手工上传构件到hosted里。    
         用来发布一些第三方不允许的组件，比如说oracle的驱动程序，ojdbc6.jar，商业软件jar包，在central repository是获取不到的，就需要手工上传到hosted里；
* Group：是仓库组，在maven里没有这个概念，是nexus特有的。    
        目的是将上述多个仓库聚合，对用户暴露统一的地址，这样用户就不需要在pom中配置多个地址，只要统一配置group的地址就可以了右边那个Repository Path可以点击进去，看到仓库中artifact列表。不过要注意浏览器缓存。    




