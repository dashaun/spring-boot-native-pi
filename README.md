# Spring Boot + Spring Native

## Raspberry Pi ARM64

Points to an example cloud native buildpack, for ARM64, that was built based on:
https://github.com/dmikusa-pivotal/paketo-arm64

### Background

The docker images were all created using a Raspberry Pi 4.8gb.

The native image that I was able to create works (better than) as expected on a Raspberry Pi Zero 2W.

### Getting Started

Clone the repo then:

```shell
./mvnw spring-boot:build-image -DskipTests
```

### Feedback Welcome!
