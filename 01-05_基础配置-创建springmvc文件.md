## 1.5 配置springmvc配置文件

在项目的资源包config中创建添加spring-mvc.xml配置文件：

	<?xml version="1.0" encoding="UTF-8"?>
	<beans xmlns="http://www.springframework.org/schema/beans"
		xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:context="http://www.springframework.org/schema/context"
		xmlns:mvc="http://www.springframework.org/schema/mvc"
		xsi:schemaLocation="http://www.springframework.org/schema/beans 
		http://www.springframework.org/schema/beans/spring-beans.xsd
		http://www.springframework.org/schema/context
		http://www.springframework.org/schema/context/spring-context-4.0.xsd
		http://www.springframework.org/schema/mvc
		http://www.springframework.org/schema/mvc/spring-mvc-4.0.xsd">
		
		<!-- 1.使用注解，扫描项目中的包 -->
		<context:component-scan base-package="com.marshal"></context:component-scan>
		
		<!-- 2.开启注解 -->
		<mvc:annotation-driven/>
		
		<!-- 3.配置例外：不是让所有的代码都走springmvc的过滤器 -->
		<!-- 配置静态资源，不被DispatcherServlet处理 -->
		<mvc:resources location="/images/" mapping="/images/**"/>
		<mvc:resources location="/js/" mapping="/js/**"/>
		<mvc:resources location="/css/" mapping="/css/**"/>
		
		<!-- 4.定义跳转文件的前缀和后缀，视图view的配置 -->
		<bean id="viewResolver" class="org.springframework.web.servlet.view.InternalResourceViewResolver">
			<property name="prefix" value="/WEB-INF/views/"></property>
			<property name="suffix" value=".jsp"></property>
		</bean>
		
	</beans>