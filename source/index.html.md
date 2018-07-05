---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:

includes:
  

search: true
---

# Introduction

Welcome to the Scalefog api

# Account

## Get Token

```curl
curl -d "username=yourusername&password=yourpassword" -X POST https://api.scalefog.com/account/getToken
```

> The above command returns JSON structured like this:

```json
[
  {
    "success": "true",
    "token": "6e8c5284926716591f9efb0935db8298"
  }
]
```

POST https://api.scalefog.com/account/getToken`

### Query Parameters

| Parameter | Required | Description            |
| --------- | -------- | ---------------------- |
| username  | Yes      | Your Scalefog username |
| password  | Yes      | Your Scalefog password |

## Register New User

```curl
curl -d "username=yourusername&email=emailaddress&password=yourpassword" -X POST https://api.scalefog.com/account/register
```

Register new user

POST https://api.scalefog.com/account/register`

### Query Parameters

| Parameter | Required | Description            |
| --------- | -------- | ---------------------- |
| username  | Yes      | Your Scalefog username |
| email     | Yes      | Your email address     |
| password  | Yes      | Your Scalefog password |

## Add SSH key

```curl
curl -H "Authorization: Bearer <Access Token> -d "sshkey=<key>" -X POST https://api.scalefog.com/account/addkey
```

Add SSH key to your account

POST https://api.scalefog.com/account/addkey

### Query Parameters

| Parameter | Required | Description |
| --------- | -------- | ----------- |
| sshkey    | Yes      | RSA key     |

# Instances

## List Instances

```curl
curl https://api.scalefog.com/instances -H "Authorization: Bearer <Access Token>"
```

Get a list of all your instances.

GET https://api.scalefog.com/instances

## Create Instance

```curl
curl -H "Authorization: Bearer <Access Token> -d "appname=yourappname&region=1" -X POST https://api.scalefog.com/instances/create
```

Create a new Instance

POST https://api.scalefog.com/instances/create

### Query Parameters

| Parameter | Required | Description       |
| --------- | -------- | ----------------- |
| appname   | No       | Your app name     |
| region    | No       | id of your region |

## Delete Instance

```curl
curl -H "Authorization: Bearer <Access Token>" https://api.scalefog.com/instances/delete/:appname
```

Delete instance

GET https://api.scalefog.com/instances/delete/:appname

## Start Instance

```curl
curl -H "Authorization: Bearer <Access Token>" https://api.scalefog.com/instances/start/:appname
```

Start instance

GET https://api.scalefog.com/instances/start/:appname

## Restart Instance

```curl
curl -H "Authorization: Bearer <Access Token>" https://api.scalefog.com/instances/restart/:appname
```

Restart instance

GET https://api.scalefog.com/instances/restart/:appname

## Stop Instance

```curl
curl -H "Authorization: Bearer <Access Token>" https://api.scalefog.com/instances/stop/:appname
```

Stop instance

GET https://api.scalefog.com/instances/stop/:appname

## List Regions

```curl
curl https://api.scalefog.com/instances/regions
```

> The above command returns JSON structured like this:

```json
[
  {
    "1": "Europe"
  }
]
```

Get a list of all available regions.

GET https://api.scalefog.com/instances/regions
