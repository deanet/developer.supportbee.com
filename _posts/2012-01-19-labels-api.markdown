---
layout: post
title: Adding Labels
description: Describes actions retrieving labels of a company, Adding a label to a ticket and Removing a label from a ticket
categories: api_docs
---

### Retrieve Custom Labels of a company

#### POST /labels.json

*Retrieves all the custom labels of a company*

#### Status Codes

Success: 200

Faliure: 500

#### Example

GET /labels.json

{% highlight javascript %}
  {
  "labels":[
    {
      "name":"label1",
      "color":"#ffffff"
    }
  ]
  }  
{% endhighlight %}  

### Add a label to a ticket

#### POST /tickets/_ticket\_id_/labels/_label\_name_.json

*Adds the label with _label\_name_ to the ticket with id _ticket\_id_*

#### Status Codes

Success: 201

#### Example

POST /tickets/1/labels/test.json

{% highlight javascript %}
  {
  "label":{
    "label":"test",
    "ticket":1
  }
  }  
{% endhighlight %}  

### Remove a label to a ticket

#### DELETE /tickets/_ticket\_id_/labels/_label\_name_.json

*Removes the label with _label\_name_ to the ticket with id _ticket\_id_*

#### Status Codes

Success: 204

#### Example

DELETE /tickets/1/labels/test.json

Response is Success with no body
