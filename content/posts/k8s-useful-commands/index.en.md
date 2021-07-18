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
- [How to view all objects in k8s](#how-to-view-all-objects-in-k8s)
- [How to find or count the number of k8s objects - namespace, pods, service](#how-to-find-or-count-the-number-of-k8s-objects---namespace-pods-service)
- [How to delete or terminate the pod force](#how-to-delete-or-terminate-the-pod-force)
- [Print lables of an object or pods](#print-lables-of-an-object-or-pods)


## How to create pods

How to create pods

```md
kubectl run podname --image imagename

```
This command will create a nginx pods

```md
kubectl run nginx-pod --image nginx
```

## How to view all objects in k8s

This command will list all the objects under the currect namespace
```md
kubectl get all
```

## How to find or count the number of k8s objects - namespace, pods, service

To simplify the output we are using ```--no-headers``` attributes alone with the commands
```sh
kubectl get namespace --no-headers | wc -l
```

## How to delete or terminate the pod force

Sometime we want to delete to pod without waiting time. The below command is useful to delete the pod without waiting time or delte / terminate the pod immediately

```md
k delete pod <pod-name> --force --grace-period 0
```
## Reading the documentation in commandline

One of the easyway to copy the syntax without referring web documentation

First search the command in the command line documentation

```md
kubectl explain pods --recursive | less
```

```md
kubectl explain pods --recursive | grep -i envFrom -A 10 -B10
```
This will list the envFrom syntax spec , before and after 10 lines 


## Print lables of an object or pods

```md
kubectl get pods --show-labels
```



