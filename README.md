# Sculpin Meta Navigation Bundle

This bundle creates a multidimensional array based on meta options of pages. It can be implemented using the `page.menu` twig variable.

## Setup

Add this bundle in your `composer.json` file by requiring it:

```
composer require janbuecker/sculpin-meta-navigation-bundle ^0.2
```

Now you can register the bundle in your `SculpinKernel` class available on `app/SculpinKernel.php` file:

```php
class SculpinKernel extends \Sculpin\Bundle\SculpinBundle\HttpKernel\AbstractKernel
{
    protected function getAdditionalSculpinBundles()
    {
        return [
           'Janbuecker\Sculpin\Bundle\MetaNavigationBundle\SculpinMetaNavigationBundle'
        ];
    }
}
```

## Usage

All files in `source` will be recognized as a Content Type Page. A Twig variable `page.menu` can be looped to automatically generate a menu. This menu is limited to 3 dimensions.

To make a menu item visible, you have to add a `menu_title` to the page.

### Options

| Variable | Type | Description |
-----------------------------
| menu_title | string | Menu item title 
| menu_order | number | Position of the item, low number equals top position
| menu_style | enum   | An additional variable to set the list style option
| group      | string | Parent menu item title on the first dimension (root)
| subgroup   | string | Parent menu item title on the second dimension
