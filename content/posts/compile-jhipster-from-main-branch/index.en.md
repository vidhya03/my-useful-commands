---
title: "JHipster from main branch"
date: 2023-03-26T01:11:15+05:30
lastmod: 2023-03-26T21:29:01+08:00
draft: false
author: "Vidhya"
description: "JHipster from main branch"

tags: ["java", "jhipster"]
categories: ["java"]

resources:
- name: "featured-image"
  src: "jhipster-2.jpg"

toc:
  auto: true  
---

💡  JHipster from main branch 👨‍💻  :two_hearts:

## Introduction
 

 {{< admonition type=quote title="What is JHipster" open=false >}}
JHipster is a development platform for building modern web applications, mobile apps, and microservices in Java and JavaScript. It provides a set of tools and workflows that make it easy to create applications using popular frameworks such as Spring Boot, Angular, React, and Vue.js. With JHipster, developers can quickly generate a full-stack application with a modern front-end, back-end, and database layer, along with user authentication, authorization, and security features. JHipster also includes built-in support for continuous integration and deployment, making it easy to deploy applications to the cloud. Overall, JHipster aims to simplify the process of building high-quality, scalable, and maintainable applications, while leveraging the best practices and technologies in the industry.
{{< /admonition >}}


Sometime upgrading the [Jhipster](https://www.jhipster.tech/) modules takes time after the Jhipster officially released.

However in this post, I'd like to show you how to clone Jhipster's GitHub repo. So you can use the latest code and try out the latest features, maybe try out a bug fix, maybe try out springboot (latest)  and basically use the latest stuff.

## Steps

### Checkout

```sh

git clone https://github.com/jhipster/generator-jhipster.git --depth=1
cd generator-jhipster
npm i
npm link

```
### Running

Once the ```npm link``` command success, we can execute the jhipster command to verfiy 

```sh
$ jhipster --version
```
However in recent the above command not working in widows. Hence running with npx excecute successfully. 

```sh
$ npx jhipster
```

Happy coding... 
