---
layout: post
title: I Said I Wouldn't...
date: 2025-02-06 19:00 -0500
description:
image:
category:
tags:
---
A simple (I thought) desire to add a Stack Overflow icon and link to this blog's footer sent me looking for a different, but still uncomplicated theme. Soon, I was off in the weeks.
<!--more-->
I knew I wanted a theme design with the blog front and center, clear documentation for configuration (preferably via the `_config.yml` file), simple layout (I like single columns), and the ability to show icons and links to developer related social media sites (such as Stack Overflow).

There are several sites dedicated to lists of available Jekyll themes. Here are the ones I found useful:

- [Jekyll Themes](http://jekyllthemes.org/)
- [Best Jekyll Themes](https://www.bestjekyllthemes.com/)
- [JAMstack Themes](https://jamstackthemes.dev/ssg/jekyll/)

Thinking that all Jekyll themes were distributed as gem files, I was surprised to find many themes were only available as GitHub repositories that were to be downloaded and built upon by the user. The Jekyll Remote Theme gem allows you to use a theme from its repository without downloading anything -- Clever! But I had nothing but trouble trying to get it to work and gave up.

It's notable, and perhaps a little concerning, that almost all the themes I found were old. A fair number were so old that links their GitHub repositories went nowhere.

So what did I end up doing? Exactly what I said I didn't want to just a could of days ago. I downloaded the Lanyon them for GitHub and went to work customizing it. It is a really nice theme created by a real web designer (he created Bootstrap!) and you can tell. My customizations were small and, fortunately, didn't detract from Mark Ott's work.

The biggest thing I did was to add the code necessary to put social media icons and links in Lanyon's sidebar. The key to that was [Jessica Reel's post](https://jreel.github.io/social-media-icons-on-jekyll/) from 2017. Here's the key snippet:

```ruby
{% if site.data.social-media %}
<div id="social-media">
    {% assign sm = site.data.social-media %}
    {% for entry in sm %}
        {% assign key = entry | first %}
        {% if sm[key].id %}
            <a href="{{ sm[key].href }}{{ sm[key].id }}" title="{{ sm[key].title }}"><i class="fa {{ sm[key].fa-icon }}"></i></a>
        {% endif %}
    {% endfor %}
</div>
{% endif %}
```
