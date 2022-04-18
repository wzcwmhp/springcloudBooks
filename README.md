# springcloudBooks
本项目记录了学习springcloud相关书籍代码
##《spring cloud 微服务架构开发实战》
>代码目录01Spring_cloud_microservice_architecture_development_practice
### 第一章 微服务架构开发
### 第二章 微服务基础
#### 2.2 快速启动spring boot
##### 2.2.1 创建一个maven项目。

##### 2.2.2 编写主pom文件：

依赖的父pom,引入后,层层往上spring-boot-dependencies,继承父类的版本定义信息,父项目的pom,pom坐标如下：

    <!--父项目的pom-->
    <parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>1.5.2.RELEASE</version>
    </parent>
定义本服务的groupId和artifactId以及版本号：

	<!--本服务的groupId和artifactId-->
	<groupId>com.wzcwmhp</groupId>
	<artifactId>chapter02</artifactId>
	<version>1.0-SNAPSHOT</version>

定义打包的格式，jar,可取值为jar,war,pom:

	<!--定义打包的格式，jar,知识点-->
	<packaging>jar</packaging>

项目名称

    <!--项目名称-->
    <name>spring boot test</name>

项目中的属性变量信息，例如版本号管理等

    <!--项目中的属性变量信息，例如版本号管理等-->
    <properties>
        <guava-vesion>20.0</guava-vesion>
    </properties>

依赖的库管理

    <!--依赖的库管理-->
    <dependencies>
        <!--spring boot web starter, web工程-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <!--guava提供缓存、集合等工具类-->
        <dependency>
            <groupId>com.google.guava</groupId>
            <artifactId>guava</artifactId>
            <version>${guava-vesion}</version>
        </dependency>
        <!--测试test依赖包-->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-test</artifactId>
            <scope>test</scope>
        </dependency>
    </dependencies>

编译打包相关标签


    <!--编译打包相关标签-->
    <build>
        <plugins>
            <!--编译阶段打包工具-->
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.5.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
            <!--package阶段打包工具，可以打包成jar，直接运行-->
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>

    </build>


##### 2.2.3 编写应用启动类：

	package com.zhichao.wan;
	
	import org.springframework.boot.SpringApplication;
	import org.springframework.boot.autoconfigure.SpringBootApplication;
	@SpringBootApplication
	public class Application {
	    public static void main(String[] args) {
	        SpringApplication.run(Application.class,args);
	    }
	}

##### 2.2.4 编写配置文件：

	#服务端口
	server:
	  port: 8080
	#日志等级
	logging:
	  level:
	    org:
	      springframework: INFO
	    com:
	      chapter02: DEBUG


##### 2.2.5 运行启动类
项目启动成功，运行在8080端口。







