**@Component:** This annotation use on class for mentioned as a spring components. @component annotation on class marked as a bean or component for component-scan and add to the application context. It is generic stereotype.

**@Bean: **

[Spring all Annotations](https://springframework.guru/spring-framework-annotations/)

https://dzone.com/articles/cglib-missing-manual

https://stackoverflow.com/questions/10604298/spring-component-versus-bean

https://dzone.com/articles/cglib-missing-manual

https://dzone.com/articles/spring-component-scan

https://dzone.com/refcardz/spring-configuration?chapter=1


**Difference between @Component and @Configure with bean**

When the class containing @Configuration or @Component contains @Bean annotated methods, those methods act as factory beans. The difference lies in the inter-bean references when one @Bean method invokes another @Bean method. If the class is annotated with @Component the @Bean method invocation is treated as a standard Java method invocation whereas when a @Bean method declared in @Configuration is called the method invocation is intercepted using CGLIB proxy and the bean cached in the spring container is returned.

https://dzone.com/articles/creating-a-rest-api-with-java-and-spring


https://spring.io/blog/2013/11/01/exception-handling-in-spring-mvc
