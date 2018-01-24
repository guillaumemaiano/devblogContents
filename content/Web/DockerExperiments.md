---
title: "Docker - Experiments in the Land of DevOps"
date: 2018-01-24T2:01:17+01:00
draft: false
cover_image: web_hugo_dev_cover.png
excerpt: "I deployed an NGinx server by hand, using SSL certificates from OpenCert. Now I'm interested in that tool DevOps praise, Docker."
authorname: Guillaume Maiano
authorlink: http://guillaume.maiano.fr
authortwitter: gmaiano
authorgithub: guillaumemaiano 
authorbio: "I'm a software developer, mostly doing iOS."
topics: [ "web", "VPS", "Kitura", "Docker"]
tags: [ "Digital Ocean", "Dockerfile", "Docker Compose"]
---

# Why?

Docker is a powerful tool to provide developer environments, testing environments, or production environments, with similar characteristics (at least, that's how it got sold to me, Developer734896352762).
It allows us to run our stateless services in isolated containers, but also (even though the Internet seems very conflicted about the practice) databases. Uber has a nice article explaining how much work they put into their MySQL dockerization.
My only need is to understand how it really works to simplify my development process and be able to fully interact with my backend colleagues, and their friends over at the DevOps cubicles.

# What?

I want to use Docker Compose. For now, I understand I need a file defining my application's environment: `Dockerfile`, a YAML file defining the app itself as a collection of services called `docker-compose.yaml`, and running the Compose tool itself.

## Dockerfile

My extrasimple Dockerfile:

    # FROM gets an initial image to build from
    ## busybox is a really bare starting point
    FROM busybox:latest
    # MAINTAINER is the maintainer's name and email
    ## It gets displayed during the build phase
    MAINTAINER Guillaume Maiano (guillaume@maiano.fr)

I build the machine with: `docker build -t GemDockerExperiment:latest .`

## Docker-compose.yaml


