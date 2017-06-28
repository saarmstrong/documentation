# Models

## Intro

This package uses a combination of ORM Entities and Service Models to manipulate the user records stored in the database tables. This package relies upon Doctrine as an ORM framework.

All interactions with the data model must be performed via entity models, and all interactions with the entities must be performed via service model methods.

## Entities

The entities in this package relate directly to a mapped database table, and an instance of an entity represents a single table row.

All entity properties have a protected scope, and must use the provided getter/setters to retrieve and manipulate their values. 

In addition to the getter/setters, all entities have a few lifecycle setters to set values based upon record creates and updates. These special case methods are indicated in this documentation.

### Role

This entity represents the `roles` table.

##### Properties

* *int* **$id**
    * Represents the autoincrement ID for Roles Table
* *int* **$active**
    * Integer flag representing boolean; Role is active if value is "1"/true, inactive if value is "0"/false
* *string* **$name**
    * String representing the Role name
* *string* **$created**
    * Date string for the timestamp when the record was created
* *string* **$updated**
    * Date string for timestamp when the record was last updated

##### Methods

* **getId()**
    * Returns the current record $id
* **setId(*int* $id)**
    * Sets the current record $id with a provided value
* **getActive()**
    * Returns the current record $active value
* **setActive(*string* $active)**
    * Sets the current record $active with a provided value
* **getName()**
    * Returns the current record $name value
* **setName(*string* $name)**
    * Sets the current record $name with a provided value
* **getCreated()**
    * Returns the current record $created value
* **setCreated(*string* $created)**
    * Sets the current record $created with a provided value
* **getUpdated()**
    * Returns the current record $updated value
* **setUpdated(*string* $updated)**
    * Sets the current record $updated with a provided value
* **doStuffOnPrePersist()**
    * Lifecycle method called on initial record create via @PrePersist annotation
    * Calls existing **setCreated()** method with current timestamp as value
* **doStuffOnPreMerge()**
    * Lifecycle method called on record update via @PreUpdate annotation
    * Calls existing **setUpdated()** method with current timestamp as value

### User

This entity represents the `users` table.

##### Properties

* *int* **$id**
    * Represents the autoincrement ID for Users Table
* *string* **$email**
    * Represents the email for a user
* *string* **$password**
    * Represents the user's hashed password 
* *int* **$role**
    * Foreign Key ID to the role table; represents a user's role
* *string* **$name**
    * Represents a user's name   
* *string* **$gateway_customer_id**
    * Foreign Key Id to a payment gateway table; represents a user's relationship to a payement gateway
    * _Please Note_: this will be implemented in a future feature.
* *string* **$last_login**
    * Timestamp of the user's last successful login
* *string* **$created**
    * Timestamp when the record was created
* *string* **updated**
    * Timestamp when the record was last updated

##### Methods

* **getId()**
    * Returns the current record $id
* **setId(*int* $id)**
    * Sets the current record $id with a provided value
* **getEmail()**
    * Returns the current record $email value
* **setEmail(*string* $email)**
    * Sets the current record $email with a provided value
* **getPassword()**
    * Description: Returns the current record $password value
* **setPassword(*password* $password)**
    * Description: MD5 encodes the provided string and sets the current record's $password value to this hashed string
* **getRole()**
    * Description: Returns the current record $role value
* **setRole(*string* $role)**
   * Sets the current record $role value with a provided value
* **getName()**
    * Returns the current record $name value
* **setName(*string* $name)**
   * Sets the current record $name with a provided value
* **getGatewayCustomerId()**
    * Returns the current record gateway_customer_id value
* **setGatewayCustomerId(*int* $gateway_customer_id)**
    * Sets the current record $gateway_customer_id with a provided value
* **getLastLogin()**
    * Returns the current record $last_login value
* **setLastLogin(*string* $last_login)**
    * Sets the current record $last_login to the provided value
* **getCreatedAt()**
    * Returns the current record $created_at value
* **setCreatedAt(*string* $created_at)**
    * Sets the current record $created_at to the provided value
* **getUpdatedAt()**
    * Returns the current record created_at value
* **setUpdatedAt()**
    * Sets the current record $updated_at to the provided value
* **doStuffOnPrePersist()**
    * Lifecycle method called on initial record create via @PrePersist annotation
    * Calls existing **setCreatedAt()** method with current timestamp as value
* **doStuffOnPreMerge()**
    * Lifecycle method called on record update via @PreUpdate annotation
    * Calls existing **setUpdatedAt()** method with current timestamp as value
* **marshall(*string* $type = 'json')**
    * Method that returns a current record as a 'safe' datatype
    * Used for serializing a record  

### User/Log

This entity represents the `user_event_log` table.

##### Properties

* *int* **$id**
    * Represents the autoincrement ID for User Event Log Table
* *int* **$user_id**
    * Foreign Key ID to the role table; represents a user record and associates it to this log record
* *string* **$event_log**
    * A string indicating the type of user event logged
* *string* **$event_data**
    * A JSON serialized object string representing a user logged event
* *string* **$created_at**
    * Date string for the timestamp when the record was created

##### Methods

* **getId()**
    * Returns the current record id
* **setId(*int* $id)**
    * Sets the current record id
* **getUserId()**
* **setUserId(*string* $userId)**
* **getEventLog()**
* **setEventLog(*string* $eventLog)**
* **getEventData()**
* **setEventData(*string* $eventData)**
* **getCreatedAt()**
* **setCreatedAt(*string* $created)**
* **doStuffOnPrePersist()**
    * Lifecycle method called on initial record create via @PrePersist annotation
    * Calls existing **setCreatedAt()** method with current timestamp as value

## Models

### Mailgun

### Role

### User

### User/Log
