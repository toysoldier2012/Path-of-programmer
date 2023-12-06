加入 LCL 的 DSI（信息系统部）ACE 部落（保险、账户、储蓄）的“保险”小队的职位描述。

# 关于项目

Je vais intégrer dans la Squad "Assurance”, qui est rattaché à la tribu ACE (Assurances, Comptes, Epargne ) de la DSI LCL

Assurer et améliorer la disponibilité des outils d’assurances dans un contexte essentiellement Producteurs /Distributeurs

问题，项目是做什么的，这个描述太笼统了

# 关于技术

1. 精通 Java/JEE 后端开发和 Spring/SpringBoot JEE 框架（包括 Servlet/JSP）。
2. 掌握标准网络技术和模式，如HTTP, REST, OAuth2, OpenID Connect, 微服务, 容器等。
3. 了解容器化/编排解决方案：Docker/Kubernetes。
4. 对计算机项目周边的技术生态系统感兴趣或精通，如应用安全、开发规范、代码质量和性能、持续集成、代码配置管理、容器化等。

architecture front-end/back-end séparée

### Servlet

1. **定义和用途**：
    
    - Servlet是一种运行在服务器上的Java程序，用于扩展服务器的功能。它主要用于处理来自Web客户端（如浏览器）的请求并生成响应。
    - Servlet工作在请求-响应编程模型上。当一个Web应用接收到一个客户端请求时，Servlet对这个请求进行处理，然后生成并返回一个响应。
2. **工作原理**：
    
    - Servlet由Web容器（如Apache Tomcat）托管和执行。
    - 当客户端发送HTTP请求到服务器时，容器决定哪个Servlet处理这个请求，然后调用该Servlet的`service`方法。
    - Servlet生成响应（通常是HTML或JSON），容器将此响应发送回客户端。
3. **特点**：
    
    - 强大的处理能力：可以处理复杂的逻辑。
    - 管理生命周期：容器管理Servlet的生命周期，包括初始化、处理请求和销毁。
    - 多线程：Servlet处理请求时是多线程的，允许同时处理多个请求。

### JSP (JavaServer Pages)

1. **定义和用途**：
    
    - JSP是一种用于创建动态内容的Web页面的技术。它允许在HTML中嵌入Java代码片段。
    - JSP被用来轻松地创建响应用户请求的动态Web页面，通常用于呈现数据。
2. **工作原理**：
    
    - 当一个JSP页面被请求时，它首先被转换成一个Servlet，然后和普通的Servlet一样被Web容器处理。
    - JSP页面中的Java代码在服务器端执行，生成的内容（通常是HTML）随着响应发送到客户端。
3. **特点**：
    
    - 易于学习和使用：对于熟悉HTML和基本Java知识的开发者来说，JSP是一个易于上手的选择。
    - JSP 标签库（JSTL _JSP_ Standard Tag Library）：提供了一组自定义标签，使得在 JSP 页面中实现复杂的功能变得更简单。
    - 结合了 HTML 和 Java：允许在 HTML 中直接嵌入 Java 代码。

### OpenID Connect（OIDC ）

OpenID Connect（OIDC）是一种基于 OAuth 2.0协议的身份认证标准。它使得客户端应用能够验证用户的身份，通常是通过认证服务器，以便为用户提供安全的登录体验。这一过程常用于单点登录（SSO）系统。OpenID Connect 建立在 OAuth 2.0之上，添加了身份验证和会话管理的特性。下面是关于 OpenID Connect 的一些关键点：

### 关键特性

1. **身份验证**：OpenID Connect允许客户端验证用户的身份，这是通过OAuth 2.0授权服务器完成的。
2. **ID Token**：它引入了一个新的令牌类型，称为ID Token，它是一个JSON Web Token（JWT），包含了用户身份的信息。
3. **标准化流程**：提供了一系列标准化的流程来管理身份验证和令牌的获取。

### 工作原理

1. **用户身份验证**：用户首先登录到身份提供者（如Google、Facebook等）。
2. **授权请求**：客户端应用发送一个授权请求到身份提供者。
3. **ID Token 和 Access Token**：成功验证后，用户被重定向回客户端应用，应用接收到ID Token（包含用户信息）和Access Token（用于访问资源）。
4. **用户信息**：客户端应用可以使用ID Token中的信息来识别用户，同时也可以使用Access Token来访问用户在资源服务器上的资源。

### 使用场景

- **单点登录（SSO）**：在多个应用或服务之间提供无缝的用户体验。
- **移动和Web应用认证**：在移动设备和Web应用中安全地管理用户会话和身份信息。
- **身份验证委托**：允许第三方应用通过受信任的身份提供者验证用户身份。