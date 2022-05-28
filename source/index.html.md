---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Chattr API
---

# Introduction

Welcome to the Chattr. You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.

We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

This example API documentation page was created with [Slate](https://github.com/slatedocs/slate). Feel free to edit it and use it as a base for your own API's documentation.

# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Trends

# Sentiment

## Get Current Stock Sentiment

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens" \
  -H "Authorization: meowmeowmeow"
```

```javascript
const axios = require("axios");

const options = {
  method: 'GET',
  url: 'http://api.chattr.dev/v1/getCurrentStockSentiment',
  params: {
    ticker: 'AAPL'
  },
  headers: {
    'X-RapidAPI-Host': 'alpha-vantage.p.rapidapi.com',
    'X-RapidAPI-Key': 'a343082d11msh0dfdaf5c982bb8ap17135fjsnf1c70dc0e0c4'
  }
};

axios.request(options).then(function (response) {
	console.log(response.data);
}).catch(function (error) {
	console.error(error);
});
```

> The above command returns JSON structured like this:

```json
{
	"latestSentiment": {
		"_id": "62914f5e001f7dbda12365a8",
		"ticker": "aapl",
		"sentiment": 1.7692307692307692,
		"numComments": 13,
		"timestamp": 1653690206
	}
}
```

This endpoint returns the latest sentiment for a specified stock.

### HTTP Request

`GET http://api.chattr.dev/v1/getCurrentStockSentiment`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
ticker | N/A | The ticker associated with the company/currency you would like to query. Example: 'AAPL'

<aside class="notice">
<code>ticker</code> is a required parameter!
</aside>

# Companies

## Get Supported Companies

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2" \
  -X DELETE \
  -H "Authorization: meowmeowmeow"
```

```javascript
const axios = require("axios");

const options = {
  method: 'GET',
  url: 'http://api.chattr.dev/v1/companies/getSupportedCompanies',
  headers: {
    'X-RapidAPI-Host': 'alpha-vantage.p.rapidapi.com',
    'X-RapidAPI-Key': 'a343082d11msh0dfdaf5c982bb8ap17135fjsnf1c70dc0e0c4'
  }
};

axios.request(options).then(function (response) {
	console.log(response.data);
}).catch(function (error) {
	console.error(error);
});
```

> The above command returns JSON structured like this:

```json
{
	"supportedCompanies": [
		"hood",
		"goog",
		"meta",
		"twtr",
		"shop",
    "..."
	]
}
```

Retrieve a list of 

### HTTP Request

`GET http://api.chattr.dev/v1/companies/getSupportedCompanies`

### URL Parameters

Parameter | Description
--------- | -----------
N/A | N/A

# Currencies