# NoCode Helper

### Scheduler and Posthook

This endpoint allows you to time and schedule a webhook to be executed.

{% swagger baseUrl="https://api.1saas.co" path="/v1/scheduler" method="post" summary="Scheduler" %}
{% swagger-description %}
Post a request to the Scheduler endpoint.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" required="true" %}
scheduler
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data" type="object" required="true" %}
JSON Object
{% endswagger-parameter %}

{% swagger-parameter in="body" name="webhook / httpendpoint" type="url" required="true" %}
The webhook URL you want to later trigger
{% endswagger-parameter %}

{% swagger-parameter in="body" name="intervalOptions" required="true" type="String/NR" %}
SEE BELOW for Examples \
\
Any:

&#x20;ISO 8601 or Linux Timestamp



CAREFUL - you need to send the Unixtimestamp as integer and the ISO 8601 as String
{% endswagger-parameter %}

{% swagger-parameter in="body" name="endDate" type="String/NR" %}
Any:

&#x20;ISO 8601 or Linux Timestamp



CAREFUL - you need to send the Unixtimestamp as integer and the ISO 8601 as String
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}

{% endswagger-response %}
{% endswagger %}

#### Request example One time execution:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

{
    "webhook":"https://somehookaddress.com/lkajsdlkajsdlk",
    "data": {
        "message": "Hello I will execute this once"
    },
    "intervalOptions": ["1639150351"]
    "endDate": "2022-01-05T15:32:31.984Z"
}
```

#### Request example multiple executions at a set time:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

{
    "webhook":"https://somehookaddress.com/lkajsdlkajsdlk",
    "data": {
        "message": "Hello lets time multiple hooks"
    },
    "intervalOptions": ["1639150351", "2021-12-10T15:32:31.984Z"]
    "endDate": "2022-01-05T15:32:31.984Z"
}
```

#### Request example to setup a cronjob:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

{
    "webhook":"https://somehookaddress.com/lkajsdlkajsdlk",
    "data": {
        "message": "Hello lets run this every minute"
    },
    "intervalOptions": "cronjob;* * * * *"
    "endDate": "2022-01-05T15:32:31.984Z"
}
```

{% hint style="info" %}
You can use the cron syntax find more here: [https://crontab.guru/](https://crontab.guru)
{% endhint %}

#### Request example to setup a timed post hook:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

{
    "webhook":"https://somehookaddress.com/lkajsdlkajsdlk",
    "data": {
        "message": "Hello lets run this every third week from now on"
    },
    "intervalOptions": "weeks;3"
    "endDate": "2022-01-05T15:32:31.984Z"
}
```

Valid options are:&#x20;

```javascript
hours
days
weeks
months
```

Some examples ex. : "hours;5"

```
hours: every X hours (X -> Options 2) Ex: hours;5 -> every 5 hours
days: every X days (X -> Options 2) Ex: days;2 -> every 2 days
weeks: every X weeks (X -> Options 2) Ex: weeks;1 -> every week
months: every X months (X -> Options 2) Ex: months;4 -> every 4 months
```

### Weekend checking and validating API

{% swagger baseUrl="https://api.1saas.co" path="/v1/weekend" method="post" summary="Weekend Checker" %}
{% swagger-description %}
Post a request to the WEEKEND endpoint. This endpoint is to check if the day is a weekend.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
weekend
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="date" type="string" %}
Send the date in following format mm/dd/yyyy.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="dateformat" type="string" %}
Define your dataformat if you want to use a different format. Default is mm/dd/yyyy.

\




\


You can try to use your own - take care it might not work with your format, have fun trying.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "isWeekend": false,
    "dayOfWeek": 1
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
"dateformat": "dd.mm.yyyy",
"date": "12/24/2030" 
} 
```

### National and Bank Holiday checking API

{% swagger baseUrl="https://api.1saas.co" path="/v1/holiday" method="post" summary="Holidays Checker" %}
{% swagger-description %}
Post a request to the holiday endpoint. This endpoint is to check if the day is a public holiday. Currently we support these countries and states https://github.com/commenthol/date-holidays#supported-countries-states-regions.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
holiday
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="year" type="string" %}
Define the year. For example "2040"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="state" type="string" %}
Define the state you want to check. For example "TX"
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="string" %}
Define your ISO 3166-2 country code. For example "US"
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
        "holidays": [
            {
                "date": "1970-01-01 00:00:00",
                "start": "1969-12-31T23:00:00.000Z",
                "end": "1970-01-01T23:00:00.000Z",
                "name": "Neujahr",
                "type": "public",
                "rule": "01-01"
            },
            ...
            
            {
                "date": "1970-12-31 14:00:00",
                "start": "1970-12-31T13:00:00.000Z",
                "end": "1970-12-31T23:00:00.000Z",
                "name": "Silvester",
                "type": "bank",
                "rule": "12-31 14:00 if sunday then 00:00"
            }
        ]
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
"countryCode": "US",
"state": "texas",
"year": "2040"
} 
```

