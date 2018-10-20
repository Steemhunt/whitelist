# Steem account black / white list
User black / white list that Steem dApps can share each other.

Each app can upload their list freely, so other dApps can use those listings to filter out abusers / spammers better.
Please request a write access to this repo via issue tickets, if you want to contribute.


## JSON Format
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

## Signed up phone numbers

Most dApps would have its own phone verifications to prevent people from making multiple alt accounts using their discounted account creation interface. However, users can still make multiple alt accounts via multiple dApps as dApps do not share their signed up numbers.

Sharing phone numbers between the services can be dangerous in terms of privacy, but just existence checks won't leak any personal information binded to the phone number.
Please implement API interface like following:

Example:
```
https://api.steemhunt.com/phone_numbers/exists.json?number=+821012345678&key=YOUR_API_KEY
-> { "exists": false }
```

To prevent brute-force attack and public access of potentially sensitive information, it's probably better idea to protect the end point using private API keys and give accesses to authorized dApps.


#### *Caution*
`+` sign on the URL parameter is translated as a space chracter, so make sure you normalize it when you query the database

Example:
```
params[:number].gsub(/^[^+](.+)/, '+\\0').gsub(/[^+0-9]/, '')
```
