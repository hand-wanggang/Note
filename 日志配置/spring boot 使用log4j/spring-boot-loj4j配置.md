# 1 - Spring Boot使用log4j配置
##### 1、 排除spring boot 自带的logging 启动器
```
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web-services</artifactId>
            <exclusions>
                <exclusion>
                    <groupId>org.springframework.boot</groupId>
                    <artifactId>spring-boot-starter-logging</artifactId>
                </exclusion>
            </exclusions>
        </dependency>
```

##### 2、添加spring-boot-starter-log4j 启动器
```
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-log4j</artifactId>
            <version>1.3.8.RELEASE</version>
        </dependency>
```
##### 3、编写log4j配置文件
```
#配置根日志等级
log4j.rootLogger = debug , stdout , fileAppender

# 配置控制台日志输出
log4j.appender.stdout = org.apache.log4j.ConsoleAppender
log4j.appender.stdout.target = System.out
log4j.appender.stdout.layout = org.apache.log4j.PatternLayout
log4j.appender.stdout.layout.conversionPattern = %d{yyyy-MM-dd HH:mm:ss SSS} %5p %c{1}:%L - %m%n

# 配置文件日志输出
log4j.appender.fileAppender = org.apache.log4j.DailyRollingFileAppender
log4j.appender.fileAppender.file = logs/presale.log
log4j.appender.fileAppender.append = true
log4j.appender.fileAppender.threshold = DEBUG
log4j.appender.fileAppender.layout = org.apache.log4j.PatternLayout
log4j.appender.fileAppender.layout.conversionPattern = %d{yyyy-MM-dd HH:mm:ss SSS} %5p %c{1}:%L - %m%n
log4j.appender.fileAppender.datePattern = '.'yyyy-MM-dd
```
> 注意：该文件需要放在resource目录下 否则无法启动log4j环境