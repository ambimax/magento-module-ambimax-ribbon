
#  ambimax® Ribbon

This module is supposed to add an ribbon attribute to Magento eCommerce.

## Installation

For installation use composer or copy files manually.

### composer
```
"repositories": [
    {
        "type": "vcs",
        "url": "https://github.com/ambimax/magento-module-ambimax-ribbon"
    }
],
"require": {
    "ambimax/magento-module-ambimax-ribbon": "~1.0"
}
```

### Theme

To add the ribbons to your theme, add the following snippet to all
required theme files.

```php
<div class="ambimax-ribbon">
    
    <?php foreach($_product->getAttributeText('ribbon') as $ribbon): ?>
        <span class="<?php echo strtolower($ribbon) ?>">
            <?php echo $this->__($ribbon) ?>
        </span>
    <?php endforeach ?>
    
</div>
```

### Add Ribbon

1. To add a ribbon just extend the ribbon attribute options (```Catalog > Manage Attributes > Ribbon Attribute > Manage Options```)
2. Style with css
3. Add translation

### Custom Ribbons

To add a custom ribbon you can extend it very easily

```php
<div class="ambimax-ribbon">
    
    <?php foreach($_product->getAttributeText('ribbon') as $ribbon): ?>
        <span class="<?php echo strtolower($ribbon) ?>">
            <?php echo $this->__($ribbon) ?>
        </span>
    <?php endforeach ?>
    
    <?php if($_product->getData('custom_ribbon')): ?>
        <span class="custom-ribbon">
            <?php echo $this->__('Custom Ribbon') ?>
        </span>
    <?php endif; ?>
    
</div>
```

### Use Image-Ribbons

It is possible to place an image within the html. But you should always
try to sove this by css!

## License

MIT / BSD

## Author Information

 - Tobias Schifftner, [@tschifftner](https://twitter.com/tschifftner)