---
title: "Getting started with MetalLB - A Load Balancer for Kubernetes on Bare Metal"
date: 2023-02-23T01:11:15+05:30
lastmod: 2023-02-23T01:11:15+05:30
draft: false
author: "Vidhya"
description: "Getting started with MetalLB - A Load Balancer for Kubernetes on Bare Metal"

tags: ["tools", "k8s"]
categories: ["git"]

resources:
- name: "featured-image"
  src: "fatured-metallb.jpg"

toc:
  auto: true  
---


## Introduction
MetalLB is an open-source load balancer for Kubernetes on bare metal hardware. It solves the problem of load balancing in bare metal environments, where it's not natively available, leading to scalability and high availability limitations. MetalLB supports layer 2 and layer 3 modes and can be customized to work with specific network topologies. It's a reliable and scalable choice for organizations running Kubernetes on bare metal hardware.

## Prerequisites
 - Basic understanding of Kubernetes is necessary to use MetalLB.
 - You should know how to deploy applications on Kubernetes and create/manage Kubernetes objects using kubectl or YAML manifests.
 - MetalLB is designed to work with Kubernetes clusters running on bare metal hardware.

{{< gist vidhya03 e7de7aa070e90e325d4346831d7ea2dd ipaddresspool.yaml >}}
{{< gist vidhya03 e7de7aa070e90e325d4346831d7ea2dd l2advertisement.yaml >}}
