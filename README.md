启动命令本来是这样的
但是我把多余的配置全部去掉了

$ STORAGE_TYPE=elasticsearch ES_HOSTS=http://myhost:9200 java -jar zipkin.jar

直接在配置文件里修改吧

collector支持多个同时传输
zipkin.collector.http.enabled 代表启动web

如果http连接支持
  zipkin:
    baseUrl: http://trace/
和
 http://localhost:9411两种方式
上面的trace是在eureka注册的服务名及本服务的spring.application.name

加入了eureka依赖

配置项在zipkin/zipkin/zipkin-server/src/main/resources/zipkin-server-shared.yml中

## 打包

```shell script
cd zipkin
mvn clean package
```

## 启动

```shell script
java -java ./zipkin-server/target/zipkin-server-2.16.2-exec.jar
```
 
