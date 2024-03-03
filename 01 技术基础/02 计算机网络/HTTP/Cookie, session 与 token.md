# Cookie
#cookie

浏览器首次发送请求之后，服务器设置 Cookie (Set-Cookie)，将 Cookie 发送给浏览器保存，之后每次浏览器发送请求都会发送 Cookie，不安全

# Session
#session

包含 `SessionId` 与会话时间 (Max-age) 等信息，首次浏览器发送请求时，服务器 Set-Cookie，将 Cookie 发送给浏览器保存，随后浏览器与服务器通过 `SessionId` 交流

相对安全

# Token
#token

基本原理与 Cookie/Session 一致，但具体包含三部分，`header`.`payload`.`signature`，`header` 包含算法，`payload` 包含基本信息，二者通过 Base 64 编码，上传至服务器，得出第三段内容 `signature`，保存在服务器