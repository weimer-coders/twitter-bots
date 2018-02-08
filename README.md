
# Twitter Bots
## What is a Twitter Bot?
- Twitter bots are scripts that use Twitter’s API to do anything from post Tweets to send DMs, to create Tweets with information gathered from another API or data source. Here’s a link to a video that gives a brief overview.
- Most developers use Node.js or Python
- If you want a review of Node.js, see Andrew's [walk-through](https://github.com/brizandrew/writing-modular-code)

## Examples of Twitter bots
There are useful and/or interesting Twitter bots, and then there are spam Twitter bots.

## Examples of Twitter bots
There are useful and/or interesting Twitter bots, and then there are spam Twitter bots.

Here are some examples of good Twitter bots:

**International Space Station Bot**
Sends you a direct message whenever the international space station (ISS) will be visible at your location. See link [here](https://twitter.com/twisst).

**Earthquake Bot**
Tweets about the location of earthquakes and their magnitude when they register as 5.0 or greater on the Richter scale. See link [here](https://twitter.com/earthquakeBot).

**Trump Alert**
A bot tracking Trump family follow and unfollows, so we can try and figure out what is going on inside the White House. See link [here](https://twitter.com/TrumpsAlert).

**Trump’s Feed**
A bot that retweets tweets from people the president follows on Twitter. A project of Phillip Bump of the Washington Post. See link [here](https://twitter.com/TrumpsAlert).

Many bot repos aren't public, but a lot by journalists are, like Joe Fox's [colorschemer](https://github.com/joemfox/colorschemer) and Ken Schwencke's [fec-moji](https://github.com/Schwanksta/fec-moji). [Poynter](https://www.poynter.org/news/7-best-twitter-bots-journalism) also has a good list of journalism Twitter bots.

## Your Twitter API Key
In order to access Twitter’s API, you need a key. You can do this by following the steps below:

1. Go to https://apps.twitter.com/.
2. Click on “Create New App”
3. Fill in the details of the application you'll be using to connect with the API
4. Your application name must be unique. If someone else is already using it, you won't be able to register your application until you can think of something that isn't being used.
5. Click on “Create your Twitter application.” Details of your new app will be shown along with your consumer key and consumer secret. If you need access tokens (as you will for this project), scroll down and click “Create my access token.” The page will then refresh on the "Details" tab with your new access tokens. You can recreate these at any time if you need to.

By default your apps will be granted for read-only access. To change this, go to the Settings tab and change the access level required in the "Application Type" section. You can always go back to see your existing bots by going to the original link at the top.

## Using your API Key
### Python
To start accessing the API, you'll need to start your script by importing a way to access the API (here we use Tweepy)
```
import tweepy #https://github.com/tweepy/tweepy

consumer_key = "ThisWillBeAStringOfValues"
consumer_secret = "ThisWillBeAStringOfValues"
access_key = "ThisWillBeAStringOfValues"
access_secret = "ThisWillBeAStringOfValues"
```
Note the need for quotation marks.

Some walk-throughs you should look at are [Build A Tweet Bot With Python](https://scotch.io/tutorials/build-a-tweet-bot-with-python) and [CUNY's Make a Twitter Bot](https://jitp.commons.gc.cuny.edu/make-a-twitter-bot-in-python-iterative-code-examples/)


### Node
 For Node, you'll need to have your API access information as part of your configurations and dependencies.

In your main js file, you'll need to require Twitter. There are different ways of formatting this, and Andrew has a longer explanation in the discussion post for those interested. But most of the walk-throughs will look like this:

```var Twit = require('twit');```

You'll pass your keys into the js file.
```
var Bot = new TwitterBot({
 consumer_key: process.env.BOT_CONSUMER_KEY,
 consumer_secret: process.env.BOT_CONSUMER_SECRET,
 access_token: process.env.BOT_ACCESS_TOKEN,
 access_token_secret: process.env.BOT_ACCESS_TOKEN_SECRET
});
```
For a full walk-through of how to build a few different types on Node Twitter Bots, read [How to build and deploy a multifunctional Twitter bot](https://medium.freecodecamp.org/how-to-build-and-deploy-a-multifunctional-twitter-bot-49e941bb3092) and [TechKnights](http://techknights.org/workshops/nodejs-twitterbot/).

**Note: When you commit your repo to GitHub, make sure you are removing your access info, otherwise people can manipulate your bots.**

## Deploying your bot
So your bot needs to live on a server outside of yours’. In order to do this, you need to deploy it to a server that can run your code and constantly allow requests to go through.
### Heroku
[Heroku](https://www.heroku.com/) is the best dynamic deployment option we've found and that most of the coding community seems to use. You're welcome to try other platforms as well. For Heroku, you’ll have to see how much space and how often your bot needs to run/respond. Some projects on Heroku can be free, but you’ll most likely need to get a basic account. It’s $7 a month, and you can split the cost with your partner, if needed.

#### Bonus: README syntax and testing
In the course of writing this, we found this really helpful [guide](https://help.github.com/articles/basic-writing-and-formatting-syntax/#quoting-code) on README syntax and a [website](https://stackedit.io/app) that lets you write in that syntax and shows you what it will look like on GitHub in the adjoining panel.  

![Twitter Bot Comic](https://imgs.xkcd.com/comics/twitter_bot.png)
