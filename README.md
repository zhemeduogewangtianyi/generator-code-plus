# 基于 mybatis-generator 的代码生成器

##### 扩展生成 Controller 

##### 扩展生成 Service

##### 扩展生成 ServiceImpl

##### 扩展生成 ViewObject

##### 扩展生成 ParamObject



### Tip:

1：作者比较懒，没有去做过多的适配，controller ||  service  || serviceImpl 任意一个无配置，就不生成这仨。

2：param || vo 任意一个不写，默认给DO 在 service || serviceImpl || controller

3：代码会覆盖！代码会覆盖！代码会覆盖！

4：目录不存在会自动创建！自动创建！自动创建



### 使用方法：

```java
public static void main(String[] args) {

        GeneratorContext gc = new GeneratorContext();

        //自定义的 mysql 连接 jar，如果需要特别指定就自己指定
//        gc.setMysqlJarPath("mysql-connector-java-8.0.21.jar");

        //jdbc 连接配置
        gc.setConnectionUrl("jdbc:mysql://192.168.3.10:3306/dddxhh");
        gc.setDriverClass("com.mysql.cj.jdbc.Driver");
        gc.setUsername("dddxhh");
        gc.setPassword("123456");

        //生成注释 - 作者的名字
        gc.setAuthor("DDDXHH");

        //表名称
        gc.setTableName("test");
    	//对应实体的前缀名称 例如：TestController
        gc.setEntityName("Test");

        //实体类生成存放地址
        gc.setDoPackage("com.dddxhh.test.entity");
    
        //dao 接口生成存放地址
    	gc.setDaoPackage("com.dddxhh.test.dao");
    	
    	//dao xml 生成存放地址
        gc.setMapperPackage("mapper");

        // param 存放的地址
        gc.setParamPackage("com.dddxhh.test.entity.param");
    	// vo 存放的地址
        gc.setVoPackage("com.dddxhh.test.entity.vo");
    	//service 接口存放的地址
        gc.setServicePackage("com.dddxhh.test.service");
    	//serviceImpl 实现类存放的地址
        gc.setServiceImplPackage("com.dddxhh.test.service.impl");
    	//controller 存放的地址
        gc.setControllerPackage("com.dddxhh.test.controller");


        //指定主键
        gc.setPrimaryKey("id");

        //生成
        GeneratorUtils.generator(gc);
    }
```

