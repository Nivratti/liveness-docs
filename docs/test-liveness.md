# Test Liveness

Liveness sdk provides interface to verify liveness, perform face match, detect age and gender of person.


## 1. Verify liveness:

To test liveness sdk provides interface named `verify_liveness`.


```php
<?php

$result = verify_liveness('images/test.png');

echo "Liveness result: \n";
print_r($result);
?>
```

It takes one parameter as path to input image.
