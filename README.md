# GetCards

Data scientist [Chris Albon](https://chrisalbon.com/) has been posting pictures of his machine learning flash cards [on Twitter](https://twitter.com/chrisalbon?lang=en). This repo uses a [Jupyter](http://jupyter.org/) notebook to download them for convenient viewing.

## Warning

As of April 2019, something has happened to Chris Albon's twitter feed.  The tweepy API, nor the twitter web client, can access past tweets.  This results in substantially fewer cards when running the notebook.  This is not something I can control.  Chris does have the cards on a cron job, so with enough time, this issue will become moot.


## OSX/Linux

To use this repo, you will:

* Install [Jupyter](http://jupyter.org/) and required modules
* Create a Twitter app to provide programmatic access to Twitter
* Run the Jupyter notebook
* View the png images it downloads to the repo's `ml-cards` directory.


### Install Jupyter

Run this command to install Jupyter and required modules:

* `pip install -r module_list.txt`

### Create your Twitter app

This repo uses [tweepy](https://github.com/tweepy/tweepy) to interact with Twitter. To use it, you will create a new Twitter app and insert those credentials into `Get Flashcards.ipnyb`.

1. Log into twitter
1. Browse to [https://apps.twitter.com/](https://apps.twitter.com/)
1. Click the `Create New App` button and define your new app. Here are some example values:
    * **Name**: `Get Flashcards - <your name>`
    * **Description**: `Chris Albon ML Flashcard puller`
    * **Website**: `http://www.not-used.com`
    * **Callback URLs**: `` <= blank
1. Check the **Developer Agreement** and click the `Create your Twitter application` button.
1. In the application details page, Select the "Keys and Access Tokens" tab.
1. Under "Your Access Token", click the `Create my access token` button.

### Insert your credentials

Open `Get Flashcards.ipynb` and locate these two lines:

```
    "auth = tweepy.OAuthHandler(consumer_key, consumer_secret) #Fill these in\n",
    "auth.set_access_token(access_token, access_token_secret)  #Fill these in\n",
```

Replace the `consumer_key`, `consumer_secret`, `access_token`, and `access_token_secret` with single-quoted values from your application settings created in the previous step.

See the [tweepy tutorial](http://docs.tweepy.org/en/v3.5.0/auth_tutorial.html) for more information, if needed.

### Run the Jupyter notebook

Run the Jupyter notebook from a shell in the repo root directory

* `jupyter notebook Get\ Flashcards.ipynb`

Jupyter will open a browser page, execute the code, placing all ML flashcards in a `ml-cards` local directory.

You can enter `CTRL+C` twice to stop jupyter from the command line.

### View the cards

All cards are stored in a local `ml-cards` directory.

