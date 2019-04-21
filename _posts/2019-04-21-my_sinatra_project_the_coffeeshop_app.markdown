---
layout: post
title:      "My Sinatra Project: The CoffeeShop App"
date:       2019-04-21 18:54:49 +0000
permalink:  my_sinatra_project_the_coffeeshop_app
---

Those that know me are intimately aware that I am an avid consumer of coffee and tea beverages, in fact, more than 90% of my completed Learn.co labs, readings, and (so far) projects are completed at a nearby Dunkin Donuts or a Starbucks cafe. 

That’s why when we were tasked with creating a web app that embodied reciprocal has many and belongs to associations, I instantly thought of a user that places coffee orders, with each order having many coffee drinks (and reciprocally, each coffee drink belonging a specific order). At the outset of my project, I was overwhelmed. I ended up creating four models: one for the user, one for each order, one to embody a drink, and one to represent an OrderDrink: a model which embodied each record used for my join table, linking orders and drinks. In this OrderDrinks table,  each row paired two foreign keys: a drink id and an order id, and ultimately resulted in an additional many to many relationship, because drinks can belong to multiple orders and multiple orders can contain the same drink (type).

So upon the outset of creating my app, I was confident: I knew my basics for Sinatra and the MVC web app design principles and using the corneal gem, a Sinatra app generator, made the initial creation of my project a snap. However, the coding the logic behind how my app would utilize those associations was more of a challenge. 

Setting up the order creation and edit forms enabled me to use checkboxes to allow the user to select which drink types they would like to add to their order. This information would become available in the relevant controller routes via the params hash and stored in an array with a key of drinks. This enabled me to use the CRUD (create, read, update, and delete) methods to change a user’s order information (both the contents -- specific drink types -- and the “favorite” attribute of each order). This use of the params hash also allowed me to offer users the ability to update their account information or terminate their account as well. While my project was definitely more model and association-heavy, I found that this added additional functionality in the manipulation of my database and enabled for a sleeker and more streamlined feeling to my ap
plication.

Sinatra is considered a “lightweight” framework -- in that contains the minimal functionality and it is highly malleable in how it will be used in the development of web applications, however, I found this very satisfying when creating routes. Being able to directly connect certain views with controller actions and their HTTP requests was empowering and enabled me to tap into my creative background: leaving me fully in control of the development of a pleasant user experience. 

