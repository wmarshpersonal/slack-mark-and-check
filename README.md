# slack-mark-and-check
Bash scripts to poll a Slack channel to see how many unread messages there are,
to mark all messages read, and to read the timestamp of the latest message.

Usage:
~~~~
  slack-channel-check [channel_id] (return number of unread messages in channel)
  slack-channel-mark [channel_id] (mark all messages read in channel)
  slack-channel-get-ts [channel_id] (get the timestamp of the latest message)
~~~~
The environment variable **SLACK_TOKEN** should be set to access the Web API.
Create a bot user in Slack or use a user token for your own user.

#### Use cases:
###### Trigger an rsync from a channel message:
~~~~
  if [ $(slack-channel-check C123456) -gt 0 ]; then do_rsync; slack-channel-mark C123456; fi
~~~~
