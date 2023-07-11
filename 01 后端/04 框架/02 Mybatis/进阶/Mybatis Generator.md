
是Mybatis中的一个插件， 用于读取数据库内容，生成pojo，mapper，mapper.xml等
实现多快好省的操作数据库
只能实现单表操作

# 向pom文件中添加generator插件

``` xml
<build>  
    <plugins>        
	    <plugin>            
			<groupId>org.mybatis.generator</groupId>  
	        <artifactId>mybatis-generator-maven-plugin</artifactId>  
	        <version>1.3.0</version> 
            
            <dependencies>                
	            <dependency>                    
		            <groupId>org.mybatis.generator</groupId>  
                    <artifactId>mybatis-generator-core</artifactId>  
                    <version>1.3.2</version>  
                </dependency>                
                <dependency>                    
	                <groupId>mysql</groupId>  
                    <artifactId>mysql-connector-java</artifactId>  
                    <version>8.0.31</version>  
                </dependency>            
            </dependencies>        
        </plugin>    
    </plugins>
</build>
```

# 创建配置文件

``` xml
<?xml version="1.0" encoding="UTF-8"?>  
<!DOCTYPE generatorConfiguration  
        PUBLIC "-//mybatis.org//DTD MyBatis Generator Configuration 1.0//EN"  
        "http://mybatis.org/dtd/mybatis-generator-config_1_0.dtd">  
        
<generatorConfiguration>  
  	<!-- 暂时还没用上的属性-->
    <!-- 数据库驱动:选择你的本地硬盘上面的数据库驱动包 -->  
    <!--<classPathEntry  location="D:\maven-warehouse\repository\mysql\mysql-connector-java\5.1.47\mysql-connector-java-5.1.47.jar"/>-->    
    <!-- <classPathEntry  location="D:\maven-warehouse\repository\mysql\mysql-connector-java\8.0.17\mysql-connector-java-8.0.17.jar"/> -->
    
    <context id="DB2Tables"  targetRuntime="MyBatis3">  
  
        <!-- 数据库连接驱动类,URL，用户名、密码 -->  
        <jdbcConnection 
	        driverClass="com.mysql.cj.jdbc.Driver"  
            connectionURL="jdbc:mysql://localhost:3306/sakila?serverTimezone=UTC"  
            userId="root"  
            password="evvf8YXEEB">  
        </jdbcConnection>  

		<!-- 生成Domain模型：包名(targetPackage)、位置(targetProject) -->  
        <javaModelGenerator 
	        targetPackage="com.xiaoyu.mbg.pojo"
	        targetProject="./src/main/java">  
            <!-- 在targetPackage的基础上，
            根据数据库的schema再生成一层package，
            最终生成的类放在这个package下，默认为false -->  
            <property name="enableSubPackages" value="true"/>  
            <!-- 设置是否在getter方法中，对String类型字段调用trim()方法-->  
            <property name="trimStrings" value="true"/>  
        </javaModelGenerator>  
        
        <!-- 生成xml映射文件：包名(targetPackage)、位置(targetProject) -->  
        <sqlMapGenerator 
	        targetPackage="com.xiaoyu.mbg.mapper" 
	        targetProject="./src/main/resources">  
            <property name="enableSubPackages" value="true"/>  
        </sqlMapGenerator>  
        
        <!-- 生成DAO接口：包名(targetPackage)、位置(targetProject) -->  
        <javaClientGenerator type="XMLMAPPER" 
	        targetPackage="com.xiaoyu.mbg.mapper" 
	        targetProject="./src/main/java">  
            <property name="enableSubPackages" value="true"/>  
        </javaClientGenerator>  
        <!-- 要生成的表：tableName - 数据库中的表名或视图名，domainObjectName - 实体类名 -->  
        <table tableName="actor" domainObjectName="Actor"  
                enableCountByExample="false"  
                enableUpdateByExample="false"  
                enableDeleteByExample="false"  
                enableSelectByExample="false"  
                selectByExampleQueryId="false"  
        />  

		<!-- 暂时还没用上的属性-->

		<!-- 实体类生成序列化属性-->  
		<plugin type="org.mybatis.generator.plugins.SerializablePlugin" />  
		<!-- 实体类重写HashCode()和equals()-->  
		<plugin type="org.mybatis.generator.plugins.EqualsHashCodePlugin" />  
		<!-- 实体类重写toString() -->  
		<plugin type="org.mybatis.generator.plugins.ToStringPlugin" />  
		  
		<commentGenerator>  
		    <!-- 是否去除自动生成的注释 -->  
		    <property name="suppressAllComments" value="true"/>  
		    <!-- 生成注释是否带时间戳-->  
		    <property name="suppressDate" value="true"/>  
		    <!-- 生成的Java文件的编码格式 -->  
		    <property name="javaFileEncoding" value="utf-8"/>  
		    <!-- 格式化java代码-->  
		    <property 
			    name="javaFormatter" 
			    value="org.mybatis.generator.api.dom.DefaultJavaFormatter" />  
		    <!-- 格式化XML代码-->  
		    <property 
				name="xmlFormatter"
				value="org.mybatis.generator.api.dom.DefaultXmlFormatter" />  
		</commentGenerator>  
		  
		<!-- java类型处理器：处理DB中的类型到Java中的类型 -->  
		<javaTypeResolver type="org.mybatis.generator.internal.types.JavaTypeResolverDefaultImpl">  
		    <!-- 是否有效识别DB中的BigDecimal类型 -->  
		    <property name="forceBigDecimals" value="true"/>  
		</javaTypeResolver>
  
    </context>  
</generatorConfiguration>
```

# Magic！

![[Pasted image 20230306232237.png]]