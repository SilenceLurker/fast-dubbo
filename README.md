# fast-dubbo

为了快速Spring Dubbo应用开发提供的pom，可通过pom添加依赖或设置为父工程

## 导入依赖

设置为父工程：

```xml

    <parent>
        <groupId>xyz.silencelurker</groupId>
        <artifactId>fast-dubbo</artifactId>
        <version>0.1.3</version>
        <relativePath/> <!-- lookup parent from repository-->
    </parent>

```

导入依赖：

```xml
    <dependency>
        <groupId>xyz.silencelurker</groupId>
        <artifactId>fast-dubbo</artifactId>
        <version>0.1.3</version>
        <type>pom</type>
    </dependency>
```

以上两种任选其一即可

## 使用

可以按照基础的Spring Boot项目进行开发，但需要先在application.properties文件中添加基础配置信息

```properties
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver
# MySQL数据库用户名
spring.datasource.name=
# MySQL数据库密码
spring.datasource.password=
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

spring.main.show-banner=false
logging.level.jdbc=ON
logging.level.jdbc.sqltiming=DEBUG
logging.level.jdbc.resultsettable=DEBUG

spring.config.import=zookeeper:127.0.0.1:2181
spring.cloud.zookeeper.connect-string=localhost:2181

spring.cloud.zookeeper.discovery.enabled=true

dubbo.application.name=fast-dubbo
dubbo.registry.address=zookeeper://${zookeeper.address:127.0.0.1}:2181
dubbo.protocol.name=dubbo
dubbo.protocol.port=-1

```
