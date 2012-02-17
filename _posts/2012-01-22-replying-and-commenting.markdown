---
layout: post
title: Replying and Commenting on a Ticket
description: Adding Comments and Replies to Ticket
categories: api_docs
---

Retrieving Replies
-----------------
#### GET /tickets/{ticket\_id}/replies.json
*Retrieves all the replies of the ticket with id {ticket\_id}*

### Example
GET /tickets/1/replies.json

{% highlight javascript %}
{
  "replies":[
    {
      "id":1,
      "created_at":"2012-01-20T03:45:51Z",
      "summary":"Reply Content",
      "cc":[],
      "ticket":{
        "replies_count":2,
        "comments_count":0
      },
      "replier":{
        "id":1,
        "email":"person2@example.com",
        "name":"Agent,1",
        "agent":true,
        "picture":{
          "thumb20":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=20",
          "thumb24":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=24",
          "thumb32":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=32",
          "thumb48":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=48",
          "thumb64":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=64",
          "thumb128":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=128"
        }
      },
      "content":{
        "body":"Reply Content",
        "html":null,
        "attachments":[]
      }
    }
  ]
}
{% endhighlight %} 

Posting a Reply
---------------
#### POST /tickets/{ticket\_id}/replies.json
*Posts a reply to the ticket with id {ticket\_id}*

#### Status Code
Success: 201

#### POST Data

{% highlight javascript %}
  {
  "reply":{
    "content_attributes":{
      "body_html":"<p>Reply Content</p>",
      "body": "Reply Content",
      "attachment_ids":[]
    }
  }
 }  
{% endhighlight %}  

The POST data must contain either "body" or "body_html". Take a looks at
[Attachment API] (#/api_docs/2012/01/19/attachments-api) to see how to upload attachments to SupportBee

#### Example
POST /tickets/1/replies.json

{% highlight javascript %}
  {
"reply":{
  "id":3,
  "created_at":"2012-01-20T04:03:09Z",
  "summary":"This is the body",
  "cc":[],
  "ticket":{
    "replies_count":3,
    "comments_count":0
  },
  "replier":{
    "id":1,
    "email":"person2@example.com",
    "name":"Agent,1",
    "agent":true,
    "picture":{
      "thumb20":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=20",
      "thumb24":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=24",
      "thumb32":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=32",
      "thumb48":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=48",
      "thumb64":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=64",
      "thumb128":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=128"
    }
  },
  "content":{
    "body":"Reply Content",
    "html": "<p>Reply Content</p>",
    "attachments":[]
  }
 }
}
{% endhighlight %}  

Retriving Comments
------------------
#### GET /tickets/{ticket\_id}/comments.json
*Retrieves all the comments of the ticket with id {ticket\_id}*

### Example
GET /tickets/1/comments.json

{% highlight javascript %}
  {
  "comments":[
    {
      "id":1,
      "created_at":"2012-01-20T04:13:26Z",
      "ticket":{
        "replies_count":0,
        "comments_count":1
      },
      "commenter":{
        "id":1,
        "email":"person2@example.com",
        "name":"Agent,1",
        "agent":true,
        "picture":{
          "thumb20":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=20",
          "thumb24":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=24",
          "thumb32":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=32",
          "thumb48":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=48",
          "thumb64":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=64",
          "thumb128":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=128"
        }
      },
      "content":{
        "body":"Reply Content",
        "html":null,
        "attachments":[]
      }
    }
  ]
}  
{% endhighlight %}  

Posting a Comment
-----------------
#### POST /tickets/{ticket\_id}/comments.json
*Posts a comment to the ticket with id {ticket\_id}*

#### Status Code
Success: 201

#### POST Data

{% highlight javascript %}
  {
  "comment":{
    "content_attributes":{
      "body_html":"<p>Reply Comment</p>",
      "body": "Reply Comment",
      "attachment_ids":[]
    }
  }
 }  
{% endhighlight %}  
 
The POST data must contain either "body" or "body_html". Take a looks at
[Attachment API] (#/api_docs/2012/01/19/attachments-api) to see how to upload attachments to SupportBee

#### Example
POST /tickets/1/comments.json

{% highlight javascript %}
  {
  "comment":{
    "id":1,
    "created_at":"2012-01-20T04:13:26Z",
    "ticket":{
      "replies_count":0,
      "comments_count":1
    },
    "commenter":{
      "id":1,
      "email":"person2@example.com",
      "name":"Agent,1",
      "agent":true,
      "picture":{
        "thumb20":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=20",
        "thumb24":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=24",
        "thumb32":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=32",
        "thumb48":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=48",
        "thumb64":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=64",
        "thumb128":"https://secure.gravatar.com/avatar/be27d979489e5ff5f6f503442c9d349b.png?r=PG&s=128"
      }
    },
    "content":{
      "body":"Comment Content",
      "html": "<p>Comment Content</p>",
      "attachments":[]
    }
  }
}  
{% endhighlight %}  