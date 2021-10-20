---
description: Execute code without any hassle.
---

# Code

### Run Javascript via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/js" method="post" summary=".js Javascript" %}
{% swagger-description %}
Post a request with a code snippet to the Javascript endpoint.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
js
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="string" %}
Your javascript code.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```javascript
{ 
    "data" : "3618"
} 
```
{% endswagger-response %}
{% endswagger %}

{% hint style="success" %}
You can find the currently supported packages for our js endpoint [**here**](https://gist.github.com/wemakefuture/362d925f199e8828d575628ab896b60f#file-packages-npm-1saas-co).

Need more modules (NPM modules)? Write us here: [beta1saas@1saas.co](mailto:beta1saas@1saas.co)
{% endhint %}

Here you can find some code examples:&#x20;

{% embed url="https://gist.github.com/wemakefuture/f8c760a822848d516c65815eb7e183ad" %}

Request example:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"code": "function multiplyNumbers(number1, number2){ var calculation = number1 * number2; result = {'data': calculation}; } multiplyNumbers(54, 67);" 
} 
```

## Run Python via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/py" method="post" summary=".py Python" %}
{% swagger-description %}
Post a request with a code snippet to the Python endpoint.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
py
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="code" type="string" %}
The Python code you want to execute.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "result": 13
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
result = { "data": YOURVARIABLE }

We will return the result in the JSON \
{ "data": YOURVARIABLE }

So please insert this at the end of your code!
{% endhint %}

Here you can find some examples:&#x20;

{% embed url="https://gist.github.com/wemakefuture/55608487840505d3e5aa195919aa3836" %}
Some Python Examples
{% endembed %}

{% hint style="success" %}
You can simply import nearly all pip3 modules - just try it out. Just put as you are used to the module in the first lines of you python3 code.
{% endhint %}

Request example:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"code": "a = 6 b = 7 c = a + b result = { 'data': c }" 
} 
```
