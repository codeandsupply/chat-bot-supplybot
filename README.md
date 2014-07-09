# Hubot

This is a version of GitHub's Campfire bot, hubot. This hubot is designed to work with IRC, and is based on [Hubot-IRC](https://github.com/nandub/hubot-irc)

### Testing Hubot Locally

You can test your hubot by running the following.

    % bin/hubot

You'll see some start up output about where your scripts come from and a
prompt.

    [Sun, 04 Dec 2011 18:41:11 GMT] INFO Loading adapter shell
    [Sun, 04 Dec 2011 18:41:11 GMT] INFO Loading scripts from /home/tomb/Development/hubot/scripts
    [Sun, 04 Dec 2011 18:41:11 GMT] INFO Loading scripts from /home/tomb/Development/hubot/src/scripts
    Hubot>

Then you can interact with hubot by typing `hubot help`.

    Hubot> hubot help

    Hubot> animate me <query> - The same thing as `image me`, except adds a few
    convert me <expression> to <units> - Convert expression to given units.
    help - Displays all of the help commands that Hubot knows about.
    ...

### Deploying this Hubot to Heroku

- Install [heroku toolbelt](https://toolbelt.heroku.com/)
- Change the procfile "supplybot" value to your desired hubot display name
- `heroku create name_for_ircbot`
- `heroku addons:add redistogo:nano`
- Activate the Hubot service from the integration tab
- Add config variables displayed in the Setup Inststuctions box

        % heroku config:add HUBOT_IRC_NICK=myhubot
        % heroku config:add HUBOT_IRC_ROOMS=#ircroom
        % heroku config:add HUBOT_IRC_SERVER=irc.example.com
        % heroku config:add HUBOT_IRC_UNFLOOD=true

- Deploy and start the bot:

        % git push heroku master
        % heroku addons:add mongolab
        % heroku ps:scale web=1

### Scripting

Take a look at the scripts in the `./scripts` folder for examples.
Delete any scripts you think are useless or boring.  Add whatever functionality you
want hubot to have. Read up on what you can do with hubot in the [Scripting Guide](https://github.com/github/hubot/blob/master/docs/scripting.md).
