---
title:  "Sending and receiving messages with Spring Cloud Stream code example"
date:   2020-10-06 06:17:00
summary: Sending and receiving messages with Spring Cloud Stream code example
---

Spring Cloud Stream provides a streaming abstraction over messaging, based on the publish and subscribe integration pattern. Spring Cloud Stream comes with out of the box support for Apache Kafka and RabbitMQ but can be extended to support other messaging brokers using custom binders.

The Message class

```java
public class MyMessage {
    private String attributeFirst = null;
    private String attributeSecond = null;
    ...
```

Spring Cloud Stream comes with default input and output channels, `Sink` and `Source`.

**To publish a message**

```java
import org.springframework.cloud.stream.messaging.Source;

@EnableBinding(Source.class)
public class MyPublisher {

@Autowired private Source source;

public String processMessage(MyMessage message) {
    source.output().send(MessageBuilder.withPayload(message).build());
    ...
```

**To receive messages**

```java
import org.springframework.cloud.stream.messaging.Sink;

@EnableBinding(Sink.class)
public class MySubscriber {

@StreamListener(target = Sink.INPUT)
public void receive(MyMessage message) {
    LOG.info("Received: {}",message);
    ...
```

To bind to RabbitMQ, include in **build.gradle**

```gradle
    implementation('org.springframework.cloud:spring-cloud-starter-streamrabbit')
```

**The configuration for the publisher**

```yaml
spring.cloud.stream:
    default.contentType: application/json
    bindings.output.destination: mydestination
```


**The configuration for the subscriber**

```yaml
spring.cloud.stream:
    default.contentType: application/json
    bindings.input.destination: mydestination
```

---
> We're surrounded by distractions. Whether it's emails, phone calls, text messages, social media notifications, or people entering and leaving your workspace, those distractions end up eating a good portion of your time.
> <small>- [John Rampton](https://www.brainyquote.com/quotes/john_rampton_799434)</small>