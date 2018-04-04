# khuxbot.com API Documentation
API documentation for the most recent version of khuxbot

## Version 2
Version 1 of the API is depreciated and will no longer be supported/updated.

# Usage

The endpoint for retrieving data is:
    https://www.khuxbot.com/api/v2/get

It is recommended you change the content type header to json with
    Content-Type: application/json

The `post` request body must be in JSON. The following paragraths will outline which fields can be used


# Filter
Example: `{filter:{"hits":8,"direction":"upright"}}`

You can find a full list of filters [here](https://www.khuxbot.com/api/docs/filters)

# Format
You can change which fields you want returend by adding the format key. The value must be an array of strings

Example: `{"format":["name", "direction", "rarity"]}`

# Buff

You can also filter by which buff each medal provides

The buff value must be an object with either the "include" key or "exclude" key (or both)

You can find a full list of buff names [here](https://www.khuxbot.com/api/docs/buffs)
