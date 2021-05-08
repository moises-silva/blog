---
layout: post
title:  "Hello Jekyll, goodbye wordpress!"
date:   2021-05-08
categories: jekyll update
---

Ok, yeah I know I am about 10yrs late to the party but finally pulled the trigger in archiving my old wordpress website and moving to a static blog platform. After about 1 second of googling and deliberation I reached out for [Jekyll](https://jekyllrb.com/). I considered using github pages for hosting but then I decided to self-host since I have a [DO](https://www.digitalocean.com/) instance I use for hobby development and testing from time to time anyways.

# Archiving a Wordpress site

If you google for archiving a wordpress site you'll find surprisingly few results. You'll find a few articles/blogs on it and they all depend on wordpress plugins or downloading some sort of web crawler apps. The plugins either did not work on my wordpress site with an old PHP version and I did not want to bother to upgrade PHP (I was using an CentOS 6 distro, don't judge me!). Another plugin simply wasn't available anymore (the author withdrew the plugin).

Given the plugins were not going to work I was considering the web crawler option when it hit me. Wait, may be `wget` has options to completely download a site and its resources recursively? after a quick google search the answer was:

**Yes it does!** 

Here is how:

{% highlight bash %}
wget --recursive \
     --no-clobber \
     --page-requisites \
     --html-extension \
     --convert-links \
     --restrict-file-names=windows \
     --domains moythreads.com
     --no-parent \
     https://moythreads.com/wordpress/ 
{% endhighlight %}

Credit goes to the [linuxjournal article](https://www.linuxjournal.com/content/downloading-entire-web-site-wget) I found about it.

Just like that. I spent more time looking at complicated ways of doing it when the easiest and cleaneast solution was right in front of my nose. The resulting archive is still at the same old url but now it's all static content for my two legacy blogs:

[https://moythreads.com/wordpress/]()  
[https://moythreads.com/astunicall/]()

This is my first ever Jekyll post and I am aiming to post regularly going forward. At least once a month. It's kind of nice and liberating to be able to write using just a textfile with markdown. I had a couple of posts started in my old wordpress blog I'll be publishing soon.

Onwards!

{% include comments.html %}