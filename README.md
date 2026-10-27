# Cache Module

The Cache module provides PSR-16 cache adapters backed by files or in-memory storage. It binds `Flexi\Contracts\Interfaces\CacheInterface` and the `cache` service alias.

## Configuration

The factory reads `cache_driver` and `cache_dir` from Flexi configuration. Supported driver values are `file`, `array`, and `memory`; `array` and `memory` use the in-memory adapter. The default is file storage under the application cache directory.

```php
$cache = $container->get('cache');
$cache->set('key', 'value', 3600);
$value = $cache->get('key', 'fallback');
```

The module requires PHP 7.4+, `flexi/contracts` `^5.2.1`, and Flexi Core `^3.2`. Install the Composer package and explicitly activate the `Cache` module.

## Tests

Install the development dependencies with `composer install`, then run `vendor/bin/phpunit tests` from the module root.
