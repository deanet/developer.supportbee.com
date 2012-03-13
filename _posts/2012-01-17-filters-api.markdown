---
layout: post
title: Filters
description: Filters API
categories: api_docs
---

Each Filter is made up of two parts. A **rule** and a **consequence**  
A rule specifies the fields to match and their values.  
A consequence specifies the actions to be done on a match with the corresponding rule.  

Retrieving Filters
-------------------
#### GET /filters.json  
*returns all the filters of the company*  

#### Status Codes  
Success: 200  

#### Example  
GET /filters.json  
{% highlight javascript %}
  {
    "filters":[{
      "id":"2_20120119141139",
      "rule":{
        "requester_email":"",
        "delivered_to":"support@example.com",
        "subject":"",
        "body":""
      },
      "consequence":{
        "archive":true,
        "spam":null,
        "label":"pending",
        "assign_user":"",
        "assign_group":"27"
      }
    }]
  }
{% endhighlight %}

Creating a Filter
-----------------
Creating a filter involves creating a rule and a consequense   

#### Creating a Rule  
#### POST /rules.json  
*creates a rule for the company and returns an id*  

#### Status Codes  
Success: 201  
Validation Errors: 400

#### Post Data  
This specifies the data in JSON required to create a rule. A sample JSON request object is  

{% highlight javascript %}
  {
    "rule":{
      "requester_email":"",
      "delivered_to":"support@example.com",
      "subject":"",
      "body":""
    }
  }  
{% endhighlight %} 

Specify atleast one of the following parameters  

**requester_email**  
Specifies the email of the requester of the ticket.  

**delivered_to**  
Specifies the email address to which ticket was delivered  

**subject**  
Specifies the keywords in the subject of the ticket    

**body**  
Specifies the keywords in the body of the ticket  

### Example Response
{% highlight javascript %}
  {
    "rule":{
      "id":"2_20120313105420"
    }
  }
{% endhighlight %}

#### Creating a Consequence
#### POST /consequences.json
*creates a consequence for the company and returns an id*

#### Status Codes
Success: 201  
Validation Errors: 400

#### Post Data
This specifies the data in JSON required to create a consequence. A sample JSON request object is 

{% highlight javascript %}
  {
    "consequence":{
        "label":"pending"
    }
  }  
{% endhighlight %} 

Specify atleast one of the following parameters

**archive**  
If _true_ archives the ticket on a filter match  

**spam**  
If _true_ spams the ticket on a filter match  

**label**  
Specifies the name of the label to attach on a filter match. The label must already exist for the company.  

**assign_user**  
Specifies the id of the user to assign on a filter match  

**assign_group**  
Specifies the id of the group to assign on a filter match  

### Example Response
{% highlight javascript %}
  {
    "consequence":{
      "id":"2_20120313105420"
    }
  }
{% endhighlight %}

#### Creating a Filter
#### POST /filters.json
*creates a filter for the company*

#### Status Codes
Success: 201  
Validation Errors: 400

#### Post Data
This specifies the data in JSON required to create a consequence. A sample JSON request object is 

{% highlight javascript %}
  {
    "filter"=>{
      "consequence_id"=>"2_20120313105925", 
      "rule_id"=>"2_20120313105924"
    }
  }  
{% endhighlight %}

**consequence_id**  
Specifies the consequence associated with this filter. You can create a consequence as shown above.  
Required

**rule_id**  
Specifies the rule associated with this filter. You can create a rule as shown above.  
Required

#### Example Response
{% highlight javascript %}
  {
    "filter":{
      "id":"2_20120119141139",
      "rule":{
        "requester_email":"",
        "delivered_to":"support@example.com",
        "subject":"",
        "body":""
      },
      "consequence":{
        "archive":true,
        "spam":null,
        "label":"pending",
        "assign_user":"",
        "assign_group":"27"
      }
    }
  }
{% endhighlight %}

Updating a Filter
-----------------
Currently one cannot update/edit a filter. 

Deleting a Filter
-----------------
#### DELETE /filters/{id}.json  
*Deletes a filter with id: {id}*  

#### Status Codes  
Success: 204  

#### Example  
DELETE /filters/1.json  
Response is Success with no body  

Search for tickets that matches a rule  
--------------------------------------
#### GET /filters/search.json  
*Retrives the tickets matching the rule in the last 100 tickets*

### Get Data  
This specifies the data in JSON required to create a consequence. A sample JSON request object is  

{% highlight javascript %}
  {
    "rule":{
      "requester_email":"",
      "delivered_to":"support@example.com",
      "subject":"",
      "body":""
    } 
  }
{% endhighlight %}

#### Example  
GET /filters/serach.json  

Sample Curl:  
  curl -v -H 'Content-Type: application/json' -X GET -d "{'rule':{'requester_email':'','delivered_to':'','subject':'Testing','body':''}}" 'http://company.supportbee.com/filters/search.json?auth_token=abcde'  


#### Example Response  
The response is similar to the API call for [retrieving tickets](#retrieving_tickets)  