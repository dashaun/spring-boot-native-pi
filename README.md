# Spring Boot + Spring Native

## Raspberry Pi ARM64

Points to an example cloud native buildpack, for ARM64, that was built based on:
https://github.com/dmikusa-pivotal/paketo-arm64

### Background

The docker images were all created using a Raspberry Pi 4.8gb.

The native image that I was able to create works (better than) as expected on a Raspberry Pi Zero 2W.

### Getting Started

- Clone the repo.
- Currently, you need a local GraalVM 22.3 installation to build an image with Maven. This will be solved in the future, see [native-build-tools issue #327](https://github.com/graalvm/native-build-tools/issues/327) for details. If you have sdkman installed run: 
```shell 
sdk install java 22.3.r17.ea-nik
```

### Generate Native ARM64
```shell
./mvnw clean -Pnative,native-arm64 spring-boot:build-image -DskipTests
```

### Generate Native AMD64
```shell
./mvnw clean -Pnative,native-amd64 spring-boot:build-image -DskipTests
```

### Generate image AMD64
```shell
./mvnw clean -Pnative spring-boot:build-image -DskipTests
```

Once complete, you should have a new image "spring-pi:0.0.1-SNAPSHOT" in your local registry.

### If you are running this from behind a company firewall

If you are running this from behind a company firewall, one that will rewrite every request, you'll need to add your company's CA certificate in a PEM format to the folder
_bindings/ca-certificates_ . The certificate will be discovered by the _Paketo CA Certificates Buildpack_ and used accordingly.

### Feedback Welcome!

Dashaun you're awesome!!!! AWESOME!!!