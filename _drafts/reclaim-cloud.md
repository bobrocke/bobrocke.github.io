---
layout: post
title: Reclaim Cloud
description:
image:
category:
tags:
---
With so many good options for cloud-base hosting, it has taken me a while to find one to at least start with. With Reclaim Cloud's two week free trial, I can see what it's all about.
<!--more-->
The reason I wanted to consider hosting beyond simple shared hosting was to have a solid way to experiment with Laravel and Ruby on Rails. My [regular WordPress blog](https://bobrockefeller.com/) is on Reclaim's shared hosting and it works just fine and is just $35 per year. But I've had nothing but trouble trying to get a Laravel app running there and it just may be because full access to the server is not possible.

Cloud hosting might be a necessity for more complicated apps such as those on Laravel and Ruby on Rails frameworks. Having greater access to the server allows for customizing PHP (or Ruby) versions and SHH access is almost mandatory.

My first step with cloud hosting was to install a WordPress environment and get my blog running there. And that lead to the first dead end. A simple setup on Reclaim Cloud can cost $5 a month, or less; one with a database (necessary for WordPress) adds at least an extra $5 per month. $10 per month is more than I plan to spend on a hobby hosting setup. So no WordPress or any other web site that requires a database.

Next up was to get my simple Ruby on Rails experiment (which uses only SQLite -- a server-less, file-based, database for simple things) running. More trouble. Errors trying to get ruby 3.2.2 installed sent me to technical support to even get that working.

My Rails app would exceed the capacity of 1 Cloudlet (128 MB of RAM and 400MHz of CPU) doing the simplest of tasks. Even running `bundle` shut down the App Server for going beyond the limits. `bundle` would run on 2 Cloudlets, but `bundle update` would not. not even on 3 Cloudlets. 4 Cloudlets finally did the trick -- but that increased the monthly maximum cost from $2.80 (1 Cloudlet) to $11.80 (4 Cloudlets)!

I do have experimental versions of my Laravel and Rails apps running on shared hosting at HelioHost. The offer free and low cost (think $1, total) hosting and even offer MariaBD and PostgreSQL at no extra cost. Of course, the downside is that HelioHost is run by volunteers (so technical support, while good, can be slow) and doesn't provide near the speed of other, more expensive, hosts.