### Advanced switching key and values API

{% swagger baseUrl="https://api.1saas.co" path="/v1/asw" method="post" summary="Advanced Switch" %}
{% swagger-description %}
Post a request to the asw where you want to switch a key against a JSON. Find an example here: https://gist.github.com/wemakefuture/5e58cc11cc017846ac3f2f357d28064f 

\




\


You can simply use an URL that hosts a JSON and define it as external, we will then switch the key against the value in the JSON. 

\




\


If you provide a JSON as internal you need to send the JSON via the API call. 
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
asw
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="external" type="boolean" %}
true
{% endswagger-parameter %}

{% swagger-parameter in="body" name="key" type="string" %}
Key you want to switch against you JSON.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="json" type="object" %}
Parameters key values you want to switch.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```javascript
{ 
    "value": "20"
}
```
{% endswagger-response %}
{% endswagger %}

Request example external JSON:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"external": true
"json": "https://gist.github.com/wemakefuture/5e58cc11cc017846ac3f2f357d28064f",
"key": "Austria"
} 
```

Request example internal JSON:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"external": false
"json": {
"Austria": 20,
"Belgium": 21,
"Bulgaria": 20,
"Croatia": 25,
"Cyprus": 19,
"Czechia": 21,
"Denmark": 25,
"Estonia": 20,
"Finland": 24,
"France": 20,
"Germany": 19,
"Greece": 24,
"Hungary": 27,
"Ireland": 23,
"Italy": 22,
"Latvia": 21,
"Lithuania": 21,
"Luxembourg": 17,
"Malta": 18,
"Netherlands": 21,
"Poland": 23,
"Portugal": 23,
"Romania": 19,
"Slovakia": 20,
"Slovenia": 22,
"Spain": 21,
"Sweden": 25
},
"key": "Austria"
} 
```

### Timezone converting API

