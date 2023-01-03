
Une norme de Java pour développer le web dynamique
C'est une interface


# 生命周期

## 加载与实例化

1. 默认第一次被访问时，由容器创建

```java
// loadOnStartup小于0，第一次被访问时创建，大于等于0，服务器启动时创建，数字越小优先级越高
@WebServlet(urlPatterns = "/demo", loadOnStartup = 1)
```

2. 初始化

容器将调用```init()```方法，只执行一次

3. 请求处理

容器将调用```service()```方法

4. 终止服务

释放内存或关闭容器时，容器将调用```destroy()```方法

## 体系结构

Servlet --> GenericServlet --> HttpServlet

### HttpServlet

```java
doGet()
doPost()
```


## XML配置方式与注解配置方式

### urlPatterns

匹配格式

## request

1. 获取请求行，请求头，请求体信息
2. 乱码问题
3. 转发

## response

1. 设置响应行，响应头，相应体
2. redirect

