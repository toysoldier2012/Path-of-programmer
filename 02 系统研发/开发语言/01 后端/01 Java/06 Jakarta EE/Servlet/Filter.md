
# Hello Filter

1. 实现Filter接口
2. 配置过滤器

```java
@WebFilter("/*")`
```

3. 重写所有方法， 其中doFilter方法为主要处理方法
4. 通过chain.doFilter放行