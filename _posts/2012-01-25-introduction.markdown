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
Authentication is through **Token Authentication**. An agent/admin can find his/her API token in *Settings > API Token* screen.  
All API calls require Authentication except for **Creating Tickets**

## API endpoint
### https://*company*.supportbee.com/
All API calls must be through a company