# unbelievaboat.py
Unbelievaboat API for python

# Docs
## Getting started
1. Download unbelievaboat.py
2. Enter this code into your discord.py bot
```python
from unbelievaboat import client
unbclient = client(API_TOKEN)
```
## API functions
### get_user_bal(*string: guild_id, string: user_id*)
Gets the users balance

Returns: `{"rank": string: rank, "user_id": string: user_id, "cash": integer: cash_balance, "bank": integer: bank_balance, "total": integer: cash + bank}`
### set_user_bal(*string: guild_id, string: user_id, integer: cash=0, integer: bank=0, string: reason=None*)
Sets the users balance

Returns: `{"user_id": string: user_id, "cash": integer: cash_balance, "bank": integer: bank_balance, "total": integer: cash + bank}`
### change_user_bal(*string: guild_id, string: user_id, integer: cash=0, integer: bank=0, string: reason=None*)
Changes user balance

Negative cash and bank values supported

Returns: `{"user_id": string: user_id, "cash": integer: cash_balance, "bank": integer: bank_balance, "total": integer: cash + bank}`
### get_leaderboard(*string: guild_id, string: sort='total', string: limit=None, string: offset='1', string: page=None*)
Gets the guild leaderboard

sort and offset CANNOT be None

Returns list of `get_user_bal()` outputs
### get_guild(*string: guild_id*)
Gets info about a guild

Returns: `{"id": string: guild_id, "name": string: guild_name, "icon": string: icon_hash, "owner_id": string: guild_owner_id, "member_count": integer: num_of_members, "symbol": string: unbelievaboat_currency_symbol}`
### get_app_perms(*string: guild_id*)
Gets permissions for a guild

Returns 1 if you have permission and 0 if you dont
## Exceptions
### invalidData
The data you submitted is invalid, try again with valid data
### invalidPermissions
Your API token is invalid, or you do not have permission to edit economy on this guild
### internetForbidden
You do not have permission to access this URL, are you sure you entered in the right data?
### unexpectedURL
This URL doesnt exist, are you sure you entered in the right data?
### requestOverload
You are sending too many requests, too quickly
### serverError
Unbelievaboat server error. try again later