{% swagger baseUrl="https://api.1saas.co" path="/v1/time" method="post" summary="Timezone Switch " %}
{% swagger-description %}
Post a request to the time endpoint. This endpoint is to check convert timezones around the globe. 
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
time
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="inputTime" type="string" %}
Convert the inputTime.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="inputTimeZone" type="string" %}
Define the inputTimeZone check timezones here https://www.iana.org/time-zones.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="destinationTimeZone" type="string" %}
Define your output Timezone.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{{ 
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
{​​​​​​
"inputTime": "21-06-2021 20:00",
"inputTimeZone": "America/New_York",
"destinationTimeZone" : "Europe/Berlin"
}​​​​​
```

### Expand shortened URL via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/esu" method="post" summary="Expand Shortened URL" %}
{% swagger-description %}
Post a request to the esu endpoint. This endpoint is to get the full url.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
esu
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
The short URL you want to get the full URL for.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```javascript
{
    "longUrl": "https://www.wemakefuture.com/services/integromat-expert-partner",
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
"url": "https://bit.ly/39a3av7",
} 
```

### Detect gender name via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/gnd" method="post" summary="Gendername detection" %}
{% swagger-description %}
Post a request to the gnd endpoint. This endpoint is to get the gender of a firstname.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
gnd
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="firstname" type="string" %}
The firstnames gender you want to verify.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```javascript
{
    "longUrl": "https://www.wemakefuture.com/services/integromat-expert-partner",
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
"firstname": "Petr",
} 
```

### Nation to ISO switch

{% swagger baseUrl="https://api.1saas.co" path="/v1/nation-iso" method="post" summary="Nation ISO Matchdown" %}
{% swagger-description %}
Post a request to the Nation ISO Matchdown endpoint. This endpoint is to switch either ISO to Nation or Nation to ISO Alpha3166 Code.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
nation-iso
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="name" type="string" %}
Send the country name. OR
{% endswagger-parameter %}

{% swagger-parameter in="body" name="iso" type="string" %}
Sent the ISO Code and get the country back.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
If you send a name:

{
    "ISO": "US"
}


If you send a ISO:

{
    "nation": "Spain"
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="info" %}
Post either Name (country name) OR ISO Code.&#x20;
{% endhint %}

Request example Name:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"name": "United States"
} 
```

Request example ISO:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"iso": "es"
} 
```

### IP to GEO location API

{% swagger baseUrl="https://api.1saas.co" path="/v1/iptogeo" method="post" summary="IP to GEO (City)" %}
{% swagger-description %}
Post a request to the iptogeo validation and city checkup endpoint. This endpoint is to check if the ip is valid, located close to you or within your accepted user range.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
iptogeo
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ip" type="string" %}
The IP address you want to verfiy.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "status": "success",
    "country": "Germany",
    "countryCode": "DE",
    "region": "HE",
    "regionName": "Hesse",
    "city": "Frankfurt",
    "zip": "23232",
    "lat": 50.518,
    "lon": 8.8172,
    "timezone": "Europe/Berlin",
    "isp": "Deutsche Telekom AG",
    "org": "Deutsche Telekom AG",
    "as": "AS3320 Deutsche Telekom AG",
    "query": "89.89.200.199"
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
"ip": "89.89.200.199",
} 
```

### Calculate BMI via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/bmi" method="post" summary="BMI Calculator" %}
{% swagger-description %}
Post a request to the BMI endpoint. This endpoint is to check if you are 🥦.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
bmi
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="height" type="string" %}
The height in CM.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="weight" type="string" %}
The weight in KG.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    bmi: 21.97,
    bmiClassification: "normal",
    dbw: 61.20,
    kcal: 1836,
    nutrients: {
       carbohydrates: 275.40, 
       protein: 68.85, 
       fat: 51.00
    }
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
"height": "185",
"weight": "89"
}
```

### Parse UTM Parameters via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/utm" method="post" summary="UTM Parameters" %}
{% swagger-description %}
Post a request to the UTM endpoint. This endpoint is to retrieve the UTM parameters from a URL.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
utm
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" type="string" %}
The URL you want to analyze.
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
    "url": {
        "utm_source": "active%20users",
        "utm_medium": "email",
        "utm_campaign": "feature%20launch",
        "utm_term": "termsarelong",
        "utm_content": "bottom%20cta%20button"
    }
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
"url": "www.yoursite.com/pricing?utm_source=active%20users&utm_medium=email&utm_campaign=feature%20launch&utm_content=bottom%20cta%20button"
}
```

### VAT validation via API

{% swagger baseUrl="https://api.1saas.co" path="/v1/vatcheck" method="post" summary="VAT ID Checker" %}
{% swagger-description %}
Post a request to the VATCheck endpoint. This endpoint is to check if the VAT Nr is valid.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="string" %}
vatcheck
{% endswagger-parameter %}

{% swagger-parameter in="header" name="auth" type="string" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="vatID" type="string" %}
IE98765343
{% endswagger-parameter %}

{% swagger-parameter in="body" name="countryCode" type="string" %}
IE
{% endswagger-parameter %}

{% swagger-parameter in="body" name="ID" type="string" %}
98765343
{% endswagger-parameter %}

{% swagger-response status="200" description="Works." %}
```
{
  countryCode: 'xx',
  vatNumber: 'xxxxxxxxx',
  requestDate: '2013-11-22+01:00',
  valid: true,
  name: 'company name',
  address: 'company address'
}
```
{% endswagger-response %}
{% endswagger %}

{% hint style="danger" %}
Disclaimer: YOU ACT ON YOUR OWN RISK - This is no tax consultation and only provided via the [https://ec.europa.eu/taxation\_customs/vies/checkVatService.wsdl](https://ec.europa.eu/taxation\_customs/vies/checkVatService.wsdl) service. You  are responsible for any harms to your or your business and you cannot claim any charges!
{% endhint %}

Request example:

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"vatID": "IE98765343"
}

OR 

{ 
"countryCode": "IE",
"ID":"98765343"
}
```

## Store JSON Data via API

{% swagger method="post" path="/v1/json" baseUrl="https://api.1saas.co" summary="JSON Bin" %}
{% swagger-description %}
Post a request to the json endpoint. This endpoint is to store json data online. U can update, get and delete it.
{% endswagger-description %}

{% swagger-parameter in="body" name="json" type="JSON" %}
data to store
{% endswagger-parameter %}

{% swagger-parameter in="body" name="binId" type="String" %}
id of the bin where data is stored
{% endswagger-parameter %}

{% swagger-parameter in="body" name="update" type="Boolean" %}
true when updating an existing bin
{% endswagger-parameter %}

{% swagger-parameter in="body" name="delete" type="Boolean" %}
true when deleting an existing bin
{% endswagger-parameter %}

{% swagger-parameter in="path" name="endpoint" type="String" required="false" %}
json
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Works." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Request Example Create JSON Bin

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"json": {
        "example": "data"
        }
}
```

