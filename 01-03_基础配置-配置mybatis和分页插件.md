## 1.3 配置mybatis和分页插件

在项目的资源包config中创建添加mybatis-config.xml配置文件：

	<?xml version="1.0" encoding="UTF-8"?>
	<!DOCTYPE configuration PUBLIC "-//mybatis.org//DTD Config 3.0//EN" 
	"http://mybatis.org/dtd/mybatis-3-config.dtd">
	
	<configuration>
	    <settings>
	        <setting name="logImpl" value="STDOUT_LOGGING"/>
	    </settings>
	    <!-- 配置分页插件，如果不设计分页，下面的可以不用写 -->
		<plugins>
			<plugin interceptor="com.github.pagehelper.PageHelper">
			    <!-- 配置数据库方言，选定项目所用的数据库 -->
			    <property name="dialect" value="mysql"/>
			</plugin>
		</plugins>
	</configuration>