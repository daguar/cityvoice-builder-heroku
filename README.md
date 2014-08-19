# CityVoice-Builder for Heroku

## Deployment

Non-CFA users shouldn't need to deploy this, but for documentation purposes, here goes!

First, go to [your account page on Heroku](https://dashboard.heroku.com/account) and under 'API Clients' click the 'Register API Client' button.

There, set the Name (whatever you want) and the OAuth Callback URL (this will be /callback on your deployment, for example: https://my-cityvoice-builder-instance.herokuapp.com/callback )

Once you've done that, note the 'ID' and 'SECRET' it gives you.

Now, clone this repo and `cd` into the folder. From there, create a Heroku app with your own name:

    $ heroku create my-cityvoice-builder-name

Now, configure your Builder app with the ID and SECRET from above:

    $ heroku config:set HEROKU_OAUTH_ID=lolmyoauthid
    $ heroku config:set HEROKU_OAUTH_SECRET=lolmysecret

Now push!

    $ git push heroku master

Lastly, provision Heroku's RedisToGo add-on:

    $ heroku addons:add redistogo:small

(Details and pricing [$39/mo for the small add-on shown above] can be found at: https://addons.heroku.com/RedisToGo )

Copyright Code for America Labs 2014, MIT License

