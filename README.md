ajaxify-cart
============

Snippet to ajaxify Your Shopify Cart.

(Use this only if your theme does not already use Ajax, of course.)

The following themes have been confirmed to work with the 'ajaxify-cart' solution without any configuration:

* Minimal
* New Standard

How to install
==============

Create a new snippet called **ajaxify-cart**. Paste in it the content of the ajaxify-cart.liquid file. 

Then, include the ajaxify-cart snippet in your theme by pasting the code below in your <a href="http://www.shopify.com/admin/themes/current?key=layout/theme.liquid">theme.liquid</a> file right above your `</body>` tag:

`{% include 'ajaxify-cart' %}`

How to configure (optional)
================

No configuration is necessary, but if you want or need to change a few things, go into your snippet and, at the bottom of it, change how the `Shopify.AjaxifyCart.init()` method is called, by passing to it a configuration object.

Things you can change:

*  `addToCartBtnLabel`

    Final label on add that cart button after the ajax request, so that you can add more. You could change that to 'Added to bag' for example. Default is `Add to cart`.
  
*  `addedToCartBtnLabel`

   Label on add to cart button that shows for howLongTillBtnReturnsToNormal milliseconds after item has been added to the cart. Default is `Thank you!`.

*  `addingToCartBtnLabel`

   Label on add to cart button while item is being added to the cart. Default is `Adding...`.

*  `soldOutBtnLabel`

   Label on add to cart button when all of the item's stock is in the cart. Default is `Sold Out`.

*  `howLongTillBtnReturnsToNormal`

   Time during which the add to cart button label is addedToCartBtnLabel. Default is `2000`. In milliseconds.

*  `cartCountSelector`

   CSS selector for the element on the page that contains the cart count to update after Ajax request.

*  `cartTotalSelector`

   CSS selector for the element on the page that contains the cart total to update after Ajax request.

*  `feedbackPosition`

   Where to position the feedback after the Ajax request. There are 3 possible values: 
   
   * `aboveForm` for top of add to cart form, 
   * `belowForm` for below the add to cart form, and 
   * `nextButton` for next to add to cart button. 
   
   The default is `nextButton`.

The configuration object can contain any of the above.

Example, if you wish to position the feedback above the add to cart form, and you wish to use 'Added to bag' as button label when the item has been added to the cart, use the following code:

```javascript
Shopify.AjaxifyCart.init({ 
  feedbackPosition: 'aboveForm', 
  addedToCartBtnLabel: 'Added to bag' 
});
```