#### Request Example Update JSON Bin

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
"binId": "YOUR-BIN-ID",
"json": {
        "example": "data"
        },
"update": true
}
```

#### Request Example Delete JSON Bin

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{ 
"binId": "YOUR-BIN-ID"
}
```

#### Request Example List all JSON Bins

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:{}
```

## Save variables online via API

{% swagger method="post" path="/v1/globalVariable" baseUrl="https://api.1saas.co" summary="Global Variable" %}
{% swagger-description %}
Post a request to the globalVariable endpoint. This endpoint is to store a variable of any datatype online. U can update, get, list and delete variables
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="String" %}
globalVariable
{% endswagger-parameter %}

{% swagger-parameter in="body" name="variable" type="String" required="true" %}
name of the stored variable
{% endswagger-parameter %}

{% swagger-parameter in="body" name="value" type="Any" %}
value to be stored in variable
{% endswagger-parameter %}

{% swagger-parameter in="body" name="update" type="Boolean" %}
true, when updating an existing variable
{% endswagger-parameter %}

{% swagger-parameter in="body" name="delete" type="Boolean" %}
true, when deleting an existing variable
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Works." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}



#### Request Example Create Global Variable

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
"variable": "YOUR-VARIABLE-NAME",
"value": "ANY-VALUE"
}
```

#### Request Example Update Global Variable

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
"variable": "YOUR-VARIABLE-NAME",
"value": "ANY-VALUE"
"update": true
}
```

#### Request Example Delete Global Variable

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
"variable": "YOUR-VARIABLE-NAME",
"delete": true
}
```

#### Request Example Get Global Variable

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
"variable": "YOUR-VARIABLE-NAME"
}
```

#### Request Example List Global Variables

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:{}
```

####

## Verify Emails by calling an API

{% swagger method="post" path="/v1/emailVerifier" baseUrl="http://api.1saas.co" summary="Email Verifier" %}
{% swagger-description %}
Post a request to the emailVerifier endpoint. This endpoint is to check if a mail is fake, free etc.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="String" %}
emailVerifier
{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" type="String" %}
email to verify and check
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Works." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Request Example

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
"email": "youremail@verify.com"
}
```

## Shorten your URL&#x20;

{% swagger method="post" path="/v1/url" baseUrl="https://api.1saas.co" summary="URL-Shortener" %}
{% swagger-description %}
shorten your URL with the API.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="String" %}
url
{% endswagger-parameter %}

{% swagger-parameter in="body" name="identifier" type="String" %}
the identifier of the shortend Url
{% endswagger-parameter %}

{% swagger-parameter in="body" name="destination" type="String" %}
the destination Url of the shortened Url
{% endswagger-parameter %}

{% swagger-parameter in="body" name="update" type="String" %}
boolean, true if you want to update a destination
{% endswagger-parameter %}

{% swagger-parameter in="body" name="delete" type="String" %}
boolean, true if you want to delete a url
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Works." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Request Example Create&#x20;

```javascript
Header:
{
"auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
"destination": "https://1saas.co"
}
```

#### Request Example Update

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "destination": "https://1saas.co",
    "update": true,
    "identifier": "YOUR-IDENTIFIER"
}
```

#### Request Example List All

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:{}
```

#### Request Example Delete

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "identifier": "6fhF436F",
    "delete": true
}
```

## Next Gen Replacer



{% swagger method="post" path="/replacer" baseUrl="https://api.1saas.co/v1" summary="Replacer" %}
{% swagger-description %}
The replacer allows you define an object with values to replace and the new value. You can replace any kind of value.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="String" %}
replacer
{% endswagger-parameter %}

{% swagger-parameter in="path" name="replaceItems" type="Object" %}
the object with the items to replace, and the new values
{% endswagger-parameter %}

