根据nacos提供的初始化sql,导入sql,会生成几个表,其中users是用户表
添加数据库连接：nacos-server-1.2.1\nacos\conf\application.properties

spring.datasource.platform=mysql
db.num=1
db.url.0=jdbc:mysql://11.162.196.16:3306/nacos_devtest?characterEncoding=utf8&connectTimeout=1000&socketTimeout=3000&autoReconnect=true
db.user=nacos_devtest
db.password=youdontknow


引入依赖

<dependency>
       <groupId>org.springframework.boot</groupId>
       <artifactId>spring-boot-starter-security</artifactId>
</dependency>


运行main方法：


package com.alibaba.nacos.console.utils;

import org.springframework.security.crypto.bcrypt.BCryptPasswordEncoder;

/**
 * Password encoder tool
 *
 * @author nacos
 */
public class PasswordEncoderUtil {

    public static void main(String[] args) {
        System.out.println(new BCryptPasswordEncoder().encode("nacos"));
    }
}