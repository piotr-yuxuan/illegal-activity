## Prevent forbidden network activity at work

> The computer you're used to working with keeps is also used at home for a whole different purpose. Sometimes you've even installed program which may cause forbidden network activity.

I've got to identify partly with this description. I'm willing to comply to network policies of the company I'm working for but how to be sure no program deemed 'forbidden' will ever run at the office, except if I explicitly run it.

Here is a partial solution for macOS : send a kill signal to any program your consider forbidden upon any connectivity change.

## Principles

- Use simple, robust design so it's obvious you can depend on it;
- Don't prevent the user to run a program if they want to.

## Usage

See http://www.launchd.info/ for how to use a `plist` file. It's currently set up to run a script every time something change in network connectivity, for example you connect to a new network.

- Copy `plist` file somewhere – for example in `$HOME/Library/LaunchAgents/illegal-activity-kill.plist`;
- Modify the agent triggers if need be;
- Make sure your launch agent is correctly registered to show up;
- Put script `illegal_activity_kill` in the location provided in the launch agent;
- Set the script executable;
- Append the script with any instructions you deem useful;
- Test it once.