{% swagger-parameter in="path" name="data" type="Array" %}
the data you want to replace, can be an array, object, int
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Works." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Request Example

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "data": [
        "Test1",
        {
            "TestKey": "Test2"
        }
    ],
    
    "replaceItems": {
        "key1": {
            "oldValue": "Test1",
            "newValue": "newValue1"
        },
        "key2": {
            "oldValue": "Test2",
            "newValue": "newValue2"
        }
    }
}
```

## QR Code Generator / Reader

{% swagger method="post" path="/QR" baseUrl="https://api.1saas.co/v1" summary="QR Code" %}
{% swagger-description %}
With this endpoint is able to create a QR-Code with given Data. You can read data from a given QR-Code.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="String" %}
QR
{% endswagger-parameter %}

{% swagger-parameter in="path" name="imageUrl" type="String" %}
the imageUrl with from the QR-Code you want to read the data of
{% endswagger-parameter %}

{% swagger-parameter in="path" name="data" type="String" %}
the data you want the QR-Code to hide
{% endswagger-parameter %}
{% endswagger %}

#### Request Example Read from URL

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "imageUrl": "URL-TO-IMAGE"
}
```

#### Request Example Create with data

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "data": "TEXT TO FOR THE QR-CODE"
}
```

## Calendar Week

{% swagger method="post" path="/v1/calweek" baseUrl="https://api.1saas.co" summary="Calendar Week" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="String" %}
calweek
{% endswagger-parameter %}

{% swagger-parameter in="body" name="unixTimestamp" type="Timestamp" %}
a Timestamp
{% endswagger-parameter %}

{% swagger-parameter in="body" name="data" type="Data" %}
a Data
{% endswagger-parameter %}

{% swagger-parameter in="body" name="weekNumber" type="Integer" %}
number of the week from year
{% endswagger-parameter %}

{% swagger-parameter in="body" name="year" type="Integer" %}
a year 
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Works." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### Request Example Current week

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:{}
```

#### Request Example Week number

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "weekNumber": 1
}
```

#### Request Example Week number and Year

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "weekNumber": 1,
    "year": 2021
}
```

#### Request Example Unix Timestamp

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "unixTimestamp": 1636815236
}
```

#### Request Example Date

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "date": "04 Dec 1995 00:12:00 GMT"
}
```

## Hash, Encrypt and Decrypt with our API

{% swagger method="post" path="/crypto" baseUrl="https://api.1saas.co/v1" summary="Crypto" %}
{% swagger-description %}
With crypto you are able to hash text with a secret key. Encrypt text and also decrypt text that is already encrypted.
{% endswagger-description %}

{% swagger-parameter in="path" name="endpoint" type="String" %}
crypto
{% endswagger-parameter %}

{% swagger-parameter in="body" name="encrypt" type="Boolean" %}
true when you want to encrypt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="decrypt" type="Boolean" %}
true when yo want to decrypt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="cryptoType" type="String" %}
type for encrypting or of the encrypted text
{% endswagger-parameter %}

{% swagger-parameter in="body" name="hash" type="Boolean" %}
true when you want to hash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="hashType" type="String" %}
hashing type
{% endswagger-parameter %}

{% swagger-parameter in="body" name="text" type="String" %}
text to encrypt or hash
{% endswagger-parameter %}

{% swagger-parameter in="body" name="encryptedText" type="String" %}
encrypted text you want to decrypt
{% endswagger-parameter %}

{% swagger-parameter in="body" name="secretKey" type="String" %}
key you want to use for hashing or encrypting
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Works." %}
```javascript
{
    // Response
}
```
{% endswagger-response %}
{% endswagger %}

#### HASH:

for HMAC add Hmac in front of the hash function e.g HmacMD5

* **MD5**
* **SHA1**
* **SHA3**
* **SHA256**
* **SHA224**
* **SHA384**
* **SHA512**
* **RIPEMD160**

#### CRYPTO

* **AES**
* **DES**
* **TripleDES**
* **Rabbit**
* **RC4**
* **RC4Drop**

#### Request Example: Hash a Text

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "hash": true,
    "text": "YOUR-TEXT",
    "secretKey": "YOUR-SECRET-KEY",
    "hashType": "ANY-TYPE-FROM-HASH-LIST"
}
```

#### Request Example: Encrypt a Text

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "encrypt": true,
    "text": "YOUR-TEXT",
    "secretKey": "YOUR-SECRET-KEY",
    "cryptoType": "ANY-TYPE-FROM-CRYPTO-LIST"
}
```

#### Request Example: Decrypt a Text

```javascript
Header:
{
    "auth": "97ab95b4-ca9c-****-****-9c1bfcd0****"
}

Body:
{
    "decrypt": true,
    "encryptedText": "YOUR-ENCRYPTED-TEXT",
    "secretKey": "YOUR-SECRET-KEY",
    "cryptoType": "THE-TYPE-USED-FOR-ENCRYPTION"
}
```

##

##



