## Common API Data (For Controllers and Views).

### appName - Applicaiton Name
```php    
  config('settings.appName') //though settings config
  echo $appName; // for view
```

### appTitle - Applicaiton Title (Long Title)
```php    
  config('settings.appTitle') //though settings config
  echo $appTitle; // for view
```

### url - Applicaiton Base Url from settings
```php    
  config('settings.url') //though settings config
  echo $url; // for view
```

### email - Applicaiton Base E-mail Address
```php    
  config('settings.email') //though settings config
  echo $email; // for view
```
### appAddress - Business Address
```php    
  config('settings.appAddress') //though settings config
  echo $appAddress; // for view
```

### contact - Business Contact Number
```php    
  config('settings.contact') //though settings config
  echo $contact; // for view
```

### logo - Company Logo
```php    
  config('settings.logo') //though settings config
  echo $logo; // for view
```



## Content Page Resources

### Content::articleByAlias()
 * Param: { string } - Post/Page Alias.
 * Return: Object | NULL

```php    
 $page = Content::articleByAlias($alias);
 echo $page->title;
``` 
 
### Content::categoryByAlias()
 * Param: { string } - Page Category Alias
 * Return: Object | NULL

```php    
 $category = Content::categoryByAlias($categoryAlias);
 echo $category->cat_title;
```


### Content::articleById()
 * Param: { int } - Post/Page Id.
 * Return: Object | NULL

```php    
 $page = Content::articleById($pageId);
 echo $page->title;
``` 

### Content::homeContent()
 * Return: Eloquent Collection | NULL

Content for Home pages. Store as section by section.

```php    
 $homeItems = Content::homeContent();
 
 foreach($homeItems as $item):
 	echo $item->h_title; // Title of the section.
	echo $item->h_content; // Section Content
	
 endforeach;
 
``` 

## Get Page if it is Linked with Menu

### Content::menuArticle()
 * Param: { int } - User by ID
 * Return: Object | NULL


## Recent Published Posts/Articles

### Content::recentArticles()
 * Param: { int } - User by ID
 * Return: Object | NULL


## Attributed Articles/Posts Like Featured, Suggested _________

### Content::attributedArticles()  
 * @param String Optional $attribution - (default 'featured') 'featured', 'suggested'
 * @param Int Optional $articleNum - (default 10) Number of post want to.
 * 
 * @return Model Collection

Get Attributed Articles like featured, Suggested etc.

```php   
 $suggestedPosts = Content::attributedArticles('suggested', 5); 
 foreach($suggestedPosts as $item):
 	echo $item->name; // Post Title
 endforeach;
 ```



## Article Tag Control _________

### Content::getTagNames()
 * @param String $articleAlias - Article or Post Alias
 * @return Model Instance | NULL

Get Tag Names of an Article.

```php   
 $tagNames = Content::getTagNames($articleAlias); 
 foreach($tagNames as $item):
 	echo $item->name; // Tag Title
 endforeach;
 ```

### Content::articleByTag()
 * @param String $tagName - Tag Name
 * @return Model Instance | NULL

Get all Articles of a Tag Name.

```php   
 $tagArticles = Content::articleByTag($tagName); 
 foreach($tagArticles as $item):
 	echo $item->title; // Article Title
 endforeach;
 ```


## Count and Get page views

### Content::viewCount()
 * Param: { int } - User by ID
 * Return: Object | NULL

### Content::getViewCount()
 * Param: { int } - User by ID
 * Return: Object | NULL



## Next or Previous Articles for A Post

### Content::next()
 * Param: { int } - User by ID
 * Return: Object | NULL

### Content::previous()
 * Param: { int } - User by ID
 * Return: Object | NULL


## Page Breadcrumb

### Content::breadcrumb()
 * Param: { int } - User by ID
 * Return: Object | NULL


## Related Articles for A Page/Post

### Content::relatedArticle()
 * Param: { int } - User by ID
 * Return: Object | NULL

### Content::dbRelatedArticles()
 * Param: { int } - User by ID
 * Return: Object | NULL


## Page Meta Data.

### Content::metaData($post)
 * Param: { Object } - Post Object.
 * Return: Object

Page/Post Meta Data.

```php  
  $meta = Content::metaData($post);
  $meta->metaTitle;
```

### $meta - Page metadata for views;

```php  
  $meta->metaTitle;
  $meta->metaUrl;
  $meta->metaImage;
  $meta->metaKeyword;
  $meta->metaDescription;
  $meta->metaSnippet;  
```






### $content
* Type: stdClass Object.

Content return the single Aarticle Post Data as stdClass Object.

```php
stdClass Object
(
    [title] => Our Definitive Guide to Cold and Flu
    [alias] => our-definitive-guide-to-cold-and-flu
    [introtext] => This is intro.... 
    [fulltexts] => This is Full Texts.....
    [featuredimg] => https://domain.com/public/images/uploads/respiratory-1024x554.jpg
    [hits] => 344
    [metakeys] => Guide to Cold, Flu, health
    [metades] => Our Definitive Guide to Cold and Flu 
    [is_menu] => 1
    [access] => 1
    [status] => active
    [cat_id] => 1
    [cat_title] => Blog
    [cat_alias] => blog
    [cat_picture] => https://domain.com/images/paper-boat-2.jpg
    [cat_description] => This is Blog Category. Any one can view blog post in this section
    [cat_status] => active
)
```

```php
 echo $content->title; // Our Definitive Guide to Cold and Flu
 
 echo $content->alias; // our-definitive-guide-to-cold-and-flu
 
```


### $homePosts
 * Type: Associative array data.
 
 Content data for home page. Maximum 6 to 10 post data.
 homePosts data can be found as array which need to be iterate.
  
 ```markdown
 Array
(
    [0] => Array
        (
		[title] => Blog Post
		[alias] => blog-post
		[introtext] => This is intro...
		[featuredimg] => 
		[created_at] => 2020-11-25 06:11:00
		[cat_title] => Blog
		[cat_alias] => blog
		[catlead] => 0                       
            
        )
 ...
)
 
 ```

 
 

