#pattern
## Adapter
#adapter

## Bridge
#bridge

## Composant
#composant

## Decoration
#decoration

## 代理模式 Proxy
#proxy 

1. 创建一个 ProxyInstance

```java
Proxy.newProxyInstance(
	sub.getClass().getClassLoader(), 
	sub.getClass().getInterfaces(),  
    invocationHandler
);
```

其中 sub 是需要被代理的对象

2. 创建 InvocationHandler

```java
public class DynamicProxy implements InvocationHandler {  
    private final Subject subject;  
  
    public DynamicProxy(Subject subject) {  
       this.subject = subject;  
    }  
  
    @Override  
    public Object invoke(Object proxy, Method method, Object[] args) throws Throwable {  
       System.out.println("Before.........");  
       Object sub = method.invoke(subject, args);  
       System.out.println("After..........");  
       return sub;  
    }  
}
```

其中 proxy 是需要被代理的实例，method 是方法，args 是方法参数
在 invoke 中实现需要完成的代理操作

## Facade

