
# [[Maven]]
#maven

- Maven permet de mieux **structurer** le projet Java dans son life-cycle, **développer, complir, tester, deployer** etc.
- L'ensemble du projet est géré à partir d'un seul fichier : le pom.xml, qui représente **toutes les informations liées au projet** (le nom, l'auteur, la version du projet etc.) et aussi les « **dépendances** » du projet.
- Maven peut aussi télécharger et mettre à jours ces dépendances Jars à partir du son répertoire
# [[Mybatis]]

# [[Spring]]

# Log4j

- 添加依赖到pow.xml

``` xml
<dependency>  
    <groupId>log4j</groupId>  
    <artifactId>log4j</artifactId>  
    <version>1.2.17</version>  
</dependency>
```

- log4j.xml

``` xml
<?xml version="1.0" encoding="UTF-8" ?>  
<!DOCTYPE log4j:configuration SYSTEM "log4j.dtd">  
<log4j:configuration xmlns:log4j="http://jakarta.apache.org/log4j/">  
    <appender name="STDOUT" class="org.apache.log4j.ConsoleAppender">  
        <param name="Encoding" value="UTF-8"/>  
        <layout class="org.apache.log4j.PatternLayout">  
            <param name="ConversionPattern" value="%-5p %d{MM-dd HH:mm:ss,SSS} %m (%F:%L) \n"/>  
        </layout>
    </appender>
    <logger name="java.sql">  
        <level value="debug"/>  
    </logger>
    <logger name="org.apache.ibatis">  
        <level value="info"/>  
    </logger>
	<root>
		<level value="debug"/>  
		<appender-ref ref="STDOUT"/>  
	</root>
</log4j:configuration>

```

FATAL > ERROR > WARN > INFO > DEBUG

# Druid

``` xml
<dependency>  
    <groupId>com.alibaba</groupId>  
    <artifactId>druid</artifactId>  
    <version>1.2.16</version>  
</dependency>
```


# [[Vuejs]]



Thymeleaf

Log