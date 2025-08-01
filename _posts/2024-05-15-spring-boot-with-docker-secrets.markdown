---
layout: post
title:  "Spring boot application with docker secrets"
date:   2024-05-15 11:05 +02:00
categories: [Spring Boot, docker secrets, config tree]
author: Martijn Klene
---
Using environment variables in Spring Boot is nothing new, however there was always an issue with using Spring Boot in Docker Swarm, the only way to use the secrets in the past was to create a application.yaml or conf in the secrets. With the new version however you can use the config tree, you can configure the following import.
<!--more-->
```yaml
spring:
  config:
    import: "optional:configtree:/run/secrets/"
```
With this you can for example configure a environment variable like ${app.keycloak.client-id:client-id} this will look for app.keycloak.client-id in /run/secrets, and usually this would mean that you have to create a directory structure like app/keycloak.

But with the name of the secret like app.keycloak.client-id this will work perfectly well too, leaving you with a compose file that can look like this:
```yaml
    version: "3.6"
    services:
     blog:
       image: some-image
       secrets:
         - app.keycloak.client-id
     

    secrets:
     app.keycloak.client-id:
       external: true
```
