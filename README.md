Style Mirror Bundle
===================

Symfony dependency injection bundle for the Style Mirror library.

This bundle provides the following services:

* `orbt_style_mirror.css.aggregator`: CSS aggregator service. This aggregates a collection of CSS resources with
  potentially different media types into a single resource.
* `orbt_style_mirror.css.scanner`: Utility for scanning linked resources from a style sheet.
* `orbt_style_mirror.css.linked_fetcher`: Resource materialize event subscriber. See Configuration below to subscribe
  the fetcher automatically to the resource mirror.

Installation using Composer
---------------------------

Add the following to the `"require"` list in your `composer.json` file:

```
    "orbt/style-mirror-bundle": "dev-master"
```

Run composer to update dependencies:

```bash
$ composer update
```

Or to just download this bundle:

```bash
$ composer update orbt/style-mirror-bundle
```

Register this bundle in the application kernel:

```php
<?php
// app/AppKernel.php
public function registerBundles()
{
    $bundles = array(
        // ...
        new Orbt\Bundle\StyleMirrorBundle\OrbtStyleMirrorBundle(),
        // ...
    );

    return $bundles;
}
```

Configuration
-------------

The style mirror is configured under the key `orbt_style_mirror`. There are two options:

* `aggregate_prefix`: The prefix of the generated file name of the aggregated style sheet. This can be used to fix the
  base in a Symfony application for routing matching requests to a controller.
* `fetch_linked_resource`: If true, the linked resource fetcher is automatically subscribed to the resource mirror
  service from the resource mirror bundle.

License
-------

This library is licensed under the MIT License. See the LICENSE file for detailed license information.
