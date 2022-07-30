### successPage($data)
 * @param Array $data  - Page Data
 * @return View Template

This funtion is used to show success message page after an action was done.

```php
  $data = [
    'title' => $title,
    'message' => $successMessage,
    'actionUrl' => $nextUrl, //optional
    'actionText' => $buttonText, //optional
  ];
  successPage( $data ); 
``` 

### emailSender($data)
  * @param $viewData['tempalteName'=> , 'templateData' => '']
  * @param $mailData ['to', 'toName', 'subject', 'from', 'fromName']
 * 
 * @return 

This funtion is used to send email.

```php
  $viewData = [
    'tempalteName' => 'frontend.email.contact',
    'templateData' => $templateData,
  ];
  
  $mailData = [
    'to' => $to,
    'toName' => $receverName,
    'from' => $from, //optional
    'fromName' => $senderName, //optional
    'subject' => $mailSubject,
  ];  
  
  emailSender( $viewData, $mailData );  
``` 


### recaptcha($data)
  * @param $attribute
  * @param $value
  * @param $fail
  * 
 * @return true|error message

```php
  recaptcha($attribute, $value, $fail);
``` 

### segment($segment, $default = '', $slash = '')
 * $segment {integer} - segment number of the uri. [1 or 2 or 3]
 * $default {string } (Optional)  - if segment not availabe then return 0 or user define value.
 * $slash {string} (Optional) - if given then return as trailing slash (abc/)
 * 
 * Return: string

Provide segment by requirements.

```php
  // http://www.domain.com/4/3
  
  echo segment(2, '1', '/'); // 3/
``` 


### text_num( $text, $length) 
 * $text {string} - Full text.
 * $length {integer} - Expected length of the return text.
 * Return: string

Return text from begining to specified length.

```php
  text_num('this is full-text', 2);  // this
``` 
 
 
 ### params() 
 * @param str $lear Optional - leading separator
 * 
 * Return: string

Return url query with the leading separators.

```php
 // http://www.domain.com/4/3?action=update
 
  params('/');  // update/
``` 
 

### home() 
 * Return: boolean

return true if it is system root .
  
```php
  // https://domain.com/
  home(); 
  // true;
``` 

  
