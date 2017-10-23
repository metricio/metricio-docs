---
title: "Home"
date: 2017-10-22T17:53:34+02:00
---

<h1>FAST & SIMPLE DASHBOARDS FOR ALL YOUR METRICS</h1>

<p style="text-align: center;"><a href="https://semaphoreci.com/dannycroft/metricio"><img style="margin: 0;display:inline"src="https://semaphoreci.com/api/v1/dannycroft/metricio/branches/master/badge.svg" alt=""></a> <a href="https://codeclimate.com/github/dannycroft/metricio/maintainability"><img style="margin: 0;display:inline"src="https://api.codeclimate.com/v1/badges/4118cd99d826d332002c/maintainability" alt=""></a></p>

Metricio [(🔊)](https://res.cloudinary.com/metricio/video/upload/v1508691679/metricio_b4nmgk.mp3 "pronunciation") is a dashboard framework that helps you display metrics and monitor
systems and APIs.

Simple to get started and quick to create build screens for all your teams.

Metricio has a similar design and achitecture to [Dashing](http://dashing.io/),
which was my "goto" framework for dashboards for years. Unfortunately, Dashing
is [no longer maintained](https://github.com/Shopify/dashing/issues/711). But if
you still prefer to write CoffeeScript and Ruby then that framework is still
awesome!

Metricio allows you to:

- Build **widgets** with React components
- Create **jobs** with Node.js and **async/await**
- Support for multiple **dashboards**
- CRON like scheduling with [node-scheduler](https://github.com/node-schedule/node-schedule)
- Caching handled with [Redis](https://redis.io/)
- Event-based communication with [socket.io](https://socket.io/)
- Number formatting with [Numeral](http://numeraljs.com/)

  The UI aims to use little resource as possible. Enabling your dashboards to
  run without crashing for prolonged lengths of time on even the most neglected
  Raspberry Pi.

  ![Example](https://res.cloudinary.com/metricio/image/upload/v1508687267/metricio_yxmmxo.gif)