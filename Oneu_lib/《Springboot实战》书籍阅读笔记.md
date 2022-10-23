# SpringBoot

## 一，初始化的SpringBoot

### 1.SpringBoot精 要

1.自动配置

2.起步依赖

3.命令行界面

4.Actuator

### 2.SpringBoot

简而言之，从本质上来说Spring boot 就是Spring，它做了那些没有它你自己也会去做的spring Bean配置，让你不用再写这样的样板配置，可以专注于应用程序的逻辑

### 3.刚初始化的SpringBoot项目

XXXApplication.java不仅仅是启动引导类，更是配置类

在XXXApplication.java中`@SpringBootApplication`开启了Spring的组件扫描 和 SpringBoot的自动配置功能；实际上`@SpringBootApplication`将三个有用的注解组合起来了：（早期版本的Springboot是下面三个注解同时标在XXXApplication.java上的，从SpringBoot1.2.0开始，有@SpringBootApplication就行了）

​		·Spring的@Configuration

​		·Spring的@ComponentScan

​		·SpringBoot的@EnableAutoConfiguration

### 4.SpringBoot自带测试类的骨架

```java
@RunWith(SpringJUnit4ClassRunner.class)
@SpringApplicationConfiguration(classes = XXXApplication.class)//通过SpringBoot加载上下文
@WebAppConfiguration
public class XXXApplicationTests{
    
    @Test
    public void contextLoads(){//测试加载的上下文
    }
}
```

contextLoads()方法是自带的一个简单的测试方法，用来证明程序上下文加载没有问题。

### 5.配置应用程序属性

​	它为你生产application.properties文件（空文件时删除不会影响程序），该文件帮助你更细粒度的调整SpringBoot程序的自动配置eg`server.port=8000`这样嵌入式Tomcat的监听端口就变成了8000，而不是默认的8080

### 6.构建过程解析

可以通过Gradle或Maven来构建应用程序，使用Maven时会生成pom.xml文件，构建插件（pom.xml文件中的<build>标签内）的主要功能是把项目打包成一个可执行的超级JAR（把包括应用程序的依赖打入JAR文件内，并为JAR添加一个描述文件，其中的内容能让你用`java -jar`来运行应用程序）

## 二，自动装配

简而言之，SpringBoot的自动装配是一个运行时（更准确地说，是应用程序启动时）的过程，考虑了众多因素，才决定Spring配置应该用哪个，不该用哪个。每当应用程序启动的时候，SpringBoot的自动配置都要做将近200个以上的决定，涵盖安全，集成，持久化，Web开发等诸多方面。所以有了这些自动配置就是为了尽量不让你自己写配置。

### 专注于应用程序功能

与其浪费时间讨论这些Spring配置，还不如看看如何利用SpringBoot的自动配置，让我们专注于应用程序。

#### 1.定义领域模型

我们应用程序里的核心领域概念是读者阅读列表的书。因此我们需要定义一个实体类来表示这个概念。

```java
//Book类
@Entity
@Date
public class Book{
    @Id
    @GeneratedValue(strategy=GenerationType.AUTO)
    private Long id;
    private String reader;
    private String isbn;
    private String title;
    private String author;
    private String description;
    
}
```

`@Entity`注解表明他是一个JPA实体，id属性加了`@Id`和`@GeneratedValue`注解，说明这个字段是实体的唯一标识，并且这个字段的值是自动生成的。

#### 2.定义仓库接口

#### 3.创建Web界面
