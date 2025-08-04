---
title: Status Codes
excerpt: ''
deprecated: false
hidden: false
metadata:
  title: ''
  description: ''
  robots: index
next:
  description: ''
---
Always check if your API call was successful or resulted in error. You may check the following

- 200 OK response header.
- 4XX ERROR response header

Please check the table below for common error constants. Note that some API functions can return custom errors of their own (listed in appropriate document sections). Check the error description for details, e.g. which field caused an error or which resource you don’t have access to.

| CODE                | HEADER | DESCRIPTION                                                              |
| ------------------- | ------ | ------------------------------------------------------------------------ |
| SUCCESS             | 200    | OK                                                                       |
| AUTH_FAILED_NO_DATA | 401    | You have not provided auth data.                                         |
| AUTH_FAILED         | 401    | The auth data you have provided is invalid.                              |
| NOT_IMPLEMENTED     | 404    | The method you are requesting is unsupported.                            |
| OVER_LIMIT          | 429    | You have exceeded the request limit.                                     |
| FIELD_EMPTY         | 400    | Required field is empty.                                                 |
| FIELD_INVALID       | 400    | Field has invalid format (see proper format in the description).         |
| NO_ACCESS           | 400    | You don't have access to this feature                                    |
| KEY_EXISTS          | 400    | The resource with this key already exists.                               |
| LEDGER_ERROR        | 400    | Insufficient funds to carry out debit                                    |
| BAD_CALLER_ID       | 400    | The sender ID you have set is not valid or number is inactive or expired |