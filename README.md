## 启动spring命令，使用docker镜像容器

1、在项目路径下进入命令行窗口输入命令：
~~~
mvn spring-boot:run
~~~

2、正常启动后访问
<http://localhost:8080/>

3、使用mvn命令打包spring项目
~~~
mvn clean package -DdiskTests
~~~

4、构建/重新构建docker镜像
~~~
docker build -t docker-spring-demo .
~~~

5、停止容器运行
~~~
docker stop spring-demo
~~~

6、如果存在旧容器删除后重新启动容器，
~~~
docker rm -f spring-demo
docker run -d -p 8080:8080 --name spring-demo docker-spring-demo
~~~

7、再次访问
<http://localhost:8080/>

8、如果访问失败，用命令查看日志
~~~
docker logs spring-demo
~~~
