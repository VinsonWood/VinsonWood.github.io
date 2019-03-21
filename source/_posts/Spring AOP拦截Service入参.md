---
title: Spring AOP 拦截Service 入参
date: 2018-12-29 15:54:57
tags:
---

Spring AOP拦截Service中内部相互调用的方法入参时需要注意一下几点：

1.  Service中AOP拦截Service时依赖Bean的代理对象，而不是Bean自身，因此 Service中内部类相互间调用不
   能直接使用xx()或者this.xx()，要注入代理对象到Bean中，然后使用代理对象的方法进行调用
2. 由于Service层在Spring中注册的都是接口类型，所以代理对象只有对依赖接口的实现类方法进行拦截，实现类中新加的方法不能拦截

..

