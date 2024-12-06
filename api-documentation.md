---
icon: book-blank
description: Up-to-date API Documentation of 0CodeKit.
---

# API Documentation

## Remarks

Previous documentation on Postman can still be found [here](https://documenter.getpostman.com/view/18297710/UVkntwBv) but is no longer maintained.

## Base URL

`https://prod.0codekit.com`

## Authentication

Include a key:value pair in the header of the request, where the key is `auth` and the value your API key that can be obtained in [your 0CodeKit account portal](https://www.0codekit.com/).

For example: `auth:a4c3dcc5-8e41-4cad-bd5f-c24086baba00`

## Functions

{% swagger src=".gitbook/assets/api.json" path="/ai/advancedocr" method="post" %}
[api.json](.gitbook/assets/api.json)
{% endswagger %}

{% swagger src=".gitbook/assets/docs.json" path="/ai/extract-from-text" method="post" %}
[docs.json](.gitbook/assets/docs.json)
{% endswagger %}

{% swagger src=".gitbook/assets/docs.json" path="/ai/fuzzy-match" method="post" %}
[docs.json](.gitbook/assets/docs.json)
{% endswagger %}

{% swagger src=".gitbook/assets/docs.json" path="/ai/redact-pdf" method="post" %}
[docs.json](.gitbook/assets/docs.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/detectadultcontent" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/picturetextrecognition" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/entitydetection" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/removebg" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/detectbrand" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/generatepythoncode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/detectcolor" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/toolongtoread" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/languagedetection" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/transcribe" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/pictureobjectrecognition" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/generateimage" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/extractcontactinformation" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/generatejavascriptcode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/mooddetection" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/detectface" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/detectemailtype" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/pdfocr" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/checkcontentpolicy" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/ai/translate" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/crypto/hash" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/crypto/decrypt" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/crypto/encrypt" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/calculate/geodistance-v2" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/calculate/bmi" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/gender" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/user/retrievecredits" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/duplicate" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/parseurlquery" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/logo" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/thumbnail" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/advancedswitch" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/api.json" path="/operator/trafficlight" method="post" %}
[api.json](.gitbook/assets/api.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/splitname" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/urlexpander" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/utm/build" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/utm/parse" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/operator/htmlparser/get" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/docs (1).json" path="/operator/merge-video-audio" method="post" %}
[docs (1).json](<.gitbook/assets/docs (1).json>)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/convert/nationiso" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/convert/msgtojson" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/convert/currency" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/convert/iptogeo" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/convert/csv/json" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/convert/csv/array" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/lookupvatrates" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/isfreemail" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/validate/geolocation" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/validate/phonenumber" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/validate/iban" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/validate/vat" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/validate/bic" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/business/verify/domain" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/docs (1).json" path="/business/facturx/validate" method="post" %}
[docs (1).json](<.gitbook/assets/docs (1).json>)
{% endswagger %}

{% swagger src=".gitbook/assets/docs (1).json" path="/business/facturx/embed" method="post" %}
[docs (1).json](<.gitbook/assets/docs (1).json>)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/temp" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/perm/del" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/perm/get" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/perm/list" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/perm/add" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/globalvariables/del" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/globalvariables/update" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/globalvariables/get" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/globalvariables/list" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/globalvariables/add" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/json/del" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/json/put" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/json/get" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/json/list" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/storage/json/add" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/dateandtime/calendarweek" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/dateandtime/isweekend" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/dateandtime/switchtimezone" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/dateandtime/holidays" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/dateandtime/detailperiod" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/dateandtime/month" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/1saas/auth" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/city" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/number" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/string" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/name" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/color" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/mockdata/user" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/html-scrape" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/jsonwebtoken/encode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/jsonwebtoken/decode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/qrcode/encode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/qrcode/decode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/barcode/decode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/generate/barcode/encode" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/text/regex" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/text/contains" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/text/comparestring" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/text/extractor" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/python" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% hint style="warning" %}
**Note on the Asynchronous Python Code Executor Pricing**

The cost of the asynchronous Python code executor is proportional to that of the regular synchronous Python executor. The key difference is that the asynchronous endpoint allows your code to run up to **5 times longer**, with a maximum total runtime of **15 minutes**.

* Charges are applied every **3 minutes**, which is the standard execution time increment for the synchronous Python executor.
* You are charged for each 3-minute interval (or part thereof) that your code runs asynchronously.
{% endhint %}

{% swagger src=".gitbook/assets/openapi.json" path="/async-python" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/javascript" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/taskstatus" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/chart/bars" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/chart/doughnut" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/chart/line" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/blur" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/convert" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/exif" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/crop" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/flip" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/html" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/overlay" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/resize" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/rotate" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/image/sharpen" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/draw/image" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/draw/text" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/metadata/edit" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/metadata/info" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/pages/add" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/pages/remove" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/pages/resize" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/pages/rotate" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/base64" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/compress" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/count" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/decrypt" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/create" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/docx-to-pdf" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/encrypt" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/getinfometadata" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/html" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/markdownstringtopdf" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/merge" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/pdf-to-image" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/pdf/split" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/add" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/del" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/list" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/get" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

{% swagger src=".gitbook/assets/openapi.json" path="/put" method="post" %}
[openapi.json](.gitbook/assets/openapi.json)
{% endswagger %}

