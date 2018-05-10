+++
title = "Getting started"
description = ""
weight = 1
alwaysopen = true
+++

Make sure you have met the requirements below before going through the installation.

## Requirements

  - Node v8.0.0+
  - Redis v2+

## Install & Start

Download the latest release from [Github](https://github.com/metricio/metricio/releases), unzip it to your desired location and run the following inside that folder:

```
npm i && npm run start
```

Open your browser at `http://localhost:3000` and you should be up and running.


## Test

Run the current test suite.

```
npm run test
```

## Lint

Run eslint over the code base.

```
npm run lint
```

## Start - Production

Start metrico in a compressed and more performant mode.

```
npm run production
```
