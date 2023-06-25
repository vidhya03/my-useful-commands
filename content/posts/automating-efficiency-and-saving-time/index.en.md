---
title: "Eliminating Repetitive Version Changes in Multiple Repositories:
Automating Efficiency and Saving Time"
date: 2023-06-23T01:11:15+05:30
lastmod: 2023-06-23T01:11:15+05:30
draft: false
author: "Vidhya"
description: "Eliminating Repetitive Version Changes in Multiple Repositories:
Automating Efficiency and Saving Time"

tags: ["tools", "automation"]
categories: ["bash","git","github"]

resources:
- name: "featured-image"
  src: "feature-automation.jpg"

toc:
  auto: true  
---

## Introduction:
In the fast-paced world of software development, staying up-to-date with version changes is crucial. However, repetitive tasks like manually updating version properties across multiple repositories can be time-consuming and prone to errors. In this blog post, we'll explore a real-life example inspired by **James Surowiecki's** concept of `"addition by subtraction"` and discuss how automating version changes not only solves a common problem but also saves valuable time.

# The Challenge of Manual Version Changes

Imagine a scenario where a software development team is responsible for maintaining seven different repositories for their projects. With each release, the team must manually update the version property in each repository, commit the changes, and raise a pull request. This laborious process not only consumes a significant amount of time but also introduces the risk of inconsistencies and human errors in versioning.

## The Friction Point:
Imagine a scenario where a software development team maintains different repositories for their projects. With each release, the team is required to manually update the version property in each repository, commit the changes, and raise a pull request. This process is not only tedious but also carries the risk of human error, potentially leading to inconsistent versioning across repositories.


## Drawing Inspiration from Lean Production:
**James Surowiecki's** observations about lean production in Japanese factories provide valuable insights into streamlining processes and eliminating waste. The Japanese companies identified points of friction in their manufacturing process and eliminated them, resulting in improved efficiency and product reliability. We can apply a similar approach to our version change problem by seeking to automate the process and eliminate repetitive effort.

## Automating Version Changes:
Recognizing the need for a more efficient solution, our development team decided to automate the version change process. They leveraged their knowledge of scripting and version control systems to create a custom solution that would save time and reduce the risk of errors.

## Implementation and Benefits:
we could use the below script that could automatically update the version property in all repositories simultaneously. With the new automated workflow, the process became as simple as executing a single command. The script would make the necessary changes, commit them, and even raise the pull request if desired.

### The script:

{{< gist vidhya03 1111d883b31cc7dfb7821b10ca8a58ae version-change.sh >}}
The script performs the following steps:

1. Set the `dir_root_path` variable to the root directory path where the code will be cloned.

2. Create an array named `files` that contains a list of microservices along with their corresponding GitHub clone URLs. Each element in the array consists of two parts separated by a semicolon (;): the microservice directory name and the clone URL.

3. Set various variables such as `itrac_codeline`, `old_version`, `new_version`, `label`, and `newbranch` to specific values.

4. Enter a loop to iterate over each element in the `files` array.

5. For each iteration, split the current element into two parts (directory name and clone URL) using the semicolon as the delimiter. Store these parts in the `Array` variable.

6. Extract the directory name and clone URL from the `Array` variable and store them in `dir_name` and `clone_url` respectively.

7. Print the full path of the microservice directory using the `dir_root_path` and `dir_name` variables.

8. Clone the microservice repository from the provided `clone_url` using the `git clone` command. The `core.sshCommand` option is set to specify the SSH key to use for authentication.

9. Change the current working directory to the cloned repository.

10. Checkout the `develop` branch.

11. Perform a hard reset to the `origin/develop` branch to discard any local changes.

12. Pull the latest changes from the remote `develop` branch.

13. Configure the git user name and email.

14. Create and checkout a new branch named `$newbranch` based on the provided `itrac_codeline`.

15. Use the `sed` command to replace the occurrence of the `old_version` with the `new_version` in the `gradle.properties` file within the microservice directory.

16. Stage the modified `gradle.properties` file using `git add`.

17. Commit the changes with a commit message indicating the updated version.

18. Push the changes to the remote repository with the specified upstream branch.

19. Use the GitHub CLI (`gh`) to create a pull request (`pr`) with the provided title, body, base branch (`develop`), head branch (`newbranch`), reviewer, and label.

20. Finally, print a message indicating that the new branch and pull request have been created for the current microservice.



## The Impact of Automation:
By implementing this automation, the development team experienced a significant reduction in the time and effort required for version changes. Previously, manually updating the version in each repository could take up to an hour per release. With the automated solution, the entire process was streamlined, saving them valuable time that could be better utilized for more critical tasks. Furthermore, the script served as a scalable solution, capable of accommodating additional repositories or adapting to changing project requirements.


## Embracing the Philosophy of "Addition by Subtraction":
The successful automation of version changes aligns with James Surowiecki's concept of "addition by subtraction." By eliminating the friction points and wasteful effort associated with manual version updates, the team achieved greater efficiency and productivity. Furthermore, the reduced cognitive load resulting from a more streamlined process contributed to a more positive work environment.

## Conclusion:

Automating version changes in multiple repositories is a game-changer for software development teams. By embracing the principles of lean production and leveraging automation, teams can eliminate repetitive and time-consuming tasks, significantly improving efficiency and productivity. The custom automation script showcased how version updates can be streamlined, saving valuable time and mitigating the risk of errors. As development teams continue to adopt automation, they empower themselves to focus on high-value activities, fostering innovation and driving their projects forward.

Automate your version changes and witness the transformation in your development process. Say goodbye to the tedious and error-prone manual updates, and embrace the power of automation for efficiency and time savings in your software development journey.

{{< admonition type=tip  open=true >}}
  Personally I use various codeline automation scripts. 
{{< /admonition >}}


