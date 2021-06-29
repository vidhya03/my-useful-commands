---
title: "K8s Useful Commands"
date: 2021-06-29T01:11:15+05:30
lastmod: 2020-03-06T21:29:01+08:00
draft: false
author: "Vidhya"
description: "K8s useful commands. for ckad/cka/cks"

tags: ["k8s", "ckad","cka","cks"]
categories: ["k8s"]

resources:
- name: "featured-image"
  src: "featured-image.jpg"

toc:
  auto: true  
---
Useful k8s commands 💡 :two_hearts:

## Table of contents

- [How to create pods](#how-to-create-pods)




## How to create pods

How to create pods

```md
kubectl run podname --image imagename

```
This command will create a nginx pods

```md
kubectl run nginx-pod --image nginx
```
