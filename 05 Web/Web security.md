# CSRF
#csrf

Cross-Site Request Forgery

防御方式
- 尽量使用 POST
- 验证码
- 验证 Refer，但 Refer 可以通过浏览器修改
- Anti CSRF token

# XSS
#xss

反射型：脚本保存在 url 中，服务器返回 url 时触发
存储型：发帖或者文本框中保存脚本，其他用户访问内容时触发
DOM-Based 型：

设置过滤器：输入/输出过滤器

lucy-xss-filter

# SQL 注入