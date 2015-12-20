# Pikebot

A really simple Ruby script to post new blog entries to Twitter

## Dependencies

- [Feedjira](http://feedjira.com) - Fetches and Parses RSS/Atom Feeds
- [Twitter](https://github.com/sferik/twitter) - A Ruby interface for the Twitter API

## Usage 

You will need to set up a [Twitter Developer Account](https://dev.twitter.com) and create a new App. Once you have your Consumer Keys and Access Tokens, you will need to set up the following environment variables: 

- TWITTER_CONSUMER_KEY 
- TWITTER_CONSUMER_SECRET
- TWITTER_ACCESS_TOKEN
- TWITTER_ACCESS_TOKEN_SECRET

Pikebot depends on these 4 environment variables to access the Twitter API. 

You will also need to change the URL in line 7 to your own blog's feed URL. After that, just symlink Pikebot to your /usr/local/bin/ directory like so: `ln -s $PWD/pikebot /usr/local/bin/`

Using the command `pikebot` in the Terminal will run the script, check your blog for new posts, and, if there are any new posts, will post the title and the link to Twitter. 

## Time Caveats

My blog, [Personal Development](http://www.jonathanpike.net), uses [Jekyll](http://jekyllrb.com) on [GitHub Pages](https://pages.github.com). While I've configured my local installation of Jekyll to use my own time zone, it appears that GitHub Pages defaults to UTC. You can see that I've specified on line 23 that Pikebot checks the latest blog entry against the current time in UTC. Since I live in EST, that would normally involve a calculation when I'm specifying when the blog post was written. No more! 

I've included a script called _utcnow_ that copies the current UTC time, formatted how Jekyll likes it, to your clipboard (if you're on OS X), ready for you to paste into your blog post.  To use it, just symlink to your /usr/local/bin/ directory like so: `ln -s $PWD/utcnow /usr/local/bin/` and run it by typing `utcnow`.  It will display "Copied!" if everything went as expected. 