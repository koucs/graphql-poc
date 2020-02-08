# Outline

This is a example of grapql-java application

Author refers [Getting started with GraphQL Java and Spring Boot](https://www.graphql-java.com/tutorials/getting-started-with-spring-boot/#graphql-java-overview) page's example.   

## To run

```shell script
➜ gradle bootRun

> Task :bootRun

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.2.0.RELEASE)

2020-02-08 20:10:51.950  INFO 17023 --- [           main] c.g.tutorial.bookdetails.Application     : Starting Application on AcToMiNi-no-Mac-mini.local with PID 17023 (/Users/acto_mini/dev/15_benkyo/graphql-poc/build/classes/java/main started by acto_mini in /Users/acto_mini/dev/15_benkyo/graphql-poc)
2020-02-08 20:10:51.953  INFO 17023 --- [           main] c.g.tutorial.bookdetails.Application     : No active profile set, falling back to default profiles: default
2020-02-08 20:10:52.900  INFO 17023 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2020-02-08 20:10:52.912  INFO 17023 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2020-02-08 20:10:52.912  INFO 17023 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.27]
2020-02-08 20:10:52.985  INFO 17023 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2020-02-08 20:10:52.985  INFO 17023 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 990 ms
2020-02-08 20:10:53.344  INFO 17023 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2020-02-08 20:10:53.508  INFO 17023 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2020-02-08 20:10:53.512  INFO 17023 --- [           main] c.g.tutorial.bookdetails.Application     : Started Application in 2.064 seconds (JVM running for 2.479)
<=========----> 75% EXECUTING [11s]
> :bootRun
```

2. call Web API
```shell script
➜ curl 'http://localhost:8080/graphql' -H 'Accept-Encoding: gzip, deflate, br' -H 'Content-Type: application/json' -H 'Accept: application/json' -H 'Connection: keep-alive' -H 'DNT: 1' -H 'Origin: file://' --data-binary '{"query":"{\n  bookById(id: \"book-2\"){\n    id\n    name\n    author {\n      lastName\n      firstName\n    }\n  }\n}"}' --compressed | jq .

{
  "data": {
    "bookById": {
      "id": "book-2",
      "name": "Moby Dick",
      "author": {
        "lastName": "Melville",
        "firstName": "Herman"
      }
    }
  }
}
```
## GUI tools

The easiest way to try out and explore a GraphQL API is to use a tool like [GraphQL Playground](https://github.com/prisma-labs/graphql-playground).

## References

- [Creating a RESTful Web Service with Spring Boot](https://kotlinlang.org/docs/tutorials/spring-boot-restful.html)