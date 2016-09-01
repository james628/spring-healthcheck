# spring-boot-healthcheck
 Generate REST API "/healthcheck" in your spring boot web project.
 
 "/healthcheck" provide many things.

1. Server status
2. Database status
3. Redis status
4. Current application version

EX)

	REQUEST (GET) - http://yourdomain.com/healthcheck
	
	RESPONSE - Content-Type: application/json
	```
		{
			"return_message":"success",
			"context":{
				"db_response_time":2,
				"redis_response_time":1
			},
			"return_code":0,
			"version":"1.10",
			"timestamp":1472708562590
		}
	```


# Quick start
1. import library (prepare for gradle, maven, etc..)

2. Create your **healthCheckClass** java file with implements HealthCheckInterface
	ex) HealthCheckClass.java
	```
	public class HealthCheckClass implements HealthCheckInterface {
		@Override
		...
	}
	```

3. Add **healthCheckClassFullName** into your properties
healthCheckClassFullName=com.studio4365.spring.healthcheck.HealthCheckClass

4. Add basePackage **"com.studio4365.spring"** in your setting in Component-scan
	* Annotation driven
	```
	@ComponentScan(basePackages="com.yourdomain, `**`com.studio4365.spring`**`")
	```
	* XML
	```
	<context:component-scan base-package="com.yourdomain, `**`com.studio4365.spring`**`" />
	```
