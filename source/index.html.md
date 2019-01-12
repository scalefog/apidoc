---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:

includes:

search: true
---

# Introduction

Welcome to the Scalefog api Documentation

# Account

## Get Token

```curl
curl -d "username=yourusername&password=yourpassword" -X POST https://api.scalefog.com/user/getToken
```

> The above command returns JSON structured like this:

```json
[
  {
    "success": "true",
    "accesstoken": "6e8c5284926716591f9efb0935db8298"
  }
]
```

POST https://api.scalefog.com/user/getToken`

### Query Parameters

| Parameter | Required | Description            |
| --------- | -------- | ---------------------- |
| username  | Yes      | Your Scalefog username |
| password  | Yes      | Your Scalefog password |

## Register New User

```curl
curl -d "username=yourusername&email=emailaddress&password=yourpassword" -X POST https://api.scalefog.com/user/register
```

Register new user

POST https://api.scalefog.com/user/register`

### Query Parameters

| Parameter | Required | Description            |
| --------- | -------- | ---------------------- |
| username  | Yes      | Your Scalefog username |
| email     | Yes      | Your email address     |
| password  | Yes      | Your Scalefog password |

## Add SSH key

```curl
curl -H "Authorization: Bearer <Access Token> -d "sshkey=<key>" -X POST https://api.scalefog.com/user/addkey
```

Add SSH key to your account

POST https://api.scalefog.com/user/addkey

### Query Parameters

| Parameter | Required | Description |
| --------- | -------- | ----------- |
| sshkey    | Yes      | RSA key     |

## Delete SSH key

```curl
curl -H "Authorization: Bearer <Access Token>" -d "token=<token>" -X "DELETE" https://api.scalefog.com/user/key
```

Delete RSA key

DELETE https://api.scalefog.com/user/key

# Instances

## List Instances

```curl
curl https://api.scalefog.com/instances -H "Authorization: Bearer <Access Token>"
```

Get a list of all your instances.

GET https://api.scalefog.com/instances

## Create Instance

```curl
curl -H "Authorization: Bearer <Access Token> -d "appname=yourappname&region=eu" -X POST https://api.scalefog.com/instances/create
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
curl -H "Authorization: Bearer <Access Token>" -X "DELETE" https://api.scalefog.com/instances/delete/:appname
```

Delete instance

DELETE https://api.scalefog.com/instances/:appname

## List Regions

```curl
curl https://api.scalefog.com//regions
```

> The above command returns JSON structured like this:

```json
[
  {
    "name": "Eu"
  }
]
```

Get a list of all available regions.

GET https://api.scalefog.com/regions
