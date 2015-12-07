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

You will also need to change the URL in line 7 to your own blog's feed URL. After that, just symlink Pikebot to your /usr/local/bin directory like so: `ln -s $PWD/pikebot /usr/local/bin/`

Using the command `pikebot` in the Terminal will run the script, check your blog for new posts, and, if there are any new posts, will post the title and the link to Twitter. 
