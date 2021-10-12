---
description: You will not believe how random this world can be.
---

# Random

### Random Number API 

{% swagger baseUrl="https://api.1saas.co" path="/v1/nr" method="post" summary="Number" %}
{% swagger-description %}
Post a request to the number endpoint. This endpoint will return you a random number within a defined range.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
nr
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="range" type="string" %}
Define the range in which between the random number should be. Comma seperated "BEGINNING,END"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" %}
Integer, Decimal (if decimal we will always return 2 nr behind the dot).

\


Default is integer. 
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "number": "12.03"
}
```
{% endswagger-response %}
{% endswagger %}

Request example

Request example:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"range": "10,90",
"type": "decimal",
} 
```

### Get random String via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/string" method="post" summary="String" %}
{% swagger-description %}
Post a request to the string endpoint. This endpoint will return you a random string within a defined length.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
string
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="type" type="string" %}
1 = only numbers 

\


2 = numbers + letters, 

\


3 = numbers + capital letters + letters

\


4 = numbers + capital letters + letters + specialchars

\




\


Default is option 4
{% endswagger-parameter %}

{% swagger-parameter in="body" name="leng" type="integer" %}
Define how many chars your number should have. 
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "string": "JafIN!sw*I"
}
```
{% endswagger-response %}
{% endswagger %}

RequestName e:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"type": "4",
"leng": 10
} 
```

### Get random Name Request example

{% swagger baseUrl="https://api.1saas.co" path="/v1/name" method="post" summary="Name" %}
{% swagger-description %}
Post a request to the name endpoint. This endpoint will return you a random name.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
nr
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "name": "Petr"
}
```
{% endswagger-response %}
{% endswagger %}

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"name": "Simo"
} 
```

### Get a random City via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/city" method="post" summary="City" %}
{% swagger-description %}
Post a request to the city endpoint. This endpoint will return you a random city from planet earth.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
city
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "city": "New York City"
}
```
{% endswagger-response %}
{% endswagger %}

Request example:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}
```

