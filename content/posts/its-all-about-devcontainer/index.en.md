
---
title: "Instantly Set Up Your Development Environment with DevContainer's One-Click Setup"
date: 2023-04-10T01:11:15+05:30
lastmod: 2023-04-10T01:29:01+08:00
draft: false
author: "Vidhya"
description: ""

tags: ["devcontainer", "tools"]
categories: ["devcontainer","tools","code"]

resources:
- name: "featured-image"
  src: "coding-devcontainer.jpg"

toc:
  auto: true  
---
## Introduction

👋 Are you tired of dealing with frustrating issues when setting up a development environment on a new machine? Or struggling with collaboration problems due to different setups across team members 👥👥 ?

With DevContainers, you can:

- ✅ Define a set of tools, configurations, and dependencies in a Docker container
- 🚀 Instantly set up your development environment with just one click
- 🌀 Create consistent and isolated development environments that can be shared and reused across different machines and platforms

In this blog post, we'll explore the features and benefits of using DevContainers. We'll discuss how they can streamline your development workflow, make collaboration with other developers easier, and solve the "works on my machine" problem.

So, if you're ready to improve your development process and avoid the headaches of dealing with different environments, let's dive in and learn more about DevContainers!

{{< admonition type=quote title="What is devcontainer" open=false >}}

## What is devcontainer

🐳 DevContainers is a feature in the Visual Studio Code editor that allows developers to create consistent and isolated development environments using containers.

🛠️ With DevContainers, developers can define a set of tools, runtime environments, and configurations in a Docker container that can be used to build and test their code.

🚀 DevContainers can provide several benefits, such as reducing the time and effort required to set up a development environment, improving consistency across different environments, and simplifying collaboration with other developers.

🌎 DevContainers can be configured to support a variety of programming languages, frameworks, and tools, making it a versatile tool for developers.

👨‍💻 DevContainers can also be version-controlled and shared, making it easier for teams to standardize their development processes and ensure that everyone is working in the same environment.
{{< /admonition >}}


## Requirements

1. 🖥️ **Visual Studio Code editor:** DevContainers is a feature in the Visual Studio Code editor, so you'll need to have it installed on your machine.

2. 🐳 **Docker:** DevContainers uses Docker to create and manage the development environment in a container. You'll need to have Docker installed on your machine and running. 
  I would suggest Rancher desktop ![Rancher desktop](rancher.png) , as it is enterprise free, where as docker destop ![Docker desktop](docker.png)  is licensed for enterprise. Personally I use rancher. 

3. 🛠️ **DevContainer specifications:** To define the configuration for the development environment, you'll need to create a DevContainer specification file (either "devcontainer.json" or "devcontainer.yml") in your project's code repository.

4. 🔍 **Code repository:** DevContainers are typically used within a code repository. You'll need to have your code repository set up with the DevContainer specification file included in the project.

By meeting these basic requirements, you'll be able to set up a development environment using DevContainers in Visual Studio Code.

## How to do 



## Important links

1. VS code devcontainer extensions
 https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers
2. Reference Specification - Dev Container metadata reference
 https://containers.dev/implementors/json_reference/




