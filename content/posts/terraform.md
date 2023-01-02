---
title: "Terraform"
date: 2023-01-01T10:38:29+05:30
draft: false
tags: 
  - Tech
  - Tutorial

categories: ["Tech", "Tutorial"]

description: A tool that allow infrastructure automation for provisioning of any cloud or service.
thumbnail: "/images/terraform.png"
image: "/images/terraform.png"
---

# Why we need Terraform 

Before we deep dive understanding about terraform lets understand the problem first. Why do we need this tool or what is the problem we are solving using terraform. 

We are going to understand the problem using a simple example. Lets say we are setting some infrastructure for our project. On the first day we don't no what all thing we need in future. Things in the sense we might need some tool or service (like SaaS, PaaS or IaaS). So whatever we need we can setup on first day. On the next day we want to add things on whatever we have and we might need versioning also for the same.For managing these tool we might want some sort of automation. So here comes terraform.


# What is Terraform?

Terraform is a `Infrastructure as code` tool.It lets you define resources and infrastructure in human-readable, declarative configuration files, and manages your infrastructure's lifecycle.


# Why should you use Terraform?

When it comes to building infrastructure there are two main possibilities: cloud and on-premise.
The fundamental difference between cloud and on-premise infrastructure is where the infrastructure exists.

## What is on-premise infrastructure?

When all the resources is installed locally on your company's physical servers.

## What is cloud infrastructure?

When all the cloud infrastructure, rather than use your own servers, all networking resources are run and fully managed by third-party providers on their servers for example: aws, azure, gcp.


# How Terraform can help?

Terraform allows DevOps Engineers to automate and manage the Data Center Infrastructure, the platforms, and the services that run on those platforms, all from one location, that you can reuse and share.

Instead of handling the infrastructure manually by logging into the AWS Web Console to create each component of your infrastructure, you just do it in code.
And if you need to change anything? Well then you just update the Terraform code and apply it, helping you to automate your cloud infrastructure and configuration.


## Further Read

Want to know more about terraform you can go on [free tutorial](https://developer.hashicorp.com/terraform/intro) available on official terraform site.