#springmvc

# Conception

## Process

AbstractAnnotationConfigDispatcherServletInitializer

![[Pasted image 20231126130659.png]]


```java
public class MainInitializer extends abstractAnnotationConfigDispatcherServletInitializer { 
	@Override 
	protected Class<?>[] getRootConfigClasses() {
		return new Class[]{WebConfiguration.class}; //基本的Spring配置类，一般用于业务层配置 
	} 
	@Override 
	protected Class<?>[] getServletConfigClasses() { 
		return new Class[0]; //配置DispatcherServlet的配置类、主要用于Controller等配置，这里为了教学简单，就不分这么详细了，只使用上面的基本配置类 
	} 
	@Override 
	protected String[] getServletMappings() { 
		return new String[]{"/"}; //匹配路径，与上面一致 
	} 
}
```

```java
@Configuration 
@EnableWebMvc //快速配置SpringMvc注解，如果不添加此注解会导致后续无法通过实现WebMvcConfigurer接口进行自定义配置 
@ComponentScan("com.example.controller") 
public class WebConfiguration implements WebMvcConfigurer {

}
```

## Interceptor

![[Pasted image 20231126132324.png]]

```java
public class MainInterceptor implements HandlerInterceptor { 
	@Override 
	public boolean preHandle(
		HttpServletRequest request, 
		HttpServletResponse response, 
		Object handler
	) throws Exception { 
		System.out.println("我是处理之前！"); 
		return true; //只有返回true才会继续，否则直接结束 
	} 
	@Override 
	public void postHandle(
		HttpServletRequest request, 
		HttpServletResponse response, 
		Object handler, 
		ModelAndView modelAndView
	) throws Exception { 
		System.out.println("我是处理之后！"); 
	} 
	@Override 
	public void afterCompletion(
		HttpServletRequest request, 
		HttpServletResponse response, 
		Object handler, 
		Exception ex
	) throws Exception { 
		//在DispatcherServlet完全处理完请求后被调用 
		System.out.println("我是完成之后！"); 
	} 
}
```

Ajouter dans `WebConfiguration`

```java
@Override 
public void addInterceptors(InterceptorRegistry registry) {
	registry.addInterceptor(new MainInterceptor()).addPathPatterns("/**") 
	//添加拦截器的匹配路径，只要匹配一律拦截 
	.excludePathPatterns("/home"); 
	//拦截器不进行拦截的路径 
}
```

## Json

如果 controller 直接返回了一个对象，那么需要配置 WebConfiguration 文件

```java
@Override 
public void configureMessageConverters(
	List<HttpMessageConverter<?>> converters
) { 
	converters.add(new FastJsonHttpMessageConverter()); 
}
```

# Scope of Bean

- request
- session
- global-session

# Annotation

@EnableWebMvc
@Controller
@RestController

@RequestMapping
- value
- params
- headers
- produces
@GetMapping
@PutMapping
@DeleteMapping
@PostMapping

@RequestParam
- value
- required
- defaultValue

> [!info] 
>  对于部分类，不需要添加注解，例如 `HttpServletRequest`，`HttpServletResponse`，`HttpSession`，或者其他同名实体类

@RequestHeader
@RequestBody
@PathVariable

@CookieValue
- value
- required
@SessionAttrbutie

@RequestScope
@SessionScope

@ResponseBody