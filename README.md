# khuxbot.com API Documentation
API documentation for the most recent version of khuxbot

## Version 2
Version 1 of the API is depreciated and will no longer be supported/updated.

# Usage

The endpoint for retrieving data is:
    `https://www.khuxbot.com/api/v2/get`

It is recommended you change the content type header to json with
    Content-Type: application/json

The `post` request body must be in JSON. The following paragraths will outline which fields can be used

# Filter
You can specify how to filter the data to your liking.

Example: `{filter:{"hits":8,"direction":"upright"}}`

You can find a full list of filters [here](https://www.khuxbot.com/api/docs/filters)

## Integer Filtering

It should also be noted that all keys which accept integer values also accept a min and max key object

Example `{"filter":{"hits":{"max":3}}`

This will retrieve all medals which deal at most 3 hits

**Min and Max are Inclusive**

If you use  `{"min":3, "max":4}` it will return all medals which are 3 or 4 in value

# Format
You can change which fields you want returend by adding the format key. The value must be an array of strings

Example: `{"format":["name", "direction", "rarity"]}`

# Buff

You can also filter by which buff each medal provides

The buff value must be an object with either the "include" key or "exclude" key (or both)

You can find a full list of buff names [here](https://www.khuxbot.com/api/docs/buffs)

# Dynamic Spriteshets

The API now supports the generation of dynamic spritesheets which depend on which query you use.

By adding the {"type":"spritesheet"} key to the object, the server will create a custom spritesheet depending on which medals were returned.

The first time you run your query, it may take some time (Tests determine about 1-2 minutes for 200 medals) but later queries will be milliseconds.
