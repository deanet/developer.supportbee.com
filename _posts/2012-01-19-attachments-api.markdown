---
layout: post
title: Attachments
description: API to add Attachments to SupportBee
categories: api_docs
---

Creating an Attachment
----------------------
#### POST /attachments.json

#### Status Code
Success: 201

#### POST data
{% highlight javascript %}
  {
    files: <file_to_upload>
  }	
{% endhighlight %}	

#### Example
POST /attachments.json

{% highlight javascript %}
{
	"attachment":{
	  "id":1364,
	  "created_at":"2012-02-17T19:23:18Z",
	  "filename":"wow.jpeg",
	  "content_type":"image/jpeg",
	  "url":{
	  	"original": <url to original file>,
	  	"thumb": <url to thumb file>
	  }
	}
}
{% endhighlight %}	

