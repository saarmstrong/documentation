# Users Ajax

## Intro

The Users package exposes some AJAX endpoints to allow your Erdiko Application to interact with the underlying service models. 

All of these AJAX endpoints return a JSON formatted response.

Some of these endpoints require an authenticated user and will be noted as such.

## Endpoints


### User Authentication AJAX

#### postLogin

#### getLogout

#### postChangepass

#### postForgotpass

### Role AJAX

#### getRoles

Return a list of active roles found in the DB and a count of active users associated with the role.

#### getRole

Returns a JSON representation of a valid Role for a provided ID
along with a list of users associate with this role.

#### postCreaterole

Create a Role record with the provided values.

#### postUpdaterole

Update a Role record for a provided ID with the provided value.

#### postDeleterole

Deletes a Role based on a provided ID.

### User AJAX

#### postRegister

Create a User record with the provided values.

#### getList

Return a list of active users found in the DB.

#### getRetrieve

Returns a JSON representation of a valid User for a provided ID along with a list of users associate with this role.

#### postUpdate

Update a Role record for a provided ID with the provided value

#### getCancel

Deactivate a user for a provided ID.

### Admin User AJAX

#### postCreate

#### getList

#### getRetrieve

#### postUpdate

#### postDelete

#### getUserActivity

#### getEventLogs

#### postChangepass

