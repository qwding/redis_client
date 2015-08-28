# redis_client

###小述
* 这是一个简单的redis使用客户端，用go语言编写。
* 下载代码后可以构建一下，即可运行
* 使用的是redigo包，采用连接池来连接，
* 使用方法 `./main -host=myredis.com:6379 -db=0 -password=mima`,默认的话连接127.0.0.1:6379,密码为password
* 输入 `help` 可查看帮助

### 使用方法
 
* 类似命令行输入 
* `keys *`查看所有键值对
* `hgetall mykey_big` 获取hash存储key为mykey_big的键值
* most redis command
 

### 增加了自己添加的新功能，
* 群删键值 `delkeys 2015_08_27_*` 删除所有 2015_08_27_ 开头的键值
* 待增加...


### 缺陷
* 因为引用redigo这个包，导致传递参数时候是interface，所以在传递参数的时候不能直接用切片传递可变长的key-value。所以很笨重的手写的不同长度的参数传递。（求指点）
* 传递过程中常会出现EOF错误，原因未知，所以出现EOF就继续发了请求，目前不影响使用，（待解决）。
