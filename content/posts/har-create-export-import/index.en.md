
---
title: "Using HAR Files to Improve Webapps Performance"
date: 2023-03-29T01:11:15+05:30
lastmod: 2023-03-29T21:29:01+08:00
draft: false
author: "Vidhya"
description: "How to create HAR file - Performance / debug webpapps"

tags: ["webapps", "tools"]
categories: ["web"]

resources:
- name: "featured-image"
  src: "har-feature.jpg"

toc:
  auto: true  
---


## Introduction:

As a 🌐 website owner, ensuring a seamless user experience is vital for the success of your business. 

However, despite your best efforts, you may receive feedback from users about slow 📈 page load times or other performance issues. 

This is where ```HAR (HTTP Archive)``` 💎 files can be a valuable tool for developers. 

In simple terms, a HAR file is a log 📄 of all the network ✅ requests and responses made by a web page . 

It provides detailed information such as ⌛ timings, HTTP headers, and content, which can help you 🧬 diagnose and optimize website performance issues .

HAR files can help you diagnose 🧬 and fix website ⛔ performance issues , thereby improving the user experience 🔗 . 

In this post, we'll explore how to generate and analyze HAR files.

{{< admonition type=quote title="What is a HAR file?" open=false >}}

A HAR (HTTP Archive) file is a log of all the network requests and responses made by a web page. It's essentially a record of everything that happens when a user visits a particular page, including all the assets that are loaded, such as images, stylesheets, scripts, and more.

Each HAR file consists of a JSON (JavaScript Object Notation) structure that contains information such as request and response headers, timings, and content. This makes it a valuable tool for developers who need to analyze website performance issues and optimize page load times.

{{< /admonition >}}

## Generating HAR Files:

To generate a HAR file, you need to use your browser's developer tools. Here are the steps to do this in popular browsers like Chrome, Firefox, and Safari:

### Generating a HAR file using Firefox:

  1. Open Firefox and navigate to the web page you want to capture. (for example: https://vidhya03.labkit.in )
  2. `Press F12` to open the developer tools window.
  3. Click on the `Network` tab.
  4. Ensure that the `Enable persistent logs` option is enabled.
  5. `Reload` the page.
  6. Once the page has finished loading, right-click anywhere in the network log and select `Save All As HAR`.
  
  ![Export & import HAR](blog-personal-har-03.gif)
  
### Tips for generating high-quality HAR files:

  1. Clear your browser cache before capturing the HAR file.
  2. Disable browser extensions that may interfere with network requests.
  3. Capture the HAR file for the entire user session, including any interactions on the page.

### Tips for analyzing HAR Files:

 * **`Filter requests by domain or resource type`** : Use filters to narrow down the requests to a specific domain or resource type. This can help you focus on specific issues and identify potential bottlenecks.


* **`Check request timings`**: Look at the timing information for each request, including the time it took to connect to the server, the time it took to receive the first byte of data, and the time it took to download the entire response. This can help you identify slow-performing requests.


* **`Analyze the waterfall chart`**: The waterfall chart shows the timing of each request, including the time it took to connect, the time it took to receive the first byte, and the time it took to download the entire response. The chart can help you identify issues such as long connection times, slow DNS lookups, or slow download times.

* **`Check response codes`**: Look for requests with HTTP response codes of 4xx or 5xx, as these indicate errors on the server-side. Identify the specific requests that are returning errors and take steps to fix them.

* **`Analyze headers`**: Analyze the headers for each request to ensure that appropriate caching headers are set. Caching can significantly improve website performance by reducing the number of HTTP requests and the time required to download assets.

## Conclusion:

In summary, HAR files are a powerful tool for optimizing website performance. 
By generating and analyzing them, developers can identify and fix issues, resulting in faster page load times and improved user experience. 
Use HAR files to ensure your website performs at its best.



