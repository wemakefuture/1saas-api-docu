---
description: API Documenation for 1SaaS.co
---

# API Documentation

### Overview of the API endpoints

Here you can find the API for 1SaaS.co currently we support the following endpoints.

| **AI**                                | **Code**   | **NoCode**                                       | **Random** | **Files**   |
| ------------------------------------- | ---------- | ------------------------------------------------ | ---------- | ----------- |
| Picture content detection (pic)       | Javascript | Weekend                                          | Number     | Files       |
| OCR from pictures (ocr)               | Python     | Holiday                                          | String     | Temp Files  |
| Entities from text detection (entity) |            | IP to GEO Location                               | Name       | PDF Merger  |
| Mood from text detection (mood)       |            | Advanced Switch                                  | City       | HTML to PDF |
| Email Validation (email)              |            | Timezone Switcher                                |            |             |
| Translation (translate)               |            | Expand Shortend URL                              |            |             |
| Language Validation / Detection       |            | <p>E-Mail Validation</p><p>&#x26; Correction</p> |            |             |
|                                       |            | Gender Name Detection                            |            |             |
|                                       |            | Nation ISO Matchdown                             |            |             |
|                                       |            | BMI Calculator                                   |            |             |
|                                       |            | UTM Parameters from URL                          |            |             |
|                                       |            | VAT and ID Checker                               |            |             |
|                                       |            | JSON Bin                                         |            |             |
|                                       |            | Save global Variabels                            |            |             |

{% swagger baseUrl="https://api.1saas.co" path="/v1/" method="post" summary="Post Auth" %}
{% swagger-description %}
This endpoint allows you to auth your self. You should allways pass the auth in every call to your specific endpoint.
{% endswagger-description %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and receive a 200, 302 or 401.
{% endswagger-parameter %}

{% swagger-response status="200" description="Auth successfully retrieved." %}
```
{
    "auth": true,
    "executions": 12
}
```
{% endswagger-response %}

{% swagger-response status="401" description="If your API key is invalid" %}
```
{
    "auth": false
}
```
{% endswagger-response %}

{% swagger-response status="402" description="If you ran out of executions" %}
```
{
    "auth": true,
    "message": "You ran out of executions",
    "executions": 0
}
```
{% endswagger-response %}
{% endswagger %}
