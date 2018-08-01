# 一、开放端口 6381
iptables -I INPUT -p tcp --dport 6381 -j ACCEPT

* 其中 –I 参数就是添加一条规则的意思，还可以用-A添加在最后面，但是我试了会失效，可能是因为前面的规则优先的原因吧，还有待考究
* INPUT 是进入规则，同样还有OUTPUT
* -p 就是protocol什么协议的意思
* --dport是destination port的意思，目标端口
* -j就是制定规则的，可以是ACCEPT、DROP

# 二、查看规则添加成功
iptables -L -n  | grep 6379

# 三、保存添加的規則
service iptables save

> root用戶下执行以上命令
