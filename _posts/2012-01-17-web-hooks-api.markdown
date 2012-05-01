---
layout: post
title: Web Hooks
description: Web Hooks API
categories: api_docs
---

Retrieving Web Hooks
-------------------
#### GET /web_hooks.json
*returns all the web hooks of the company*

#### Status Codes
Success: 200

#### Example
GET /web_hooks.json
{% highlight javascript %}
  {
    "web_hooks":[{
      "id":"1_20120501071947",
      "url":"http://example.com"
    }]
  }
{% endhighlight %}

Creating a Web Hook
-------------------
#### POST /web_hooks.json
*creates a web hook for the company*

#### Status Codes
Success: 201  
Validation Errors: 400

#### Post Data
This specifies the data in JSON required to create a web hook. A sample JSON request object is 

{% highlight javascript %}
  {
  "web_hook":{
    "url": "http://example.com"
  }
}  
{% endhighlight %} 

**url**  
Specifies the url for the web hook.  
Required

#### Example Response
{% highlight javascript %}
  {
    "web_hook":{
      "id":"1_20120501073314",
      "url":"http://example.com"
    }
  }
{% endhighlight %}

Updating a Web Hook
-------------------
#### PUT /web_hook/{id}.json
*updates a web hook with id {id}*

#### Status Codes
Success: 200
Validation Errors: 400

#### PUT Data
Same as POST Data for creating a web hook. 

#### Example Response
Same as the response for creating a web hook.

Deleting a Web Hook
-------------------
#### DELETE /web_hooks/{id}.json
*Deletes a web hook with id: {id}*

#### Status Codes
Success: 204  

#### Example
DELETE /web_hooks/1_20120501073314.json  
Response is Success with no body

Testing a Web Hook
------------------
#### POST /web_hooks/test.json

#### POST Data
This specifies the data in JSON required to test a web hook. A sample JSON request object is 

{% highlight javascript %}
  {
    "action_type": "ticket.created"
    "url": "http://example.com"
  }  
{% endhighlight %}

**action_type**  
Specifies the kind of action to trigger to test the web hook.  

**url**  
Specifies the url to which a HTTP POST is triggered with the test data.

#### Status Codes
Success: 200  
Failure: 500