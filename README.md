# pixel-php
Pixel pass through redirect using php

## Setup
This method requires no setup, PHP includes all the functionality we need.

## Implementation
For this step we need to get the value from the url. In our exmaple we're getting the subid from the url. We're checking if a subid is there, then sending the user to the success page along with the subid.

```php
<?php
  $newURL = './success.php';

  if(isset($_GET['subid'])) {
    header('Location: '.$newURL.'?subid='.$_GET['subid']);    
  }
?>
```

#### Success
On the success page we then repeat the similar process of getting the value from the url, then setting the result to an image.

Firstly lets get the `subid`, and store it.

```php
<?php
  $subid = '';
  
  if(isset($_GET['subid'])) {
    $subid = $_GET['subid'];
  }
?>
```

Next, lets add it to our img src.
```html
<img id="subid-img" src="https://creative.wwwpromoter.com/conversion?c=29621&a=4132&ch=<?= $subid ?>"/>
```

This is the part of the code where we add it to the string. 
```php
<?= $subid ?>
```
