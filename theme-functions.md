## Theme Functions.
 * [Menu Bars](theme-functions.md#menu)
 * [Images](theme-functions.md#image)
 * [Other](theme-functions.md#other)


## Menu

### showMainMenu($menu, $attributes = [] )
 * $menu {array} - formatted multidimentional associative array.
 * $attributes {array | optional }  - HTML tag attributes

Show the main menu for the system.

```html
<nav class="navbar navbar-expand main-menu">				  
	<div class="collapse navbar-collapse justify-content-end top-nav">		
		<?php 
			$attributes = [
				'navAttr' => 'class="navbar-nav ml-auto"',
				'subNavAttr' => 'class="dropdown-menu animate__animated animate__fadeIn animate__faster"'
			];
			showMainMenu($menu, $attributes );
		?>
	</div>																
</nav>
```




## Image

### viewImage($images, $title, $withimgtag, $single)
 * $images {string} - Image path strings
 * $title {string} (Optional) - title of the image. Default: NULL
 * $withimgtag {boolean} (Optional) - With image tag or only image path. Default: (TRUE) - return with image tag
 * $single {boolean} (Optional) - if multiple image paths then determine whether need single first one or all. Default: (TRUE) - Single image.
 
 Format featured image paths into html way. 
 
 ```php
  viewImage('http://domain.com/images/image.jpg', 'This is image');
  //<img srg="http://domain.com/images/image.jpg" title="This is image" />
  
 
 ```
 
 
 
 ## Other
 
### share($content)
* $content {array} - Base content array.
* Return: string

Return article post share links. Use only on a single post page.


### contentUtility()
* Return: string

Article post print, text size increase or decrease utility. Use Only on a single post page.




 
