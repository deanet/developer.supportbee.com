---
layout: post
title: Introduction
description: Introduction to SupportBee API
categories: api_docs
---

REST API for SupportBee. Response format is JSON.

## Error Codes
Success:            **200**  
Created:			**201**  
Failure:            **500**  
Access Denied:      **401**  
Validation Failure: **400**

## Authentication
Authentication is using **Token Authentication**.  

The key to pass the
authentication token is **auth_token**  
For Example **https://{company}.supportbee.com/users.json?auth_token=_ABSCDFEESDSD**  

An agent/admin can find his/her API token in *Settings > API Token* screen.  
All API calls require Authentication except for  **Creating Tickets**

## API endpoint
### https://{company}.supportbee.com/
All API calls must be through a company

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