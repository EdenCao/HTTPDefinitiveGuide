# URL 与资源

## URL 的语法

\<schema\>://\<user\>:\<password\>@\<host\>:\<port\>/\<path\>;\<params\>?\<query\>#\<flag\>

- schema: 使用哪种协议，大小写无关
- user: 用户名
- password：密码
- host：主机名或服务地址
- port： 端口号
- path：服务器上资源的本地名，说明了资源位于服务器的什么地方。
- params：参数为名=值对 type=d;sale=false;
- query：查询
- frag：片段，引用对象时，不会将 frag 字段传送给服务器；这个字段是在客户端内部使用的。

## URL 快捷方式

相对 URL = 基础 URL + 相对 URL

### 自动扩展 URL

- 主机名扩展
- 历史扩展

## 字符

### URL 字符集

UL-ASCII + 转义序列

### 编码机制

% + 两位十六进制 ASCII（4 字节）
