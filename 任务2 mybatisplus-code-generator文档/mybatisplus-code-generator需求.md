# mybatisplus code generator

## 需求

xml文件：自定义写sql
kt文件：
1、@TableName
class TestEntity

2、TestDao: baseMapper

3、实现类和接口类 Repository, ServiceImpl<TestDao, TestEntity>()

## 当前要做

确定代码生成流程，确认选型方案，大概的编码流程，跑个demo。

构建项目，学习Java swing

去除字段前缀，删除多余代码。

加一个重置系统的功能。

## 需要有的窗口

Main主界面;TableColumnDialog双击数据库中的表；GlobalConfigDialog全局配置的界面；DataSourceDialog添加数据源的界面;类型映射的界面。

需要输出过程中的设计和所遇问题。

## 难题

* 主要看了一下自动生成代码的流程，还有需要生成的文件。现在在想先写配置类，在考虑配置类需要定义什么内容还有配置怎么获取。
* 用什么来开发界面 Java swing还是GUI
* GUI Form开发时跳转界面必须调用main方法，导致界面为空，组件全部消失的问题，没有找到很好的解决方案。
* 怎么保持数据库一直连接，不需要每次打开首界面都需要重新连接。
* gradle项目要引用maven项目作为依赖，没有办法直接通过配置实现，也没有办法直接通过模块依赖来实现，gradle.kts的语法。

## Bug

* 配置保存时显示请输入自定义的Entity超类。
* 不同版本的idea同时安装此插件，会出错。



## 流程

Config->



## 需求对应项目中的文件为:large_blue_circle:

1、@TableName
class TestEntity 

对应的是entity包下的GameSchool。

2.TestDao: baseMapper

对应的是mapper包下的GameSchoolMapper:BaseMapper<GameSchool>。

对应的xml文件是在resources.mapper下的GameSchoolMapper

3、实现类和接口类 Repository, ServiceImpl<TestDao, TestEntity>()

实现类Repository对应的是application.repository下的GameSchoolRepository。

在mybatisplus code generator 对应service

**即repository对应service**

接口类ServiceImpl<TestDao, TestEntity>()对应的是Impl包下的GameSchoolRepositoryImpl:ServiceImpl<GameSchoolMapper,GameSchool>(),GameSchoolRepository。

在mybatisplus code generator 对应serviceImpl

**即repositoryImpl对应serviceImpl**



## 需要使用到的:radio:

最新可以生产
<!--逆向工程-->
        <dependency>
            <groupId>com.baomidou</groupId>
            <artifactId>mybatis-plus-generator</artifactId>
            <version>3.5.1</version>
        </dependency>
        <!--逆向工程需要模板引擎-->
        <dependency>
            <groupId>org.freemarker</groupId>
            <artifactId>freemarker</artifactId>
            <version>2.3.28</version>
        </dependency>



https://mvnrepository.com/artifact/com.baomidou/mybatis-plus-generator
https://mvnrepository.com/artifact/com.github.davidfantasy/mybatis-plus-generator-ui



## 优化:rainbow:

* 包名的修改。
* kotlin 默认值的优化，各个字段对应的默认值，注解的优化
* 打开表的显示字段，自定义和全局的优先顺序
* 包名的修改
* mapper的路径
