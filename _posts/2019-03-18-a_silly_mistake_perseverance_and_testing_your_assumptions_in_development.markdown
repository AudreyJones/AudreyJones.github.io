---
layout: post
title:      "A Silly Mistake: Perseverance and Testing your Assumptions in Development"
date:       2019-03-19 00:09:37 +0000
permalink:  a_silly_mistake_perseverance_and_testing_your_assumptions_in_development
---

When I first started the OOP curriculum at Flatiron, I was so excited. I had been self-studying coding on and off for a couple of years, and I felt like I had waited so long to reach this material!

So when our first project, the creation of a CLI Ruby Gem came, I was so stoked! Finally, I could put my little bit of OOP knowledge to use! As an avid gamer and consumer of Nintendo products, I decided to base my project around Nintendo’s top-selling games. 

At the outset of this project, I really (odd as it may sound) found that I enjoy scraping! I love the idea that I could both visualize (via Chrome’s Developer Tool’s point-and-click ‘Inspect’ tool) and access HTML elements organized into nodes by Nokogiri. It doesn’t hurt that visualizing the nodes also helps me to parse elements more effectively.

My gem first scrapes the index page for Nintendo’s best-selling games (https://www.nintendo.com/games/bestsellers) and then accesses each individual game’s url (game_url) and scrapes that to provide the user with more information about the particular game that they’re interested in (the rating, category, and number of players). I did this in my class definition for my scraper (scraper.rb), in which I created two methods: #.scrape_index and #.scraped_title to scrape those pages, respectively.

Using CSS selectors and Nokogiri was a snap in finding the elements I needed for the bestsellers index page, but when I tried to scrape individual game title pages, I received blank return values for my searches: empty arrays, empty strings, or nil.

My initial thought was that I might be mis-using Nokogiri syntax or that I was not using the right css selectors when searching the page’s HTML tags. After a few frustrating days filled with cssselector testing, consulting with my cohort mates, and googling Nokogiri documentation (and let’s keep it real – some soul-searching), I realized that I had made a fundamental assumption that proved to be incorrect: the game_url variable for the game’s title page was returning only a ‘/’! This, concatenated onto https://www.nintendo.com was having my second scraping method scraping the Nintendo homepage! So that whole time I had been basically scraping a site blind! 

No wonder my return results had been so empty. After resolving the initial scraping of the game_url, and ensuring that it was concatenated and encapsulated in my game_page variable, scraping once again became infinitely easier – and once again, something that I looked forward to.

I have found that over the last few weeks being in the Flatiron program, I have made numerous silly mistakes such as this one. And while incredibly frustrating (and disheartening at times), I find that they tend to be the best teachers in helping me to hone my troubleshooting skills and response to error messages. I’m just immensely thankful to have the space, opportunity, and support in which to make these necessary, but silly mistakes and have them inform my growth early on – on the path to becoming a software developer.

