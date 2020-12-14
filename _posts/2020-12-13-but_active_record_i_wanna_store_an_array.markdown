---
layout: post
title:      "But Active Record, I Wanna Store an Array!"
date:       2020-12-14 02:33:38 +0000
permalink:  but_active_record_i_wanna_store_an_array
---


       I spend the last week building a game in vanilla JavaScript. The game gives the user the ability to create a new level after completing all the existing levels. Upon submitting the level, the game, makes a fetch request, sending over the level data to a Ruby on Rails server. This server then creates a new instance of a level and stores it to the database. Seems easy enough. However, it's not as simple as I thought.
			 
			 The level data that I was sending over was nested. Each level consisted of an array of objects. Each of these objects represented a brick with location data. Active Record had some thoughts. As it turns out Active Record does not like storing arrays and hashes as attribues since the SQLite does not support them. Darn!
			 
			 I found a couple resources suggesting that I store it as a string and serialize it but was warned against it by a few Stack Overflow users. But wait, we are working with relational databases here! I settled on setting up two separate models, Level and Brick. This allowed me to set up a has_many and belongs_to between these two models and make two separate fetch requests creating first the level and then creating associated bricks from one JavaScript instance. While it felt a little strange, it practice, it worked great and it allowed me to avoid doing any bizare serialization. WIN-WIN!
