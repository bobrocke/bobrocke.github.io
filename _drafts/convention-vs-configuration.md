---
layout: post
title: Convention vs. Configuration
description:
image:
category:
tags:
---
Ruby on Rails is well known for its philosophy of *convention over configuration*. And there are most certainly benefits to that approach. But are there also disadvantages that outweigh the advantages?
<!--more-->

Rails' *convention over configuration* is basically the opposite of Django's and Laravel's *explicit over implicit*. Relying on convention reduces a certain amount of programmer overhead when writing code because Rails 'knows' what to do in many circumstances without have to be 'told'. For example, there's no need for PHP's `uses` in Laravel nor Python's `import` in Django. Rails' routes 'know' about controllers, and controllers 'know' about views without having to be 'told'.

Less code means fewer places for mistakes and faster reading. But it also means that programmers have to understand those conventions and what that means in code. That's a big disadvantage to *convention over configuration*.

A programmer with a strong background in other frameworks will take a while to get up to speed with Rails, but an experienced Rails developer understands right away. I may jump around from one framework to another experimenting and then come back to Rails needing to relearn those conventions. Laravel and Django code may be more verbose, but its meaning is clearer because everything is spelled out.



