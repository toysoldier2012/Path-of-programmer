#enum 

在 Java 中，enums（枚举）是一种特殊类型的数据类型，用于表示固定数量的常量值。

Enums中的每个元素都是一个常量，通常表示一组相关的常量。例如，您可以使用enums表示星期几、颜色、方向等常量。Enums常常被用于替代常量的使用，它们提供了类型安全性和更好的可读性。

# 创建

1. 在 Java 中定义一个 enum 类型，需要使用 enum 关键字，例如：

``` java
public enum Color {
    RED, GREEN, BLUE;
}
```

2. Enums 还可以包含方法，这些方法可以为每个枚举值提供自定义行为。例如：

``` java
public enum Direction {
    NORTH {
        public String getSymbol() {
            return "^";
        }
    },
    EAST {
        public String getSymbol() {
            return ">";
        }
    },
    SOUTH {
        public String getSymbol() {
            return "v";
        }
    },
    WEST {
        public String getSymbol() {
            return "<";
        }
    };

    public abstract String getSymbol();
}
```

3.  Size 枚举类，它定义了两个字段 width 和 height：

``` java
public enum Size {
    SMALL(100, 200),
    LARGE(200, 400);

    private int width;
    private int height;

    private Size(int width, int height) {
        this.width = width;
        this.height = height;
    }

    public int getWidth() {
        return width;
    }

    public int getHeight() {
        return height;
    }
}
```

- 枚举类作为内部类时，可以用 private 和 static 修饰

# 读取

1. 示例 1 中，Color 是一个枚举类型，它有三个枚举值：RED、GREEN、BLUE。这些枚举值都是 Color 类型的常量，可以在代码中像其他常量一样使用，例如：

```java 
Color c = Color.RED;
```

2. 示例 2 中，可以调用 `Direction.EAST.getSymbol()` 获取值
3. 示例 3 中，可以调用 `Size.SMALL.getHeight()`，修改或者获取值
4. `.values()` 方法返回一个包含所有值的数组
5. `.valueOf()` 获取特定的值，`Size size = Size.valueOf("SMALL");`

# 修改

## 添加新的枚举常量

您可以通过在枚举类中添加新的常量来扩展枚举类。例如，假设我们有一个名为Color的枚举类，它定义了三种颜色：

``` java
public enum Color {
    RED,
    GREEN,
    BLUE,
    YELLOW
}
```


现在，我们想要添加一种新的颜色 YELLOW，只需要在枚举类中添加一个新的常量即可：

``` java
public enum Color {
    RED,
    GREEN,
    BLUE,
    YELLOW
}
```

## 修改枚举类中的其他元素

您可以修改枚举类中的其他元素，例如枚举类中的字段、方法等，以实现“修改”的效果，如：

``` java
public enum Size {
    SMALL(100, 200),
    LARGE(200, 400);

    private int width;
    private int height;

    private Size(int width, int height) {
        this.width = width;
        this.height = height;
    }

	public void setWidth(int width) {  
	   this.width = width;  
	}  
	  
	public void setHeight(int height) {  
	   this.height = height;  
	}

    public int getWidth() {
        return width;
    }

    public int getHeight() {
        return height;
    }
}


class TestSize{  
   public static void main(String[] args) {  
      Size.SMALL.setHeight(50);  
   }  
}
```

