---
layout: post
title:      "Setting up a Rails App with Devise: Benefits & Drawbacks"
date:       2019-05-30 13:12:05 +0000
permalink:  setting_up_a_rails_app_with_devise_benefits_and_drawbacks
---


I found at the start of my Rails Project that I was very overwhelmed — we had not attempted a project of this size yet and knowing all of the different files, views, and controllers that I would need was anxiety-inducing. Thankfully, Devise, a gem used to setup a user authentication system for a rails app held my hand through it. It enabled me to focus more on user experience, design, and which key features to build out, rather than the technical minutiae that are characteristic of completing the Rails section’s code-alongs and lab curriculum.

Setting up a rails app with devise is a snap:

Once you’ve created your repo and project, add the devise gem to your Gemfile and run ‘bundle install’:

> gem 'devise'
> bundle install

Then run the following in your terminal to fully install devise in your app:

> rails g devise:install

Next, you will need to configure devise’s default url options. Within config/environments/development.rb, add the following line (before end):

> config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }

Devise comes with default alerts that appear based on its user authentication system, in order to see those in your views, you need to include the following two p tags:

> <p class="notice"><%= notice %></p>
> <p class="alert"><%= alert %></p>

These same two lines can also be used to display the validation errors a user would receive when, say, improperly complete a form on your app. Initially, I placed these two lines between the head and body of my views/layouts/application.html.erb file, so that they could be accessed globally throughout my app, however, I learned that if I created a partial template — which I aptly named alerts.html.erb, I could more easily reference a users validation errors with a single-line addition appended to the end of whichever line I used to take my user to the next page following their unsuccessful form submission:

>[redirect or rendering of next page] , alert: errors.join(", “) or , notice: errors.join(“, ”)

You will still need to place a <%= yield %> in the body of your layouts file to yield to the views that you will be creating for the other pages of your Rails app.

Then, the moment you’ve been waiting for! Setting up your User model with devise:

> rails g devise user
> rails db:migrate

Once that is done, you can use the auto-generated file db/migrate/seeds.rb to create seed data (dummy data to test and play around with) that contains instances of the user class. Seed your data base with this data using:

> rake db:seed

And to ensure your rails server is running properly, run:

> rails s

and open up  http://localhost:3000/users/sign_up to create your account and test to make sure everything is working.

Devise, although being so incredibly easy to setup, does have its drawbacks: while it affords a quick and easy user authentication system setup experience for a budding rails app, having devise generate those account registration routes made me feel as though I had less control, understanding, and ownership of my routes, especially those concerning the user. I remedied this after both diving deeper into seeing what Devise had generated for me and after adding routes that enhanced those that devise had created. Overall, this enabled me to create a more fleshed-out and secure Rails app. 

