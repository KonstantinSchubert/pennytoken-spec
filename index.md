---
title: The Pennytoken Micropayment System
layout: page
---


The pennytoken specification aims to define a micropayment system that provides an immediate benefit both to the content providers and the consumers. The goal is friction-free cross-provider consumption of online media and other services. 

By forcing interoperability, it tries to prevent lock-in effects as well as a harmful fragmentation. It also leaves room for competing operators to differentiate.

## Specification

[The specification can be found here](details/).

## The actors 

Three types of actors interplay during a micropayment transacting. 

1. The content creator: 
    For example the operator of an online news website. 
2. The user: 
    For example a person browsing the internet, consuming media content on different websites. 
3. The micropayment service provider: 
    He is paid by the user and pays the content creators according to usage. 

## Design goals 
 * Works across an unlimited number of content providers. 
 * Avoid user tracking. 
 * Easy implementation for the content providers.
 * Pay-per-view for prices comparable to advertisement revenue. 
 * Frictionless user experience. No registrations, no subscriptions, no logins. 

## Design limitations 
 * The user must install a browser plugin that implements the specification. 
 * The content provider must be trusted regarding issues such as money laundering. 
 * The micropayment provider is theoretically able to track which websites are visited by the users. 


## Working Principle 
The micropayment provider sells secret tokens to the user. Like poststamps. 
The user's browser sends one or more of these tokens with the `http` request, for example by appending them to the url of a `GET` request. 
The content providers verifies and thereby cashes in the secret token with the micropayment provider. This can happen synchronously before serving the content. The content provider then responds to the `http` request and serves the for-pay content.
The micropayment provider regularly sends payments to the content provider corresponding to the total value of the cashed in tokens. 
