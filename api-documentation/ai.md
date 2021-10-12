---
description: 1Simple API to run AI as we love it!
---

# AI

### OCR API

{% swagger baseUrl="https://api.1saas.co" path="/v1/ocr" method="post" summary="OCR" %}
{% swagger-description %}
Post a request to the AI OCR Read Text in Picture endpoint. This endpoint is to read what is on the picture.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
ocr
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="imageUrl" type="string" %}
URL of the image you want to analyse.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{ 
	Detections: detections [...{}] 
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

Body:
{ 
"imageUrl": "url" 
} 
```



### Picture Recognition API

{% swagger baseUrl="https://api.1saas.co" path="/v1/pic" method="post" summary="PIC" %}
{% swagger-description %}
Post a request to the AI Picture Regconition endpoint to detect what is on a picture.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
pic
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="imageUrl" type="string" %}
URL of the image you want to analyse. 
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{	
	Concepts : concepts […{}] 
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

Body:
{ 
"imageUrl": "url" 
} 
```

### Entity detection API

{% swagger baseUrl="https://api.1saas.co" path="/v1/entity" method="post" summary="ENTITY" %}
{% swagger-description %}
Post a request to the ENTITY endpoint to detect the entities of a text.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
entity
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
Text you want to analyse.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{ 
	EntityResult: entityresults[…{}] 
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

Body:
{ 
"text": "Look at my horse, my horse is amazing." 
} 
```

### Mood Detection API

{% swagger baseUrl="https://api.1saas.co" path="/v1/mood" method="post" summary="MOOD" %}
{% swagger-description %}
Post a request to the mood endpoint to detect the mood of a text.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
mood
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
Text you want to analyse.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{ 
	SentimentResult: sentimenResult[...{}] 
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

Body:
{ 
"text": "I have a dream that one day this nation will rise up and live out the true meaning of its creed: We hold these truths to be self-evident, that all men are created equal." 
} 
```

### Email validation and correction

{% swagger baseUrl="https://api.1saas.co" path="/v1/email" method="post" summary="Email validation" %}
{% swagger-description %}
Post a request to the email endpoint to detect if the email is valid, if not we will try to fix the email. 

\




\


For example 1saas-iscool@gmail.co will be fixxed to 1saas-iscool@gmail.com
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
email
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="string" %}
The email you want to fix.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```javascript
{ 
		"email":"1saas-iscool@gmail.com" 
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

Body:
{ 
"email": "1saas-iscool@gaml.co" 
} 
```

### Translation API

{% swagger baseUrl="https://api.1saas.co" path="/v1/translate" method="post" summary="Translation" %}
{% swagger-description %}
Post a request to the trans endpoint to translate the text. We will detect the language automatically, you need to set the resulting language you wish.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
trans
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="resultLang" type="string" %}
en
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
The text you want to translate.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```javascript
{ 
		"result" : "My horse does not eat cucumber salad" 
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

Body:
{ 
"text": "Mein Pferd isst keinen Gurkensalat",
"resultLang": "en"
} 
```

### Language validation API

{% swagger baseUrl="https://api.1saas.co" path="/v1/lang" method="post" summary="Language Translation" %}
{% swagger-description %}
Post a request to the trans endpoint to Address Validation. We will detect the address automatically, and maybe correct it if needed.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
lang
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="string" %}
Simone is an amazing italian pizza hunter.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```javascript
{ 
		'result' : '1 Main Street, San Diego, CA, US' 
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

Body:
{ 
"text": "Simone is an amazing italian pizza hunter."
} 
```

