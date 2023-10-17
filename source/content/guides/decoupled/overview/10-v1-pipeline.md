---
title: Pantheon Front-End Sites
subtitle: Opting in to the V1 Pipeline
description: Build Caching and Node Versions
tags: [webops, workflow, decoupled]
contributors: [stevector]
layout: guide
showtoc: true
permalink: docs/guides/decoupled/overview/v1-pipeline
reviewed: "2023-03-23"
contenttype: [guide]
innav: [false]
categories: [create]
cms: [decoupled]
audience: [development]
product: [decoupled]
integration: [--]
---

In the Fall of 2023 Pantheon introduced a new build pipeline for Front End Sites.
Among under-the-hood-optimizations, like caching of folders between builds, the new pipeline changes the mechanism by which the Node.js version is selected for your build and your runtime environment.

Sites made prior to DATE will continue to use the old pipeline, and will need to opt-in to the new pipeline to take advantage of the new features.

Sites made after DATE will automatically use the new pipeline and cannot opt to the old pipeline.

On NEXT DATE, all sites will be migrated to the new pipeline.

## How to Opt-In

We recommend trying the new pipeline with a branch or pull request before switching over all brances and builds.

To switch over a single multidev environment, set an environment variable in your site's dashboard named `FLAG_V1_PIPELINE` to the name of a Multidev branch that you can make next like `multi-v1pipeline`.

TODO: Add screenshot

To see the improvement in build times, you will need to make at least two pushes to the branch.
The first push will be a full build, and the second push will be a cached build.
For our own Docs site, we saw a reduction of many minutes in build time.

If you are satisfied with the results, you can switch over all branches and builds by setting the environment variable to `all`. If you wish to test across multiple branches, you can set the environment variable to a comma-separated list of branches like `multi-v1pipeline,multi-v1pipeline2`. TODO: ADD PR EXAMPLE see https://docs.google.com/document/d/1XWVyLfGTisRHVzYp1k0akBCG-YBWnD1fSHFxopSo1Ng/edit?disco=AAAA7Cn4Yto

TODO: Add screenshot