---
layout: page
title: "RSS-based Scene Analysis for Indoor Positioning"
description: ""
---
{% include JB/setup %}

## Introduction

Indoor positioning becomes more and more popular in recent years due to widely applications, such as indoor navigation and
business promotion. In general, there are following four methods to do indoor positioning:

* Trilateration
* Triangulation
* Scene Analysis
* Proximity

## Methods
Among these four methods, scene analysis does not rely on extra hardware. We can use the ubiquitous Wi-Fi Acess Points (AP) 
deployed in buildings to build our indoor positioning system. In this project, we use AP RSS-based scene anlysis method. This
method consists of the following two stages:

* offline stage: We select many locations in the building. And for each location, we measure the signal strengths of different APs and
  send the data to server database. We call the signal strengths measured at one location as the fingerprint for this location.
* online stage: For the location we want to know, we measure the fingerprint at this location, and compare this fingerprint with the records
  in the database. We use weighted KNN to determine user location.

<img src="../imgs/ips.jpg" alt="indoor positioning" style="width: 666px;"/>

## Results


