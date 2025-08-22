---
title: "Java 17 migration tips/checklist "
date: 2024-04-14T01:11:15+05:30
lastmod: 2024-04-14T21:29:01+08:00
draft: false
author: "Vidhya"
description: "Devcontainer"

tags: ["development","java","spring-boot"]
categories: ["tools"]

resources:
- name: "featured-image"
  src: "java-head.png"

toc:
  auto: true  
---

## Introduction
Navigating the Java 17, Spring 6, and Spring Boot 3 Upgrade Journey can be a challenging yet rewarding endeavor. As you embark on this journey, it's crucial to understand the scope of the upgrade and the key considerations involved in each component's migration. In this article, we'll delve into essential aspects of upgrading, including migrating from Java EE to Jakarta EE in Spring 6, updating Hibernate configurations for Java 17 and Spring 6, upgrading API documentation from Swagger to OpenAPI, transitioning to Apache HttpClient 5, and migrating to Java 17 with Spring Boot 3 using OpenRewrite.

## Migrating from Java EE to Jakarta EE in Spring 6
 
When upgrading to Spring 6 and Spring Boot 3, compatibility with Java EE or Jakarta EE APIs is paramount. This entails updating imports and configurations to align with namespace changes. For instance, understanding the mapping between Java EE and Jakarta EE namespaces is crucial for a seamless migration:

| Java EE Namespace          | Jakarta EE Namespace       |
|----------------------------|----------------------------|
| javax.servlet              | jakarta.servlet            |
| javax.servlet.http         | jakarta.servlet.http       |
| javax.servlet.annotation   | jakarta.servlet.annotation |
| javax.servlet.descriptor   | jakarta.servlet.descriptor |
| javax.servlet.jsp          | jakarta.servlet.jsp        |
| javax.servlet.jsp.el       | jakarta.servlet.jsp.el     |
| javax.servlet.jsp.tagext   | jakarta.servlet.jsp.tagext |
| javax.websocket            | jakarta.websocket          |
| javax.websocket.server     | jakarta.websocket.server   |
| javax.xml.*                | jakarta.xml.*              |
| javax.activation           | jakarta.activation         |
| javax.annotation           | jakarta.annotation         |
| javax.enterprise           | jakarta.enterprise         |
| javax.jms                  | jakarta.jms                |
| javax.jws                  | jakarta.jws                |
| javax.mail                 | jakarta.mail               |
| javax.management           | jakarta.management         |
| javax.persistence          | jakarta.persistence        |
| javax.security.*           | jakarta.security.*         |
| javax.transaction          | jakarta.transaction        |
| javax.validation           | jakarta.validation         |
| javax.websocket            | jakarta.websocket          |
| javax.xml.*                | jakarta.xml.*              |

## Hibernate Update in Java 17 and Spring 6

Upgrading to Java 17 and Spring 6 necessitates considerations for updating Hibernate configurations. Key points to note include updating the Hibernate dialect and annotations for defining custom types. Ensuring compatibility with the latest Hibernate versions and adhering to evolving best practices is essential.

 1. Hibernate Dialect Update:
The `org.hibernate.dialect.MySQLDialect` is supported from Hibernate 5.3 onwards. Prior to Hibernate 5.3, it was recommended to use `org.hibernate.dialect.MySQL57Dialect` for MySQL 5.x and 8.x. However, with the release of Hibernate 5.3, a `org.hibernate.dialect.MySQL8Dialect` was introduced, and it is recommended to use `org.hibernate.dialect.MySQLDialect` since `Hibernate 6`, as `org.hibernate.dialect.MySQL8Dialect` is  deprecated.

 2. Type and TypeDef Annotations Update:
In Hibernate 6, there are changes in the annotations used for defining custom types. For example, the usage of `@TypeDef` and `@Type` annotations has been updated. 
```xml
<dependency>
    <groupId>com.vladmihalcea</groupId>
    <artifactId>hibernate-types-60</artifactId>
    <version><!-- specify version --></version>
</dependency>

```
Instead of:

```java
import org.hibernate.annotations.Type;
import org.hibernate.annotations.TypeDef;

@TypeDef(name = "json", typeClass = StringJsonUserType.class)
public class EntityName {

 @Type(type = "json")
 private propertyName
}
```

You should now use:

```java
import jakarta.persistence.Convert;
import org.hibernate.annotations.JdbcTypeCode;

@Convert(attributeName = "entityAttrName", converter = StringJsonUserType.class)
public class EntityName {

 @JdbcTypeCode(SqlTypes.JSON)
 private propertyName
}

```
## API documentation upgrade swagger to OpenAPI

Migrating from Swagger annotations to OpenAPI annotations involves updating your codebase to use the newer annotations provided by the `springdoc-openapi` library, as well as adjusting any configuration or usage accordingly. Here's a list of some common changes you may need to make:


| Swagger Annotation                         | OpenAPI (springdoc-openapi) Annotation                                    |
|--------------------------------------------|--------------------------------------------------------------------------|
| `io.swagger.annotations.ApiIgnore`          | `org.springdoc.core.annotations.Hidden`                                 |
| `io.swagger.annotations.ApiModelProperty`   | `io.swagger.v3.oas.annotations.media.Schema`                            |
| `io.swagger.annotations.ApiParam`           | `io.swagger.v3.oas.annotations.Parameter`                               |
| `io.swagger.annotations.ApiOperation`       | `io.swagger.v3.oas.annotations.Operation`                               |
| `io.swagger.annotations.ApiResponse`        | `io.swagger.v3.oas.annotations.responses.ApiResponse`                   |
| `io.swagger.annotations.ApiModel`           | `io.swagger.v3.oas.annotations.media.Schema`                            |
| `io.swagger.annotations.ApiImplicitParams`  | `io.swagger.v3.oas.annotations.parameters.Parameters`                   |
| `io.swagger.annotations.ApiResponses`       | `io.swagger.v3.oas.annotations.responses.ApiResponse`                   |

