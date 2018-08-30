#### 环境变量
compose配置文件允许我们动态的传入环境变量。
运行docker-compose up的时候，compose会先去我们当前的shell的环境变量中查找WEB_PORTS，找到了则为它赋值。如果没找到则compose会抛出错误。

compose也支持使用环境变量配置文件的方式引入变量，docker-compose.yml的目录下面创建一个.env的文件，compose运行的时候会去读取它。

不过，如果我们当前的shell环境中也含有同名的变量，则compose会以shell环境变量优先，即shell环境变量会覆盖.env配置文件中的同名变量。

#### Docker network

> 官方文档中可以看出--link已经标记为删除，可能在后面的版本中会直接删除该指令。
从安全性角度考虑及官方文档都建议使用docker network来完成容器之间的通信。

