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
  src: "jhipster-module-header.png"

toc:
  auto: true  
---

💡  JHipster from main branch 👨‍💻  :two_hearts:

## Introduction

Sometime upgrading the Jhipster modules takes time after the Jhipster officially released.

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
