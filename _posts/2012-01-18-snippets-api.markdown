---
layout: post
title: Snippets
description: Snippets API
categories: api_docs
---

Retrieving Snippets
-------------------
#### GET /snippets.json
*returns all the snippets of the company*

#### Status Codes
Success: 200

#### Example
GET /snippets.json
{% highlight javascript %}
  {
  	"snippets":[{
  		"id":4,
  		"created_at":"2012-01-06T20:18:08Z",
  		"name":"Facebook Link",
  		"tags":"facebook, link",
  		"content":{
  			"text":"Facebook",
  			"html":"<p><a href=\"http://facebook.com\">Facebook</a></p>"
  		}
  	}]
  }
{% endhighlight %}

Creating a Snippet
------------------
#### POST /snippets.json
*creates a snippet for the company*

#### Status Codes
Success: 201  
Validation Errors: 400

#### Post Data
This specifies the data in JSON required to create a snippet. A sample JSON request object is 

{% highlight javascript %}
  {
  "snippet":{
    "name" : "Facebook Link",
    "content_attributes":{
      "text": "Facebook",
      "html":"<p><a href=\"http://facebook.com\">Facebook</a></p>"
    },
    "tags": "facebook, link"
  }
}  
{% endhighlight %} 

**name**
Specifies the name of the snippet.
Required

**body/body_html**  
Specifies the content of the snippet. Either body or body_html must be present

**tags**
Specifies the tags for the snippet.

#### Example Response
{% highlight javascript %}
  {
  	"snippet":{
  		"id":4,
  		"created_at":"2012-01-06T20:18:08Z",
  		"name":"Facebook Link",
  		"tags":"facebook, link",
  		"content":{
  			"text":"Facebook",
  			"html":"<p><a href=\"http://facebook.com\">Facebook</a></p>"
  		}
  	}
  }
{% endhighlight %}

Updating a Snippet
------------------
#### PUT /snippet/{id}.json
*updates a snippet with id {id}*

#### Status Codes
Success: 200
Validation Errors: 400

#### PUT Data
Same as POST Data for creating a snippet. 

#### Example Response
Same as the response for creating a snippet.

Deleting a Snippet
------------------
#### DELETE /snippets/{id}.json
*Deletes a snippet with id: {id}*

#### Status Codes
Success: 204  

#### Example
DELETE /snippets/1.json  
Response is Success with no body
