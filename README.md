# cloudgo
# 16340299  赵博然
## 安装
```
go get github.com/go-martini/martini
```
## 启动
```
go run main.go
```

可以使用-p参数设置端口. 默认为`8080`.

浏览器访问`http://localhost:8080/hello/cloudgo`, 其中cloudgo可随意更改.

网站显示文本`Hello cloudgo`.
## 使用 curl 工具访问 web 程序
```
[yaroglek@centos-new cloudgo]$ curl -v http://localhost:8080/hello/cloudgo
* About to connect() to localhost port 8080 (#0)
*   Trying ::1...
* Connected to localhost (::1) port 8080 (#0)
> GET /hello/cloudgo HTTP/1.1
> User-Agent: curl/7.29.0
> Host: localhost:8080
> Accept: */*
> 
< HTTP/1.1 200 OK
< Date: Thu, 15 Nov 2018 06:26:00 GMT
< Content-Length: 13
< Content-Type: text/plain; charset=utf-8
< 
* Connection #0 to host localhost left intact
Hello cloudgo
```
## 对 web 执行压力测试
```
[yaroglek@centos-new cloudgo]$ ab -n 1000 -c 100 http://localhost:8080/hello/re8080/hello/cloudgo
This is ApacheBench, Version 2.3 <$Revision: 1430300 $>
Copyright 1996 Adam Twiss, Zeus Technology Ltd, http://www.zeustech.net/
Licensed to The Apache Software Foundation, http://www.apache.org/

Benchmarking localhost (be patient)
Completed 100 requests
Completed 200 requests
Completed 300 requests
Completed 400 requests
Completed 500 requests
Completed 600 requests
Completed 700 requests
Completed 800 requests
Completed 900 requests
Completed 1000 requests
Finished 1000 requests


Server Software:        
Server Hostname:        localhost
Server Port:            8080

Document Path:          /hello/re8080/hello/cloudgo
Document Length:        19 bytes

Concurrency Level:      100
Time taken for tests:   4.747 seconds
Complete requests:      1000
Failed requests:        0
Write errors:           0
Non-2xx responses:      1000
Total transferred:      176000 bytes
HTML transferred:       19000 bytes
Requests per second:    210.67 [#/sec] (mean)
Time per request:       474.665 [ms] (mean)
Time per request:       4.747 [ms] (mean, across all concurrent requests)
Transfer rate:          36.21 [Kbytes/sec] received

Connection Times (ms)
              min  mean[+/-sd] median   max
Connect:        0    2   1.9      1      11
Processing:     3  453 454.0    423    2064
Waiting:        1  452 454.1    423    2061
Total:          3  455 453.4    424    2064

Percentage of the requests served within a certain time (ms)
  50%    424
  66%    462
  75%    471
  80%    476
  90%   1332
  95%   1351
  98%   2047
  99%   2047
 100%   2064 (longest request)
```