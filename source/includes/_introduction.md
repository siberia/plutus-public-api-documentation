# Introduction

Welcome to the No Name Brand Platform API! You can use our API to access No Name Brand Platform API endpoints, for transactional banking.

**PLEASE NOTE THAT THIS DOCUMENT IS SUBJECT TO CHANGE**

You can view code examples in the dark area to the right.

If you have any queries about the No Name Brand Platform API, please direct them to support at no name brand dot co dot za.

Our API uses JSON payloads over HTTPS and returns JSON payloads back.

## Pagination

Pagination works on collections of models (i.e. users, transactions history, accounts, etc.)

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
limit | 100 | Specifies the maximum number of users to fetch
offset | 0 | Starts from the first user up to limit users

## API Request Identifiers

All API calls return a X-Request-ID which should be provided for when debugging issues you experience.

> Example of headers:

```
X-Request-ID: 9d45fcf7-ca4e-4146-a344-6421ef90cbe0
```

## API Repsonse Statuses

### Status Codes

Key | Value
--- | -----
ok | Response is ok (i.e. retrieved the requested resource which is then contained in the details key in the returned JSON response.
error | Something went wrong (i.e. missing required parameters or the resource requested does not exist.)

> Example of a successful response:

```json
{
  "status": "ok",
  "details": [
    {
      "uuid": "9ee3314c-40dd-11e5-9bc4-1bbf7f69525d",
      "title": "MR",
      "first_name": "JOHN",
      "last_name": "RABIE",
      "mobile_number": "271234567890"
    },
    {
      "uuid": "9df55274-40dd-11e5-be41-033d23a48a0e",
      "title": "MR",
      "first_name": "MICHAEL",
      "last_name": "TUCKER",
      "mobile_number": "271234567891"
    }
  ]
}
```

> Example of an unsuccessful response:

```json
{
  "status": "error",
  "message": "You cannot transact until you provide your FICA documentation to the call center.  Contact 08610 XXXXX."
}
```
