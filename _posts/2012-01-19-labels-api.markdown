---
layout: post
title: Labels
description: Describes actions retrieving labels of a company, Adding a label to a ticket and Removing a label from a ticket
categories: api_docs
---

Retrieve Custom Labels of a company
-----------------------------------
#### POST /labels.json
*Retrieves all the custom labels of a company*

#### Status Codes
Success: 200

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

Add a label to a ticket
-----------------------
#### POST /tickets/{ticket\_id}/labels/{label\_id}.json
*Adds the label with {label\_id} to the ticket with id {ticket\_id}*

#### Status Codes
Success: 201

#### Example
POST /tickets/1/labels/2.json
{% highlight javascript %}
  {
  "label":{
    "id":2,
    "label":"label1",
    "ticket":1
  }
  }  
{% endhighlight %}  

Remove a label to a ticket
--------------------------
#### DELETE /tickets/{ticket\_id}/labels/{label\_id}.json
*Removes the label with {label\_id} to the ticket with id {ticket\_id}*

#### Status Codes
Success: 204

#### Example
DELETE /tickets/1/labels/2.json  
Response is Success with no body