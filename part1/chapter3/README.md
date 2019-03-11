# HTTP 报文

## 报文流
报文的发送方是上游，报文的接收方是下游

## 报文的组成部分
报文包括**起始行**、**首部**、**主体**三部分。

请求报文：
```html
<method> <request-URL> <version>
<headers>

<entity-body>
```

响应报文
```html
<version> <status> <reason-phrase>
<headers>

<entity-body>
```

### 状态码
* 100 ～ 199: 信息提示
* 100 ～ 299：成功
* 300 ～ 399: 资源被转移走
* 400 ～ 499: 客户端请求错误
* 500 ～ 599: 服务端错误

### 首部分类
* 通用首部
既可以出现在请求报文中，也可以出现在响应报文中

* 请求首部
提供更多有关请求的信息

* 响应首部
提供更多有关响应的信息。

* 实体首部
描述主体的长度和内容，或者资源自身

* 扩展首部
规范中没有定义的新首部

## 状态码

### 关于 100 状态码
100 Continue 实际上是一种优化，如果客户端愿意在发送实体之前等待 100 Continue 响应，
就需要在发送的时候发送一个包含 100 Continue 值的 Expect。如果没有实体，就不应该使用
100 Continue。同时也应该做出服务端不会按预期返回 100 Continue 的准备。

## 首部

### Accept 首部
* Accept： 告诉服务器能够发送那些媒体类型
* Accept-Charset： 告诉服务器能够发送哪些字符集
* Accept—Encoding： 告诉服务器能够发送哪些编码方式
* Accept-Language： 告诉服务器能够发送哪些语言
* TE： 告诉服务器可以使用哪些扩展传输编码

### 条件请求首部
* Expect：允许客户端列出某请求所要求的服务器行为
* If-Match：如果实体标记与文档当前的实体标记相匹配，就获取这份文档。
* If-Modified-Since： 除非在某个指定的日期之后资源被修改过，否则就限制这个请求。
* If-None—Match： 如果提供的实体标记与当前文档的实体标记不相符，就获取文档。
* If-Range：允许对文档的某个范围进行条件请求
* If-Unmodified—Since： 除非在某个指定日期之后资源没有被修改过，否则就限制这个请求
* Range：如果服务器支持范围请求，就请求资源的指定范围

### 安全请求首部
* Authorization：包含了客户端提供给服务器，以便对其自身进行认证的数据
* Cookie： 客户端用它向服务器传送一个令牌
* Cookie2: 用来说明请求端支持的 cookie 版本

### 内容首部
* Content-Base: 解析主体中的相对 URL 使使用的基础 URL
* Content-Encoding： 对主体执行的任意编码方式
* Content-Language：理解主体时最适宜使用的自然语言
* Content-Length： 主体的长度或尺寸
* Content-Location：资源实际所处的位置
* Content-MD5: 主体的 MD5 校验值
* Content-Range：在整个资源中此实体表示的字节范围
* Content-Type：这个主体的对象类型

### 实体缓存首部
* ETag： 与此实体相关的实体标记
* Expires： 此实体不再有效，要从原始的源端再次获取此实体的日期和时间
* Last-Modified：这个实体最后一次被修改的日期和时间
