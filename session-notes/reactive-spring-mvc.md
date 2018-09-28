# Reactive in Spring MVC

Tues 11AM

https://springoneplatform.io/2018/sessions/guide-to-reactive-for-spring-mvc-developers
https://github.com/rstoyanchev/reactive-for-webmvc
https://www.infoq.com/articles/Servlet-and-Reactive-Stacks-Spring-Framework-5

Related talk: Reactive for Relational Database Connectivity, Wed 12:10PM

## History

- Blocking I/O contracts
- Add Async request processing allows decoupling of request and servlet container thread

### RestTemplate

- Synchronous
- no streaming (well byte streaming only)

```java
RestTemplate$.setUriTemplateHandler() //  set a base url
RestTemplate$.getForObject("/<request-path>") // appends to baseUrl
```

## Reactive Present / Future

- Java 8 supports async concepts natively

## Spring WebFlux

### WebClient

- WebClient in SF 5.0
- Fluent API (replace excessive method overloads)
- Reactive, declarative, streaming

mono = single response
flux = multi response

```java
WebClient.create(<baseUrl>)

client.get().uri(<request-path>).retrieve().bodyToMono(Clazz)
// immediately returns
// collect mono promises
Mono.when(monos).block()
```
