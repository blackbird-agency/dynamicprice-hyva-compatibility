# Blackbird Dynamic Price Hÿva Compatibility

[![Latest Stable Version](https://img.shields.io/packagist/v/blackbird/dynamicprice-hyva-compatibility.svg?style=flat-square)](https://packagist.org/packages/blackbird/dynamicprice-hyva-compatibility)
[![License: MIT](https://img.shields.io/github/license/blackbird-agency/dynamicprice-hyva-compatibility.svg?style=flat-square)](./LICENSE.txt)

Compat module for Blackbird Dynamic Price on Magento 2 using a Hyvä Theme. The product page sub-total (unit price for
the chosen quantity × quantity, computed by the Dynamic Price controller: tier prices, customer group, catalog price
rules, chosen variant of a configurable product) is displayed with Alpine.js and Tailwind CSS, without jQuery.
This requires:
- A [Hyvä Theme](https://www.hyva.io/) license
- A License to [Blackbird Dynamic Price](https://store.bird.eu/)

The module is only active on Hyvä themes (Hyvä compat module fallback); a Luma store is not affected.

## Requirements

* PHP >= 8.1
* Hÿva Theme: ^1.3
* Blackbird Dynamic Price version: ^1.2.4

## Behaviour on Hyvä

* Display positions (`Stores > Configuration > Catalog > Catalog > Dynamic Price on Catalog Product Page > Display`):
  * **under sku**: next to the stock status,
  * **under price**: under the price / add to cart row, left of the wishlist and compare buttons,
  * **under add to cart button**: under the add to cart button.
* Settings used: loader, delay (a delay of 0 is replaced by 250 ms so that typing a quantity sends one request).
  The Luma selectors (product form, qty field, sub-total container) are not used: the Hyvä product page is fixed.
* Shown for simple, virtual and configurable products (once a variant is chosen). Not shown for bundle and
  downloadable products: the Dynamic Price controller ignores bundle selections and downloadable links.

## Setup

Get the package

Composer Package:
```composer require blackbird/dynamicprice-hyva-compatibility```

Zip Package:
Unzip the package in app/code/Blackbird/DynamicPriceHyvaCompatibility, from the root of your Magento instance.


## Install the module

Go to your Magento root directory and run the following magento commands:

```
php bin/magento setup:upgrade
php bin/magento hyva:config:generate
```

Then rebuild the Tailwind CSS of your Hyvä theme (`npm run build` in `web/tailwind`) so the module's templates are
included.

## Support

- If you have any issue with this code, feel free to [open an issue](https://github.com/blackbird-agency/dynamicprice-hyva-compatibility/issues/new).
- If you want to contribute to this project, feel free to [create a pull request](https://github.com/blackbird-agency/dynamicprice-hyva-compatibility/compare).

## Contact

For further information, contact us:

- by email: support@bird.eu
- or by form: [https://black.bird.eu/en/contacts/](https://black.bird.eu/contacts/)

## Authors

- [**Blackbird Team**](https://github.com/blackbird-agency) - *Maintainer* -

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.txt) file for details.

***That's all folks!***
