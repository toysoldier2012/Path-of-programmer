#lambda 

- 简化函数接口
- (parameters) -> expression 
或 (parameters) -> { statements; }

- 最多只能有两个参数

- 省略规则

	- 参数

		- 可以省略参数类型
		- 如果只有一个参数，可以同时省略参数类型和小括号

	- 方法体

		- 如果只有一条语句，可以省略大括号
		- 如果只有一条return语句，可以省略return和大括号

	- 通过::继续简化

		- 静态方法引用（static method）语法：classname::methodname 例如：Person::getAge
		- 对象的实例方法引用语法：instancename::methodname 例如：System.out::println
		- 对象的超类方法引用语法： super::methodname
		- 类构造器引用语法： classname::new 例如：ArrayList::new
		- 数组构造器引用语法： typename[]::new 例如： String[]:new