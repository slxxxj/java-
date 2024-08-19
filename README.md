# java-druid
记录遇到的坑

试过3种方法配置：
1: 直接配置
druid:
connectionTimeout: 300000
socketTimeout: 300000

2：jdbcurl中加参数
url: jdbc:sqlserver://****;loginTimeout=300000;socketTimeout=300000

3：配置connectionProperties属性
druid
connectionProperties: loginTimeout=300000;socketTimeout=300000

3种方式配置，最终通过druid创建出来的SqlServerConnection中，loginTimeout都是10，socketTimeout都是10000

据说 从 1.2.12 ~ 目前最新1.2.21 版本都有这问题， 只能退回 1.2.11 版本 
<!-- Druid -->
<dependency>
    <groupId>com.alibaba</groupId>
    <artifactId>druid-spring-boot-starter</artifactId>
    <version>1.2.11</version>
</dependency>
