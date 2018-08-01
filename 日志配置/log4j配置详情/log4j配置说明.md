# 1 - 基础配置结构
#### 配置根日志等级 并添加appender
log4j.rootLogger = info[日志等级] , appender1 , apperder2

#### 配置日志输出信息目的地 appender
log4j.appender.appenderName = xxxAppender.class
> 注意此处有一些细节配置


#### 配置日志输出格式
log4j.appender.appenderName.layout = xxxLayout.class
> 注意此处有一些细节配置

# 2 - 日志输出等级

|日志等级|级别|
|:---:|:---:|
|FATAL|0|
|ERROR|3|
|WARN|4|
|INFO|6|
|DEBUG|7|

# 3 - Appender 类型
|序号|类型|作用|
|:---:|:---:|:---:|
|1|org.apache.log4j.ConsoleAppender|控制台输出|
|2|org.apache.log4j.FileAppender|文件输出|
|3|org.apache.log4j.DailyRollingFileAppender|每天产生一个日志文件|
|4|org.apache.log4j.RollingFileAppender|文件到达指定大小生产一个新文件|
|5|org.apache.log4j.WriterAppender|将文件以流的形式发送到任意指定的地方|

# 4 - Layout 日志文件布局
|序号|布局类型|布局说明|
|:---:|:---:|:---:|
|1|org.apache.log4j.HTMLLayout|以HTML表格的形式布局|
|2|org.apache.log4j.PatternLayout|自定义布局指定Pattern|
|3|org.apache.log4j.SimpleLayout|简单布局包含日志等级和信息|
|4|org.apache.log4j.TTCCLayout|包括日志产生时间、线程、类别|

# 5 - Pattern语法
|序号|语法|含义|
|:---:|:---:|:---:|
|1|%m|输出代码中指定的信息|
|2|%p|输出该日志优先级|
|3|%r|输出应用自启动到输出该日志信息耗费的时间|
|4|%c|输出所属类目 通常是累的全名|
|5|%t|输出产生该日志的线程名称|
|6|%n|输出一个换行|
|7|%d|输出日志打印时间可指定格式 %d{yyyy MM dd HH:mm:ss SSS}|
|8|%I|输出日志事件发生的位置 类目名称 线程 代码中的行数|

# 6 - 配置demo
#### 1 - 控制台输出配置
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
log4j.appender.fileAppender.datePattern = '.'yyyy-MM-dd #文件名pattern
```















