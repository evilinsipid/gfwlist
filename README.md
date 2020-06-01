##### === 通配符支持 => `*`
###### `*.example.com/` 代表 `http://example.com` `http://233.example.com` `https://233.example.com` `https://666.example.com/233.mp4` 全部走代理。
###### 同时`*`可省略，`.example.com/` 与 `*.example.com/` 效果是一样的
 
 ---
 
##### === 正则表达式支持
###### 以 `\` 开始和结束，`\[\w]+:\/\/example.com\`
 
 ---
 
##### === 例外规则 => `@@`
###### `@@*.example.com/` 表示`@@`后面的网址规则`(*.example.com)`不走代理
###### 如：`@@www.baidu.com` 表示 `www.baidu.com` 不走代理
 
 ---
 
##### === 匹配地址开始和结尾规则 => `|`
###### `|http://example.com`、`example.com|` 分别表示 以`http://example.com`开始 和 以`example.com`结束 的地址
###### 如：`|http://233.com` ，代表 `http://233.com` 开头的网址才会走代理，即 `https://233.com` `http://1.233.com` 都不会走代理
###### 如：`233.com|`，代表 `233.com` 结尾的网站才会走代理，即 `http://233.com` `https://233.com` `http://1.233.com` 都会走带了，而 `http://233.com/index.html` 不会走代理。
  
 ---
 
##### === 全匹配规则 => `||`
###### `||example.com` 则代表 `http://example.com`、`https://example.com`、`ftp://example.com` 等协议的地址全部走代理
###### 如：`||233.com` ，即 `http://233.com`、`https://233.com`、`ftp://233.com` 等地址全都走代理
  
 ---
 
##### === 注释规则 => `!`
###### !我是注释233
###### !我也是注释666

---

##### === 分隔符 => `^`
###### 表示除了字母、数字或者 `_ - . %` 之外的任何字符。如 `http://example.com^` ，`http://example.com/` 和 `http://example.com:8000/` 均满足条件，而 `http://example.com.ar/` 不满足条件。
