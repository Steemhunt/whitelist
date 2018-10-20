# Steemhunt Whitelist and Blacklist

## Whitelist

The Steemhunt whitelist includes users whose user score is at least 1.0 or above. The user score is decided by the following formula:
```
Score = Credibility Score *  Activity Score * Curation Score * Hunter Score
```

1. Credibility Score
This score represents the trustworthiness of the account. It’s calculated by combining:
  a. Steem reputation
  b. Steem power
  c. Account age (based on the date you signed up to Steemhunt)
  d. [Buildawhale blacklist](https://github.com/themarkymark-steem/buildawhaleblacklist) - an external blacklisted user database

2. Activity Score
This shows how much the user actively uses Steemhunt.

3. Curation Score
This reflects how well the user upvotes hunting posts in an adding-value way. It can be increased if the user has upvoted many different users as this will increase their diversity score  Or it can be decreased if a user is considered to be a circle voter (involved in a voting ring).


4. Hunter Score
This score represents how many valuable hunts the user has posted. It’s calculated based on:
  a. The average rank of the users hunt post
  b. The amount of penalty points a user has (users receive penalty points each time their hunt post is delisted by our community moderators)

## Blacklist
We blacklist users for 30 days if the user attempts any of the following actions:

1. Operates alternative accounts to disrupt Steemhunt voting pool, its ranking chart, and HUNT token airdrops
2. Creates spam posts or comments
3. Commits Plagiarism

## Signed up phone numbers
```
https://api.steemhunt.com/phone_numbers/exists.json?number=+821012345678&key=API_KEY
-> { "exists": false }
```

Please request an API key via [email](steemhunt@gmail.com) or [Discord](https://discord.gg/uekggj6) if your dApp wants an access.
