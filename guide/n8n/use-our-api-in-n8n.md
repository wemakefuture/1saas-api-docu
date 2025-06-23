---
description: >-
  In n8n you can use the 0Codekit Node or use our API directly. This is a how to
  use our API directly.
---

# Use our API in n8n

Our API docs are hosted here: [https://scalar.0codekit.com/](https://scalar.0codekit.com/)

To get access to our api just go to scalar and select the api you want to use.&#x20;

Then make sure you select the dropdown option under Shell:Curl&#x20;

<figure><img src="../../.gitbook/assets/image (14).png" alt=""><figcaption></figcaption></figure>

Copy the Curl command and open you n8n workflow.&#x20;

Add a new HTTP node and open it.

On the top right click on import curl and paste the curl command from our api documation

<div align="center"><figure><img src="../../.gitbook/assets/image (15).png" alt="" width="375"><figcaption></figcaption></figure></div>

After the import you just have to fill in the fields like your actual API key and body parameters.

<figure><img src="../../.gitbook/assets/image (17).png" alt="" width="375"><figcaption></figcaption></figure>

With that you are now directly connected to the 0CodeKit API :tada:
