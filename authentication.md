# Authentication

### register($credentials)
 * Param: Array $credentials
 * Return: boolean

Register a new user to the system.


### authenticate(array $credentials)
     * @param Array $credentials 
     * @return reply object

Authenticate a user to the system
 
 ### check()
   * @param no
   * @return reply object

Check whether the user logged in or not. If logged then it returns true, otherwise false.

```php

if(dAuth()->check())
echo dAuth()->getUser()->username;

```

### getUser()
 * Return: Object | NULL

Return the user name when looged in, otherwise return NULL

```php
echo dAuth()->getUser()->username;
```


### findById($id)
 * $id { int } - User by ID
 * Return: Object | NULL

Find A User by its Id.

```php
 $user = dAuth()->findById(1)
 
```


