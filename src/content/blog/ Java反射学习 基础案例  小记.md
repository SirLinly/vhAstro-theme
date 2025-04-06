---
title:  Java反射学习 基础案例--小记
date: 2021-11-22 20:48:00
updated: 2021-11-22 20:48:15
categories: Java学习笔记
tags:
- Java
- Java笔记
id: 7408
cover: "https://img0.baidu.com/it/u=294544346,1526372923&fm=253&fmt=auto?w=1200&h=800"
---
```java
package cc.bltang.demo01;

import java.io.IOException;
import java.io.InputStream;
import java.lang.reflect.Constructor;
import java.lang.reflect.Method;
import java.util.Properties;

public class ReflectDemo02 {
    public static void main(String[] args) throws  Exception {

        //反射 案例
        Properties pro = new Properties();
        //加载配置文件，转换为一个集合
        //获取Class目录下的配置文件
        ClassLoader classLoader = ReflectDemo02.class.getClassLoader();
        InputStream is = classLoader.getResourceAsStream("pro.properties");
        pro.load(is);
        //获取配置文件中定义的数据
        String className = pro.getProperty("className");
        String methodName = pro.getProperty("methodName");

        //加载类进内存
        Class<?> aClass = Class.forName(className);
        //创建对象
       //  Constructor<?> c = aClass.getConstructor();
      //   Object obj = c.newInstance();
        Object obj = aClass.newInstance();

        //获取方法对象
        Method method = aClass.getMethod(methodName);
        //执行方法
        method.invoke(obj);


    }
}

```