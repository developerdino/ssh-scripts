# Setting up ssh-agent to run on login and add your keys

## .profile

Add a `KEYS` variable to your bash profile and export it. Can be 1 or more keys you want to add to your agent. Must have either an absolute path or be based on your home dir.

i.e. add this to .profile, .bashrc or.bash_profile depending on your setup.

```bash
KEYS=~/.ssh/key1 ~/.ssh/key2
export KEYS
```

Use the following script when logging in to make sure your ssh-agent is running and has your keys loaded.


```bash
if [ -f ~/ssh-scripts/ssh/load-agent ]; then
    . ~/ssh-scripts/ssh/load-agent
fi
```

Now when you log in to your system you will be asked for a passphrase for the keys you specified in your `$KEYS` environment variable.
