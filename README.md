# GitHub webhook bot to rebuild site and notify keybase team

## Keybase bot account
On your dev machine, generate a bot token:
```bash
keybase bot token create
```

On your webhook server, create a bot account:
```bash
keybase bot signup -u bot -t <token from above>
```

Save the paper key it outputs for use in the next step. Install the bot to your team with the "bot" permission.

## Bot setup

Install keybase-bot from npm

```bash
npm install keybase-bot
```

Edit the `./start` script, add the paperkey from above, together with the bot username, team name, channel name, and secret for your GitHub webhook, and start the bot
```bash
% ./start
Starting...
Ready!
```

## GitHub setup

In your project repo settings, create a webhook with JSON encoding, push event only, and set a secret of your choice that matches the start script. Sending a test event should work, and pushing something should trigger the site rebuild and notify keybase.
