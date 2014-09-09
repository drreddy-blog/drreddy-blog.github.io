---
layout: post
title: Myths & Mysteries of Scraping/Crawling - 1
---


<div class="message">
  It has been long since I have posted anything on this blog, recently I have been working on various scrapers and crawlers and so this post will contain some of my experiences and the guidelines/referrences according to me, which can be useful for some who is starting on writing a crawler/scraper.
</div>

###I will not show you some sample code this is not a tutorial, but i will provide you with all the resources which you can use to write it yourself.
----
I beleive that you know what a web crawling/scraping is? If asked I would crudely put it as a form of technology wherein a script or a software retreives the content/data from a website/bunch of websites with out you doing manual work. You can check more on wikipedia.
####Before going any further, There are some rules which needs to be followed for scraping a website / crawling it
 * Respect robots.txt
    * Every server will have this file and contains info about which parts of the site can be crawled or simply to say which data of the site can be accessed
 * Don't increase the server load too much
    * You may not be the only person using the website there are real users who may have real needs, so don't load the server and crash it. This can be avoided a by adding a time put between your requests
 * Legal issues
    * Now coming to the law this whole scraping and crawling is in a grey area.

----

There is no one magic scraper which works for all the websites. So I will discuss a general flow here:

1. First pick out a website which will satisfy all your data needs.
2. Check what would be the general flow like for example do you have to login for viewing data/how the data is getting loaded like is there a pagination or ajax calls being made.
3. Check if the website has implemented any client side security like limited time sessions etc.
4. Check out the layout of the website like the CSS-selectors which can be used to extract the data.
5. Write scraper taking into consideration all the above points, run it either locally or on a remote server and store the data.

> writing and running a scraper/crawler is a long and tiring task you will face a lot of issues. You will just have to take time and finish it the end result would be amazing trust me, this is coming from a guy who has written scrapers successfully and retreaved data of around ~16 lakh entries

So thats it for this post in the next one I will give you language specific resources.

----- 
