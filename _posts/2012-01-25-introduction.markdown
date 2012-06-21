---
layout: post
title: Introduction
description: Introduction to SupportBee API
categories: api_docs
---

[SupportBee](http://supportbee.com) is a simple and snappy help desk software that doesn't kill your company's human face.

This page documents the REST API for SupportBee. Response format is JSON.

## Error Codes
Success:            **200**  
Created:			**201**  
Failure:            **500**  
Access Denied:      **401**  
Validation Failure: **400**

## Authentication
We use **Token Authentication**.  

The key to pass the
authentication token is **auth_token**  
For example **https://{company}.supportbee.com/users.json?auth_token=your_auth_token**  

You can find your API token in *Settings > API Token* screen.  
All API calls except **Creating Tickets** require authentication 

## API endpoint
### https://{company}.supportbee.com/

## Date Format

Some of the following API calls accept parameters which represents Date/Time. **The date/time should be provided in UTC**. The format to specify date is shown in the following examples:

{% highlight ruby %}
2001-02-15T04:05:06+07:00
20010215T040506+0700
15th Feb 2001 04:05:06 PM
2001-02-15
20010215
{% endhighlight %}	

Also you can use the format returned in the results of our API.
