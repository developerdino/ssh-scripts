# Setting up ssh-agent to run on login and add your keys

## .profile

Add a `KEYS` variable to your bash profile and export it

```bash
KEYS=~/.ssh/my-private-key ~/.ssh/my-private-key2
export KEYS
```

Use the following script when logging in to make sure your ssh-agent is running and has your keys loaded.

```bash
if [ -f ~/helper-scripts/ssh/load-agent ]; then
    . ~/helper-scripts/ssh/load-agent
fi
```

Now when you log in to your system you will be asked for a passphrase for the keys you specified in your `$KEYS` environment variable.
