---
layout: post
title: Myths & Mysteries of Scraping/Crawling - 2
---

### Check out the initial post <a href="/2014/09/09/scraping-post/" target="none">Myths & Mysteries of Scraping/Crawling - 1</a> before going through this one.

In this post I will get into language specific resources. I will discuss using Ruby, Python, NodeJS and a tool called Apache Nutch

First I will start with ruby

* Common Libraries/Gems used:
	* Nokogiri (for direct retreival), Mechanize (for form filling/submission, button clicking etc), open-uri(library used to send request to the server)
* Resources:
	* Check for screencasts on railscasts, but beware of the version. Using screencast you will learn how to use them, then use the official documentation to actually write your code.
* Pitfalls:
	* If you are working behind a proxy server always check for proxy support in the gems.
	* Generally used for the case of web scraping. I mean i feel like mechanize is not upto the mark as compared to selenium from python
* Use case:
	* Best use case is while using Nokogiri i.e. for direct data retreival

Now coming to python

* Common packages used:
	* Scrapy (for direct retreival), Selenium (user behaviour emulation)
* Resources:
	* The best resource I found is on their own official website, but there is also a large user community for these.
* Pitfalls:
	* Problems in slow internet connection (as selenium uses browser).
* Use case:
	* Best case is using selenium as it emulates the browser and user, it can be very useful in cases of  user login or security precautions like fixed timed session etc.

Now coming to NodeJS

* Common libraries used:
	* cheerio (for direct retreival), CasperJS (user behaviour emulation)
* Resources:
	* The best resource I found is on their own official website, but there is also a large user community for these.
* Pitfalls:
	* As you will be using NodeJS you must write all the code asynchronously, which can be daunting for those who are not familiar with it.
* Use case:
	* The main advantage is cheerio provides jquery kind of DOm selector which is very easy to handle. Useful when writing a quick and dirty scraper

Finally the tool Apache Nutch

* Packages used:
	* No packages required except Java. It can be easily installed following the instructions on its website.
* Resources:
	* The best resource I found is on their own official website, but there is also a large user community for these.
* Pitfalls:
	* As you will be using a tool, you wont be able to understand all the intricasies. I maen yeah you can read and understand the whole code for knowing more about the tool
* Use case:
	* Ideal for use as a crawer/spider and you need the whole website data like in the case of a search engine.
	* Easy integration with other tools like Apache Solr, Elasticsearch.

For selecting specific data (i.e. for getting css) you can use the tool selector gadget or you can simple use the developer tools/forebug.

Thats it for this post. I hope all the above information will be useful for you and if you have any quereies you can shoot me a <a href="mailto:rajeev.reddy.d@gmail.com">mail</a>.

##Happy Scraping !!!

-----
