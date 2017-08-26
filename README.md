# yiigo
Golang集成常用类库并封装，用于WEB、API和爬虫开发

## 特点

* 支持多数据库连接
* 支持主从分离
* 支持 `redis`
* 支持 `mongo`
* 支持爬虫模拟登录
* 支持邮件发送
* 支持日志记录
* 采用 `ini` 配置文件

## 获取

```go
go get -u github.com/iiinsomnia/yiigo
```

## 使用

```go
package main

import "github.com/iiinsomnia/yiigo"

func main() {
    //mysql、mongo、redis
    err := yiigo.Bootstrap(true, true, true)

    if err != nil {
        panic(err)
    }
}
```

## 说明
* 在 `main.go` 所在目录创建 `env.ini` ENV配置文件，具体配置可以参考 `env.ini.dev`
* 在 `main.go` 所在目录创建 `log.xml` 日志配置文件，具体配置可以参考 `log.xml.dev` 和 `log.xml.prod`
* 目前数据库仅针对MySQL封装，多数据库连接只需在`ini`文件中配置多个即可
* code.google.com 上 go get 不下来的库，可以在这里[获取](https://github.com/golang)
* 如爬虫不需要模拟登录，则只需要使用 [goquery](https://github.com/PuerkitoBio/goquery) 即可
* 具体使用可以参考 [yiigo-example](https://github.com/IIInsomnia/yiigo-example)