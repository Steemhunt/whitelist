# Steem account black / white list
User black / white list that Steem dApps can share each other.

Each app can upload their list freely, so other dApps can use those listings to filter out abusers / spammers better.
Please request a write access to this repo via issue tickets, if you want to contribute.


# JSON Format
Example:
```
/steemhunt/README.md -> Explain the criteria how you validate users.
/steemhunt/whitelist.json ->
  [
    "user-a",
    "user-b"
  ]
/steemhunt/blacklist.json ->
  [
    "user-c"
  ]

* Please seperate each username with a new line so we can check the git change logs easily.
* Indentation: 2 spaces.
* Sort usernames by alphabetical orders
```
