---
layout: post
title:      "Ruby CLI Project"
date:       2019-11-06 03:11:10 +0000
permalink:  ruby_cli_project
---

For my CLI project, I created a “scraper gem” that pulls specific information off a website and presents it to a user.

I utilized the website of the furniture shop, www.roomandboard.com.  

There are 53 sofas listed on the site, and I wanted to be able to present a list of those products to the user and allow them to choose a product, and be able to see further details such as price range and options (ie. fabric, size).

The main thing to create this gem is to create repository in github, then clone and download it to the IDE.  The gem will have a bin folder, lib folder, gemfile, and other necessary files automatically created.

I required nokogiri and openURI in the executable files.

Nokogiri is an HTML, XML, SAX, and Reader parser. Among Nokogiri's many features is the ability to search documents via XPath or CSS3 selectors. OpenURI is a popular tool that is used to fetch contents on a URL and display it on the console. It directs the gem to the website you give it, and then Nokogiri scrapes the information that you need.

My gem is getting two levels of information from the website. The names of the chairs and the details (price ranges, options). These bits of information are found when you inspect the CSS for the parent (chair names) and the child tags (price ranges, options).  It took a little time to figure out what these were on the website but it became more apparent with some practice. This website called the chair names = product groups. It referred to the details as pg-price and pg-options. 

I created a scraper file in the lib, to make these details clear, so that the user can obtain the exact information they need.

I created a CLI file in the lib, which is the code that interacts with the user. It presents the information to them. It asks which chair to look up as well, and shows them the details for that product.

The chair.rb file contains the data for all the chair names.  The details.rb file contains the data for the details on the chosen chair.

That is a brief synopsis of the scraper gem.


