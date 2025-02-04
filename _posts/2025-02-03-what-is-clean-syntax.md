---
layout: post
title: What is Clean Syntax?
description:
image:
category:
tags:
date: 2025-02-03 21:20 -0500
---
Programmers talk about *clean syntax* say and this or that language or framework has such a property. I've commented that Ruby and Ruby on Rails have this thing, too. So what is it?

I think it means the syntax is easy to read and easy to follow. Further, it has few, if any, delimiters. Delimiters such as `[`, `(`, and `{`. Looking at any JavaScript code shows exactly what I referring to -- nested `[`, `(`, and `{` everywhere!

Because I've been working with Laravel and Ruby on Rails lately, I have examples from those.

Both of these code snippets do the same thing -- read the first record from a database.

Laravel is explicit in naming the table of interest and there's a fair number of expressions and parameters:
```php
$color = DB::table("colors")->find(1);
```
Rails, on the other hand, takes just a few expressions to get the job done:
```ruby
@color = Color.first
```
Both work just fine and neither is 'better' than the other. It's just that the Rails syntax is so much *cleaner*.

Another example is the way in which the two send the user to a view with a variable to use from a controller.

Laravel:
```php
return view("colors", ["color_hex" => $color_hex]);
```
Rails requires nothing at all. Rails controller methods 'know' where their views are and just send the browser there. Views 'know' about their controllers' variables and have access to them automatically.

One more. Both of these snippets define a route with a name. 

Laravel:
```php
Route::get("/colors", [ColorController::class, "colors"])->name("colors");
```

Rails:
```ruby
get "colors", to: "colors#colors"
```

Here, Rails 'knows' the definition is in the `routes.rb` file, so must be a route definition. And it 'knows' there's controller `colors` with a method `colors`.

So combining Rails *convention over configuration* with Ruby's simple syntax results in less code that is easier to read. The downside is that you must understand Rails' conventions.

Needless to say, once you've worked with PHP and Laravel for a while, you eye will not notice the complexity of the code quite as much. And you may actually prefer being explicit about what you want the code to do.

But I'm a hobbyist without the experience to digest a block of PHP or to know what classes and namespaces to include as easily as the professionals.

