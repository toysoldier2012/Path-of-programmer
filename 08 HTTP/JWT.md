#jwt

基本原理与 Cookie/Session 一致，但具体包含三部分，header.payload.signature，header 包含算法，payload 包含基本信息，二者通过 Base 64 编码，上传至服务器，得出第三段内容 signature，保存在服务器