# jquery-responsiveShopifyImg
Responsive image support for Shopify stores based on Shopify's provided image sizes.

Suggested primarily for responsive background-image sizing on sites that can rely on users having JS enabled.

## Usage
Simply assign the `data-shopify-src` attribute to any element with a valid shopify image URL. The script will choose wether to apply the chosen size's url as an `src` attribute or as a `background-image: url()` style depending on the type of element.

## Example
```HTML
<img data-shopify-src="//cdn.shopify.com/s/files/1/xxxx/xxxx/files/img_1024x1024.jpg" alt="Responsive" />
<script>
  $("[data-shopify-src]").responsiveShopifyImg();
</script>
```

## Warnings & Caveats
Because this is a javascript solution you will need to trust that your users have JS enabled, or use a `<noscript>` fallback. Without a fallback if somehting goes wrong the image will not load at all. You may use a default Shopify image URL in your `src` attribute or `background-image` property, however know that it will be loaded by the browser before the plugin runs, thus potentially downloading multiple image sizes and wasting your user's bandwidth.

The better solution if you don't need to support older browsers would be to use HTML5 techniques such as the `<picture>` element or `srcset` and `sizes` attributes.

This is only mildly tested and was scrapped for the time being on our own project. Please don't hesitate to fork this and tinker with it, clean it up, etc. Send any pull requests back that you see fit.
