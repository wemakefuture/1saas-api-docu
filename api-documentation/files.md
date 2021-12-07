---
description: Everything regarding files
---

# Files

### Files

Our "files" endpoint allows you to permanently store files up to 10MB and reuse them in workflows and scenarios.

{% swagger method="post" path="/v1/files" baseUrl="https://api.1saas.co" summary="Upload a file" %}
{% swagger-description %}
Uploads a file either from a url or as a buffer
{% endswagger-description %}

{% swagger-parameter in="header" name="auth" type="String" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileURL" type="String" required="false" %}
Public accessable file urll
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileBuffer" type="Buffer" %}
File buffer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="uploadName" type="String" %}
If you upload a buffer, you can define a file name
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Your file was uploaded successfully" %}
```javascript
{
    "message": "File Upload successfully",
    "fileID": "YOURFILEID",
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="/v1/files" baseUrl="https://api.1saas.co" summary="Download a file" %}
{% swagger-description %}
You can download a file by file name
{% endswagger-description %}

{% swagger-parameter in="header" name="auth" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileName" %}
Your file name. To get all your saved files, you can use the API Method described down below
{% endswagger-parameter %}

{% swagger-parameter in="body" type="boolean" name="getAsUrl" %}
Get the file as a temporary url (24 hours)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Response with a standard buffer" %}

{% endswagger-response %}

{% swagger-response status="200: OK" description="Response with a JSON containing the url" %}
```javascript
{
    "url": "FILEURL"
}
```
{% endswagger-response %}
{% endswagger %}

{% swagger method="get" path="/v1/files" baseUrl="https://api.1saas.co" summary="List all saved files" %}
{% swagger-description %}
Get a list of all your file names in an array
{% endswagger-description %}

{% swagger-parameter in="header" name="auth" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Success" %}
```javascript
{
    "files": ["FILE1", "FILE2", ...]
}
```
{% endswagger-response %}
{% endswagger %}

### Temp Files

{% swagger method="post" path="/v1/tempfiles" baseUrl="https://api.1saas.co" summary="Upload a buffer and returns a temporary file url " %}
{% swagger-description %}
Works best in combination with our other api's
{% endswagger-description %}

{% swagger-parameter in="header" name="auth" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="buffer" type="Buffer" required="true" %}
The buffer you want to upload
{% endswagger-parameter %}

{% swagger-parameter in="body" name="fileName" %}
Optional file name
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="You successfully uploaded a file" %}
```javascript
{
     "message": 'File Upload successfully',
     "url": "FILEURL"
}
```
{% endswagger-response %}
{% endswagger %}

### PDF Merger

{% swagger method="post" path="/v1/pdfmerger" baseUrl="https://api.1saas.co" summary="Merges multiple pdf files to a single pdf" %}
{% swagger-description %}
You can merge files from url's or buffer's and define pages you want to merge from each file
{% endswagger-description %}

{% swagger-parameter in="header" name="auth" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" required="true" name="files" type="Array" %}
Array of 

<mark style="color:green;">

Files Object

</mark>
{% endswagger-parameter %}

{% swagger-parameter in="body" name="getAsUrl" type="boolean" %}
Get the file as a temporary url (24 hours)
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Reponse with a standard buffer" %}

{% endswagger-response %}

{% swagger-response status="200: OK" description="Response with a JSON containing the url" %}
```javascript
{
    "url":"FILEURL"
}
```
{% endswagger-response %}
{% endswagger %}

#### <mark style="color:green;">Files Object</mark>

Each object in the files array either needs a url or a buffer and optional the pages you want to merge.

{% code title="File Object" %}
```javascript
{
    "url": "",             // public accessable pdf file url
    "buffer": Buffer,      // file buffer
    "pages": ""            // pages you want to merge
}
```
{% endcode %}

Possible values for pages are the following:&#x20;

```javascript
[3]        // only page 3
[2, 5]     // page 2 and 5
"1, 2, 5"  // page 1, 2, 5
"4 to 8"   // page 4 to 8
"4-8"      // page 4 to 8
```

### HTML to PDF

{% swagger method="post" path="/v1/htmltopdf" baseUrl="https://api.1saas.co" summary="Convert HTML to a pdf" %}
{% swagger-description %}
Convert plain HTML code or a webpage from an url to a pdf file with optional configuration options
{% endswagger-description %}

{% swagger-parameter in="header" name="auth" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="html" required="false" %}
HTM code with single quotes or escaped double quotes
{% endswagger-parameter %}

{% swagger-parameter in="body" name="getAsUrl" type="boolean" %}
Get the file as a temporary url (24 hours)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="options" type="Object" %}
JSON Object of options described down below
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Reponse with a buffer" %}
```javascript
{
    // Response
}
```
{% endswagger-response %}

{% swagger-response status="200: OK" description="Response with a JSON containing the url" %}
```javascript
{
    "url": "FILEURL"
}
```
{% endswagger-response %}
{% endswagger %}

#### HTML to PDF options

The following options can be applied to the output pdf file

{% code title="PDF Options" %}
```javascript
{
    "scale": 1.3             // Scale of the webpage rendering. Defaults to 1. Scale amount must be between 0.1 and 2 
    "landscape": false       // Paper orientation. Defaults to false.
    "format": "A4",          // Paper format. If set, takes priority over width or height options. Defaults to 'Letter'.
    "width": "10cm",         // Paper width, accepts values labeled with units
    "height": "15cm",        // Paper height, accepts values labeled with units
    "margin": {              // Paper margins, defaults to none.
        "top": 5,
        "right": 10,
        "bottom": 10,
        "left": 5
    }      
}
```
{% endcode %}

### Split PDF

{% swagger method="post" path="/v1/splitpdf" baseUrl="https://api.1saas.co" summary="Splits a pdf into custom defined sections" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="auth" required="true" %}
Send your API Key in the header and recieve a status 200 or 402 or 401.
{% endswagger-parameter %}

{% swagger-parameter in="body" name="url" %}
Public URL of the pdf
{% endswagger-parameter %}

{% swagger-parameter in="body" name="buffer" type="Buffer" %}
Buffer
{% endswagger-parameter %}

{% swagger-parameter in="body" name="pages" type="Array" required="true" %}
Array of strings defining the sections which you want to split the pdf into:

Example: `["1", "3-5", "2-3]`

Splits PDF into three pdfs:

only page 1,

page 3 to 5

page 2 and 3
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="Array of URL of the pdfs (lasts 24h)" %}
```javascript
{
    pdfUrls: [
        url1,
        url2,
        ...
    ]
}
```
{% endswagger-response %}
{% endswagger %}
