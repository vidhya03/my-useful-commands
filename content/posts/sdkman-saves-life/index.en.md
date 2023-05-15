---
title: "The Secret to Developer Productivity: Discover SDKMAN"
date: 2023-05-15T01:11:15+05:30
lastmod: 2023-05-15T01:11:15+05:30
draft: false
author: "Vidhya"
description: "The Secret to Developer Productivity: Discover SDKMAN"

tags: ["tools", "java","maven"]
categories: ["java"]

resources:
- name: "featured-image"
  src: "fatured-sdkman.jpg"

toc:
  auto: true  
---


## Introduction
 - SDKMAN is a command-line tool for managing software development kits (SDKs).
 - It simplifies the process of installing, managing, and switching between different SDK versions.
 - It supports popular SDKs like Java, Maven, Gradle,  Groovy, Scala, Kotlin, and more. 
 {{< admonition type=tip  open=true >}}
    Personally I use for maven gradle and Java (JDK)
 {{< /admonition >}}
 - SDKMAN provides a centralized repository of SDKs with various versions.
 - It automates the installation and configuration of SDKs, saving developers time and effort.
 - Developers can easily list available SDKs, install specific versions, and switch between them seamlessly.
## Getting Started with SDKMAN

  ### Installing SDKMAN on your system:
 - Open your terminal or command prompt. for windows run from `gitbash`
 - Run the following command to download and install SDKMAN: 
      ```sh
        curl -s "https://get.sdkman.io" | bash
      ``` 
  ### Setting up SDKMAN environment variables:
 - After the installation completes, run the following command to initialize SDKMAN:
      ```sh
        source "$HOME/.sdkman/bin/sdkman-init.sh"
      ```
  ### Verifying the installation:
 - To verify that SDKMAN is installed correctly, run the following command:
      ```sh
        sdk version
      ```
 - It should display the version of SDKMAN installed.

## Managing SDKs with SDKMAN

To effectively manage SDKs with SDKMAN, follow these steps:

### Listing available SDKs and versions:
 - To view the available SDKs and their versions, use the following command:
    ```sh
    sdk list <sdk>
    ```
 - Example for Java JDK:
    ```sh
    sdk list java
    ```
    This command will display a list of available Java JDK versions.

### Installing SDKs using SDKMAN:
 - To install a specific SDK version, use the following command:
    ```sh
    sdk install <sdk> <version>
    ```
 - Example for Java JDK:
    ```sh
    sdk install java 17.0.5-zulu
    ```    
    This command will install Java JDK version **17.0.5-zulu**.

### Switching between different SDK versions:
 - To switch between different SDK versions, use the following command:
    ```sh
    sdk use <sdk> <version>
    ```
 - Example for Java JDK: suppose if you installed already `sdk install java 11.0.17-zulu`
    ```sh
    sdk use java 11.0.17-zulu
    ```    
    This command will switch Java JDK version to **11.0.17-zulu**.

 ### Setting a default SDK version:

SDKMAN simplifies setting a default SDK version for each candidate, applying it automatically when you start a new session or open a terminal. Use the "default" command to set it effortlessly.

 - Setting a default SDK version:
    ```sh
    sdk default <sdk> <version>
    ```
 - Example for setting the default Java JDK version:
    ```sh
    sdk default java 17.0.5-zulu
    ```    
    This command will set java jdk version **17.0.5-zulu** as default.    
### Checking the current default SDK version:
 - To check the current default version for an SDK candidate, use the following command:
    ```sh
    sdk default <sdk>
    ```
 - Example for checking the default Java JDK version:
    ```sh
    sdk default java
    ```
    This command will display the currently set default version of Java JDK.

### Removing SDKs with ease:
 - To remove an installed SDK, use the following command:
    ```sh
    sdk uninstall <sdk> <version>
    ```
 - Example for Java JDK :
    ```sh
    sdk uninstall java 11.0.17-zulu

    ```
    This command will uninstall Java JDK version **11.0.17-zulu**.



## Conclusion

 - **SDKMAN** is the secret to boosting developer productivity by simplifying SDK management.
 - It provides a centralized repository of SDKs and automates installation, configuration, and version switching.
 - **SDKMAN** eliminates the time-consuming and error-prone aspects of SDK management, allowing developers to focus on coding.
 - Setting default SDK versions in **SDKMAN** further enhances productivity by reducing manual version switching.
 - Additionally, removing SDKs is a breeze, ensuring a clean and efficient SDK management process.
 - Embracing **SDKMAN** unlocks convenience, automation, and customization in SDK management.
 - With streamlined installation, effortless version switching, and the power to set default SDK versions, **SDKMAN** empowers developers to write high-quality code.
 - Discover **SDKMAN** and embark on a journey of increased productivity, seamless SDK management, and accelerated development outcomes.