Swagger Annotation: @ApiIgnore
```java
import io.swagger.annotations.Api;
import io.swagger.annotations.ApiIgnore;

@Api(tags = "Sample Controller")
public class SampleController {

    @ApiIgnore
    public void ignoredMethod() {
        // This method will be ignored in Swagger documentation
    }
}
```

OpenAPI (springdoc-openapi) Annotation: @Hidden
```java
import org.springdoc.core.annotations.Hidden;
import io.swagger.v3.oas.annotations.tags.Tag;

@Tag(name = "Sample Controller")
public class SampleController {

    @Hidden
    public void ignoredMethod() {
        // This method will be hidden in OpenAPI documentation
    }
}
```
Swagger Annotation: @ApiModelProperty
```java

import io.swagger.annotations.ApiModelProperty;
import lombok.Data;

@Data
public class SampleModel {

    @ApiModelProperty(value = "The ID of the entity", example = "1")
    private Long id;

    @ApiModelProperty(value = "The name of the entity")
    private String name;
}
```
OpenAPI (springdoc-openapi) Annotation: @Schema
```java

import io.swagger.v3.oas.annotations.media.Schema;
import lombok.Data;

@Data
public class SampleModel {

    @Schema(description = "The ID of the entity", example = "1")
    private Long id;

    @Schema(description = "The name of the entity")
    private String name;
}
```
## Upgrading to Apache HttpClient 5

#### Key Differences:
- `Package Names`: HttpClient 5 uses `org.apache.hc.client5.http` and related packages, whereas HttpClient 4 uses `org.apache.http.`
- `Class Structure`: HttpClient 5 introduces new classes and restructures existing ones for configuration and connection management.
- `SSL Context Handling`: HttpClient 5 provides a different approach for SSL context handling using `SSLConnectionSocketFactoryBuilder`.
- `Connection Pooling Configuration`: Configuration related to connection pooling is done differently in `HttpClient 5` with `PoolingHttpClientConnectionManagerBuilder`.
- `Proxy Configuration`: HttpClient 5 proxy configuration involves changes in how `HttpHost` is used.

{{< gist vidhya03 a41a85bc38e3f295321bde42bb57146b RestTemplateLegacy.java >}}

New updated migrated code 
{{< gist vidhya03 a41a85bc38e3f295321bde42bb57146b RestTemplateHttp5Upgrade.java >}}

#### Additional Notes:
- WebClient: Remember that WebClient is the recommended alternative to RestTemplate for new applications, as it provides both synchronous and asynchronous capabilities.
- RestTemplate: However, if you’re working with existing code, RestTemplate remains a viable choice.

The new webclient will be 

{{< gist vidhya03 5d21de835b5fc3a11d4df9bc2b6f6fcf WebFluxConfig.java >}}


## Migrating to Java 17 with Spring Boot 3 using OpenRewrite
#### Introduction to OpenRewrite

OpenRewrite is a powerful tool for automating code refactoring and transformation tasks in Java projects. It provides a flexible framework for writing custom rules to analyze and modify Java code programmatically. In this section, we'll explore how to integrate OpenRewrite into both Maven and Gradle projects to facilitate the migration from Java 11 to Java 17, along with Spring Boot 3.
```java
// Before OpenRewrite
import javax.servlet.http.HttpServletRequest;
...

```

```java
// After OpenRewrite
import jakarta.servlet.http.HttpServletRequest;
...

```


#### Integrating OpenRewrite into Maven Projects

#### Step 1: Add OpenRewrite Plugin to `pom.xml`

To use OpenRewrite in a Maven project, first, add the OpenRewrite Maven plugin to your project's `pom.xml`:

```xml
<project>
  <build>
    <plugins>
      <plugin>
        <groupId>org.openrewrite.maven</groupId>
        <artifactId>rewrite-maven-plugin</artifactId>
        <version>5.27.0</version>
        <configuration>
          <activeRecipes>
            <recipe>org.openrewrite.java.migrate.UpgradeToJava17</recipe>
          </activeRecipes>
        </configuration>
        <dependencies>
          <dependency>
            <groupId>org.openrewrite.recipe</groupId>
            <artifactId>rewrite-migrate-java</artifactId>
            <version>2.11.0</version>
          </dependency>
        </dependencies>
      </plugin>
    </plugins>
  </build>
</project>
```
Run `mvn rewrite:run` to run the recipe.
alternatively 
```sh
mvn -U org.openrewrite.maven:rewrite-maven-plugin:run -Drewrite.recipeArtifactCoordinates=org.openrewrite.recipe:rewrite-migrate-java:RELEASE -Drewrite.activeRecipes=org.openrewrite.java.migrate.UpgradeToJava17
```
#### Integrating OpenRewrite into Gradle Projects

#### Step 1: Add OpenRewrite Plugin to gradle
- Add the following to your `build.gradle` file:
```build.gradle
plugins {
    id("org.openrewrite.rewrite") version("6.11.2")
}

rewrite {
    activeRecipe("org.openrewrite.java.migrate.UpgradeToJava17")
}

repositories {
    mavenCentral()
}

dependencies {
    rewrite("org.openrewrite.recipe:rewrite-migrate-java:2.11.0")
}
```
- Run `gradle rewriteRun` to run the recipe.

