# Steem account black / white list
User black / white list that Steem dApps can share each other.

Each app can upload their list freely, so other dApps can use those listings to filter out abusers / spammers more effectively. Please request a write access to this repo via issue tickets if you want to contribute.


## JSON Format
Example:
```
/steemhunt/README.md -> Explain what criteria you use to validate users.
/steemhunt/whitelist.json ->
  [
    "user-a",
    "user-b"
  ]
/steemhunt/blacklist.json ->
  [
    "user-c"
  ]

* Please separate each username with a new line so we can check the git change logs easily.
* Indentation: 2 spaces.
* Sort usernames by alphabetical order
```

## Signed up phone numbers

dApps may have their own phone verifications to prevent people from making multiple alt accounts using their discounted account creation interface. However, users can still make multiple alt accounts through different dApps because it's currently not possible for them to share the signed up user's numbers.

If we do simple existence checks on phone numbers across the services, it will not affect users privacy and no personal information will be leaked, so we can safely and securely stamp out multiple alt account abuse. Please implement API interface in the following way:

Example:
```
https://api.steemhunt.com/phone_numbers/exists.json?number=+821012345678&key=YOUR_API_KEY
-> { "exists": false }
```

To prevent brute-force attack and public access of potentially sensitive information, it's better to protect the end point using private API keys and only give access to authorized dApps.


#### *Caution*
`+` sign on the URL parameter is translated as a space character, so make sure you normalise it when you query the database

Example:
```
params[:number].gsub(/^[^+](.+)/, '+\\0').gsub(/[^+0-9]/, '')
```
