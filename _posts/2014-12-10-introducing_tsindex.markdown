---
layout: post
title:  "tsindex.ado"
date:   2014-12-10 00:00:00
categories: stata
---

Sometimes when dealing with panel or time series datasets it becomes useful to index variables.
For example, you might have GDP for various countries over time, and you want to compare growth over time from a certain point.
Doing this in Stata is easy enough, but I found myself doing it enough times that I wrote an ado-file to (a) spend less time writing the code and (b) minimize the chance of making a mistake when doing it over and over again.

The ado-file is called "tsindex" and the GitHub repository is [here][tsindex]. It's a fairly simple file, but it should save you some lines of code.
Over the next few weeks, I'm going to add functionality for multiple input variables and write a help file.
After that, it should be ready for submission to SSC.

[tsindex]: https://github.com/PrestonMui/tsindex