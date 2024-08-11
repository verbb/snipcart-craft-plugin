# Changelog

## 3.0.0 - 2024-05-13

### Changed
- Now requires PHP `8.2.0+`.
- Now requires Craft `5.0.0+`.

## 2.1.6 - 2024-08-11

### Fixed
- Fix an error with field validation not working correctly when not providing a price value.

## 2.1.5 - 2024-03-01

### Fixed
- Fix an error when migrating from Craft 3.
- Fix an error when generating buttons when overriding `class` attributes.
- Fix order of operations when uninstalling the plugin.

## 2.1.4 - 2024-01-31

### Fixed
- Fix `textEmailTemplate` typing. (thanks @tobystokes).
- Fix dashboard widget icon.

## 2.1.3 - 2024-01-23

### Added
- Add 404 handling for detail view of objects.
- Add french translations. (thanks @scandella).

### Fixed
- Fix a migration error.
- Fix Shipstation shipments.
- Fix display of “Total Spent” values.
- Fix metadata typing.

## 2.1.2 - 2023-12-19

### Added
- Add plugin setting to modify plugin name.
- Add `craft.snipcart.plugin` and `craft.snipcart.pluginName`.
- Add translations file.
- Add some missing English translations.

### Fixed
- Fix subscriptions viewing items.
- Fix an error for abandoned cart users.
- Fix welcome image alignment.
- Fix type errors for API keys.

## 2.1.1 - 2023-12-12

### Fixed
- Fix lack of `showPrice` for `craft.snipcart.cartLink()`.
- Fix URL param for buy now button.

## 2.1.0 - 2023-12-12
> {note} The plugin’s package name has changed to `verbb/snipcart`. Snipcart will need be updated to 1.7.0 from a terminal, by running `composer require verbb/snipcart && composer remove fostercommerce//craft-snipcart`.

### Changed
- Migration to `verbb/snipcart`.
- Now requires Craft 4.5+.

## 2.0.0 - 2023-09-11

### Added
- Add migration to move product data from the custom `product_details` table to Craft native content tables.
- Add `snipcart/cleanup console command to remove legacy `product_details` table when required.

### Changed
- Update plugin to work with Craft 4.
- Move to using native Craft content table instead of custom `product_details` table.

### Removed
- Removed legacy class alias for field type.

## 1.6.1 - 2023-09-14

### Changed
- Added back PHP 7.4 compatibility

## 1.6.0 - 2023-06-20

### Added
- Add compatibility with PHP 8.0

### Fixed
- Fixed customer counts in overview

## 1.5.7 - 2022-01-11

### Fixed
- Removed debug code left in the `ProductDetails` class

## 1.5.6 - 2021-11-26

### Fixed
- Fixed deprecation warning for `getSourceId()`

## 1.5.5 - 2021-07-09

### Changed
- `craft.snipcart.cartLink` now renders HTML passed as its first argument, not just text.
- `ShippingRateEvent` is now a `craft\events\CancelableEvent`. Set `isValid` to `false` to display an error message, which can be customized with [the `errors` property](https://docs.snipcart.com/v2/webhooks/shipping#error).

## 1.5.4 - 2021-03-05

### Removed
- Removed unnecessary warning log when transforming model data.

## 1.5.3 - 2021-02-28

### Fixed
- Fixed encoded onload value when loading Snipcart's JS.
- Fixed some Control Panel screens using the incorrect currency symbols.

## 1.5.2 - 2021-02-28

### Fixed
- Saving product details on non-default sites cleared the field data ([#31](https://github.com/FosterCommerce/snipcart-craft-plugin/issues/31))

## 1.5.1.1 - 2021-02-09

### Fixed
- Fixed composer and package plugin version number.

## 1.5.1 - 2021-02-01

### Fixed
- Fixed aliases to use new `@fostercommerce` instead of `@workingconcept`. Thanks @mattstein.

## 1.5.0 - 2021-01-22
> {warning} Links to deprecated classes have been removed. Be sure to update any custom modules or plugins relying on Snipcart prior to 1.4.0.

### Changed
- Changed `workingconcept` namespace to `fostercommerce`.

### Removed
- Removed deprecated class links to get rid of composer warnings.

## 1.4.4.1 - 2020-09-21

### Fixed
- Fixed an issue preventing new webhook events from being logged.

## 1.4.4 - 2020-09-21

### Added
- Added support for `order.refund.created` and `order.notification.created` webhooks.
- Added template hooks: `cp.snipcart.cart.detail`, `cp.snipcart.customer.detail`, `cp.snipcart.discount.detail`, `cp.snipcart.order.detail`, `cp.snipcart.subscription.detail`.

### Changed
- Uninstalling now properly removes all plugin data.

### Fixed
- Fixed an issue that prevented plugin from uninstalling successfully.

## 1.4.3.1 - 2020-09-08

### Fixed
- Fixed a bug that kept the Product Details currency symbol from being displayed.

## 1.4.3 - 2020-09-06

### Fixed
- Fixed a bug that could have misidentified duplicate SKUs in Craft 3.5. ([#21](https://github.com/workingconcept/snipcart-craft-plugin/issues/21))
- Updated Codeception setup, added simple unit tests.
### Changed
- Refactored format helper to do a better job returning an explicitly-requested currency’s symbol.

## 1.4.2 - 2020-08-29

### Added
- Exposed order item subscription details in control panel views.

### Fixed
- Various minor improvements for control panel templates.
- Product details `getBuyNowButton()` no longer requires a `|raw` Twig filter.

## 1.4.1.1 - 2020-08-01

### Fixed
- Recent Orders summary displays order completion dates rather than creation dates.

## 1.4.1 - 2020-08-01

### Fixed
- Fixed custom email notifications.
- Order notification email subjects are now translatable.
- Admin order email notifications will only display a ShipStation ID when it’s not empty. 

### Changed
- The Recent Orders summary now uses relative timestamps rather than `m/d` format.

## 1.4.0 - 2020-07-21
> {warning} This release re-namespaces some classes for PSR-4 compliance. If you’re using event hooks or other custom code relying on the `workingconcept\snipcart\models\*` or `workingconcept\snipcart\providers\*` namespaces, you may need to update those references.

### Fixed
- Product Details price is displayed and saved properly when a user’s preferred language is German. ([#17](https://github.com/workingconcept/snipcart-craft-plugin/issues/17))

### Changed
- Code quality improvements: cleanup, formatting, and minor refactoring.

### Deprecated
- `workingconcept\snipcart\models\Dimensions` is now `workingconcept\snipcart\models\snipcart\Dimensions`.
- `workingconcept\snipcart\models\Item` is now `workingconcept\snipcart\models\snipcart\Item`.
- `workingconcept\snipcart\models\Address` is now `workingconcept\snipcart\models\snipcart\Address`.
- `workingconcept\snipcart\models\OrderEvent` is now `workingconcept\snipcart\models\snipcart\OrderEvent`.
- `workingconcept\snipcart\models\DigitalGood` is now `workingconcept\snipcart\models\snipcart\DigitalGood`.
- `workingconcept\snipcart\models\Category` is now `workingconcept\snipcart\models\snipcart\Category`.
- `workingconcept\snipcart\models\Order` is now `workingconcept\snipcart\models\snipcart\Order`.
- `workingconcept\snipcart\models\Notification` is now `workingconcept\snipcart\models\snipcart\Notification`.
- `workingconcept\snipcart\models\Plan` is now `workingconcept\snipcart\models\snipcart\Plan`.
- `workingconcept\snipcart\models\Product` is now `workingconcept\snipcart\models\snipcart\Product`.
- `workingconcept\snipcart\models\Domain` is now `workingconcept\snipcart\models\snipcart\Domain`.
- `workingconcept\snipcart\models\Discount` is now `workingconcept\snipcart\models\snipcart\Discount`.
- `workingconcept\snipcart\models\Customer` is now `workingconcept\snipcart\models\snipcart\Customer`.
- `workingconcept\snipcart\models\AbandonedCart` is now `workingconcept\snipcart\models\snipcart\AbandonedCart`.
- `workingconcept\snipcart\models\SubscriptionEvent` is now `workingconcept\snipcart\models\snipcart\SubscriptionEvent`.
- `workingconcept\snipcart\models\Tax` is now `workingconcept\snipcart\models\snipcart\Tax`.
- `workingconcept\snipcart\models\ShippingEvent` is now `workingconcept\snipcart\models\snipcart\ShippingEvent`.
- `workingconcept\snipcart\models\PaymentSchedule` is now `workingconcept\snipcart\models\snipcart\PaymentSchedule`.
- `workingconcept\snipcart\models\CustomField` is now `workingconcept\snipcart\models\snipcart\CustomField`.
- `workingconcept\snipcart\models\ShippingRate` is now `workingconcept\snipcart\models\snipcart\ShippingRate`.
- `workingconcept\snipcart\models\ProductVariant` is now `workingconcept\snipcart\models\snipcart\ProductVariant`.
- `workingconcept\snipcart\models\TaxesEvent` is now `workingconcept\snipcart\models\snipcart\TaxesEvent`.
- `workingconcept\snipcart\models\UserSession` is now `workingconcept\snipcart\models\snipcart\UserSession`.
- `workingconcept\snipcart\models\CustomerStatistics` is now `workingconcept\snipcart\models\snipcart\CustomerStatistics`.
- `workingconcept\snipcart\models\Refund` is now `workingconcept\snipcart\models\snipcart\Refund`.
- `workingconcept\snipcart\models\ShippingMethod` is now `workingconcept\snipcart\models\snipcart\ShippingMethod`.
- `workingconcept\snipcart\models\Subscription` is now `workingconcept\snipcart\models\snipcart\Subscription`.
- `workingconcept\snipcart\models\Package` is now `workingconcept\snipcart\models\snipcart\Package`.
- `workingconcept\snipcart\providers\ShipStation` is now `workingconcept\snipcart\providers\shipstation\ShipStation`.

## 1.3.4 - 2020-06-23

### Added
- Added support for using Product Details fields in element queries.

### Changed
- Improved precision of price, weight, and dimensions by storing as decimals rather than floats.
- Orders without any shippable items are not sent to ShipStation.

### Fixed
- Fixed minor styling issues with price field in Craft 3.4.
- Fixed CSS inliner call during email rendering.

## 1.3.3 - 2020-05-18

### Changed
- Exceptions will be thrown if Snipcart’s API is erroring or unresponsive.

### Fixed
- Fixed error that could occur if a failed request did not include a response.
- Weightless Snipcart orders now report `0` weight to ShipStation rather than `null`.

## 1.3.2 - 2020-04-12

### Added
- Added support for Swiss Franc (CHF).
- Added `ShipStation::EVENT_BEFORE_SEND_ORDER` event for modifying the ShipStation order before it’s sent to their REST API.

### Changed
- ShipStation orders now include `carrierCode` only if a `serviceCode` is provided for the shipping method. This makes it possible to request custom shipping methods not provided by any carrier.

## 1.3.1 - 2020-02-29

### Fixed
- Fixed various date format issues in the control panel. (User’s preferred format is now honored.)
- Fixed Customer list search field display in Craft 3.4.
- Updated pagination style in control panel listings.

## 1.3.0 - 2020-01-17

### Added
- Added multi-site support for the Product Details field.
- Added support for Item `pausingAction` and `cancellationAction` properties.

### Fixed
- Email notifications display with item `unitPrice` and `totalPrice`.
- ShipStation orders are built with each item’s adjusted unit price.
- Fixed error that kept Product Details field from being used in Quick Post Dashboard widget.

### Changed
- Improved display of product options in email notification.
- Removed field delta saving to avoid bugs.
- Tidied up order notification email templates.

## 1.2.4 - 2019-12-12

### Fixed
- Fixed a type error that could prevent automatic quantity deprecation for non-shippable products. ([#13](https://github.com/workingconcept/snipcart-craft-plugin/issues/13))

## 1.2.3 - 2019-11-21

### Added
- Added support for Product Details delta saving in Craft 3.4+.

### Fixed
- Fixed missing `£` in some templates.

## 1.2.2 - 2019-11-08

### Added
- Added ability to force ShipStation re-feed attempts from the command line.
- Improved logging for ShipStation re-feed attempts.
- Console ShipStation verifier now has an optional `limit` argument.
- Added support for GBP `£`.

### Changed
- Console ShipStation verifier skips checking orders without shippable items.

## 1.2.1 - 2019-11-01

### Added
- Added support for test mode!
- Added `Discounts::updateDiscount()`.
- Added status constants to Snipcart Order model.

### Fixed
- Fixed a template bug that could have wrongly indicated an expired discount.
- Fixed an error when clearing the Snipcart API cache from the Clear Caches utility.
- Fixed a few template template display bugs where some details may not be present.
- Custom product options can now be plain text inputs. (No array of choices required.)

## 1.2.0 - 2019-10-17

### Added
- Added GraphQL support to Product Details fields.
- Exposed shipping data re-feed attempt window as a configurable setting.

### Fixed
- Minor code improvements.

## 1.1.4 - 2019-09-23

### Fixed
- Removed a changed API reference that caused an error in the Abandoned Cart list.

## 1.1.3 - 2019-08-15

### Fixed
- Fixed a query error that could prevent Product Details fields from saving.

## 1.1.2 - 2019-07-06

### Fixed
- Added support for Craft 3.2.0-RC2.

## 1.1.1 - 2019-06-02

### Fixed
- Fixed a template bug that caused the Customers search field to disappear when there were no results.

## 1.1.0 - 2019-05-31

### Deprecated
- `InventoryEvent::$entry` is now deprecated. Use `InventoryEvent::$element` instead.
- `Products::reduceProductInventory()` is now deprecated. Use `Products::reduceInventory()` instead, which takes a single Snipcart Item as an argument.
- `Orders::updateElementsFromOrder()` is now deprecated. Use `Orders::updateProductsFromOrder()` instead.

### Added
- Added Matrix support for Product Details field.
- Added ability to provide a custom `name` and `url` in `getBuyNowButton()`, which defaults to Entry or parent Entry’s Title and URL.

### Fixed
- Product Details SKU is now properly validated to be unique.

## 1.0.7 - 2019-04-28

### Added
- Added code to prevent Snipcart API changes from resulting in control panel errors.

### Fixed
- Fixed minor control panel view inconsistencies.
- Fixed an error that could occur if ModelHelper::stripUnknownProperties() received non-iterable data.
- Fixed a bug that prevented API response cache from being disabled.
- Added a new Discount property that might have thrown errors in the control panel.

### Changed
- Updated charting library and made minor stylistic and readability improvements.

## 1.0.6.1 - 2019-03-18

### Fixed
- Fixed a bug that affected chart’s date range display.

## 1.0.6 - 2019-03-18

### Added
- Added store performance chart to the CP section and made date range editable.
- Improved dashboard widget charts.
- Added `FormatHelper::formatCurrency()` and `craft.snipcart.formatCurrency()` for consistent currency display that honors default store currency setting.

### Changed
- Optimized AssetBundles.

### Fixed
- Fixed minor padding issues for the very last elements in some control panel views.

## 1.0.5 - 2019-03-10

### Added
- `getBuyNowButton()` can now take an `image` parameter.
- `cartLink()` supports a `showCount` setting for optionally removing the cart button’s dynamic item count.

### Changed
- `cartSnippet()` now includes Snipcart’s base theme stylesheet by default.
- `getBuyNowButton()` now adds `.btn` as a default that can be removed.

## 1.0.4 - 2019-03-09

### Added
- Added Twig template methods: `craft.snipcart.getCustomer()`, `craft.snipcart.getOrder()` and `craft.snipcart.getSubscription()`.
- Added ability to override Twig `getBuyNowButton()` price with support for multiple currencies.
- `getBuyNowButton()` can now include custom options with negative price adjustments.

### Fixed
- Currency setting is now saved properly.
- Improved consistency of currency values displayed in the control panel and email templates.
- Fixed UnknownPropertyException when viewing Discounts because of new `normalizedRate` property.

## 1.0.3 - 2019-03-05

### Fixed
- Fixed a bug where passing a `null` value for Product Details `customOptions` would throw a warning in PHP 7.2. 

## 1.0.2 - 2019-03-04

### Fixed
- Fixed bug populating existing Element’s product detail.

## 1.0.1 - 2019-03-03

### Added
- Added support for pre-3.1 versions of Craft CMS.

### Fixed
- Fixed an issue that would cause a Section re-save task to fail after a Product Details field is added to an existing Section.
- Product defaults are honored correctly per field setting on new and existing entries.
- Fixed a JS error in Product Details field settings.

## 1.0.0 - 2019-02-27

### Changed
- Removed beta tag! 🎉

## 1.0.0-beta.27 - 2019-02-27

### Fixed
- Improved safety of CraftQL check.

## 1.0.0-beta.26 - 2019-02-27

### Fixed
- Fixed Install migration to prevent blocking re-install.

### Changed
- Added a nicer configured+empty landing state graphic.

## 1.0.0-beta.25 - 2019-02-26

### Fixed
- Cleaned up docblocks and variable names for consistency.

### Changed
- Required endpoint parameter for `get()` , `post()`, `put()`, and `delete()` API service methods.

## 1.0.0-beta.24 - 2019-02-24

### Fixed
- Fixed a bug that kept static config settings from counting toward a configured state.

## 1.0.0-beta.23 - 2019-02-24

### Added
- Added pagination support to Abandoned Carts.
- Added a friendlier CP section empty state before plugin is configured.

### Changed
- Ajaxified CP landing stat panels to speed up page load.
- Spiffed up the Craft Commerce comparison table in the readme.

### Fixed
- Fixed template error when `shipFrom` settings are empty.
- Fixed incorrect reference that interfered with subscription invoice creation webhook.
- Invalid/unparsed environment variables won’t count as a “configured” state for the plugin.

## 1.0.0-beta.22 - 2019-02-18

### Added
- Added Notifications service.

### Fixed
- Fixed bug in console Snipcart → ShipStation verification utility.

## 1.0.0-beta.21 - 2019-02-17

### Added
- Added CraftQL support for field data.
- Improved support for [Webhooks plugin](https://github.com/craftcms/webhooks).

### Changed
- Isolated API caches with TagDependency.
- Refactored webhooks into component.

### Fixed
- Stopped inventory event from firing for products that don’t store inventory.

## 1.0.0-beta.20 - 2019-02-17

### Added
- Added support for additional AbandonedCart attributes.

## 1.0.0-beta.19 - 2019-02-16

### Added
- Added Fields service.

### Fixed
- Improved webhook resilience in some cases when incoming payloads contain unexpected attributes.

## 1.0.0-beta.18 - 2019-02-15

### Added
- Added new Order and Item attributes.

## 1.0.0-beta.17 - 2019-02-14

### Added
- Added inventory to the Product Details field type.
- Added the ability to designate a custom admin order notification email template.
- Webhook log now stores `mode`.
- Added support for displaying Subscriptions and cancelling them from the control panel.
- Added Overview tab for control panel section.
- Added Event hook for registering shipping providers.
- Some settings now offer env and template suggestions.
- Added environment variable support for Snipcart + ShipStation API keys.

### Changed
- Flattened migrations into single Install.
- Improved several control panel views.
- Optimized control panel assets.
- Vastly improved speed and flexibility of Dashboard widget.
- Refactored control panel views.

### Removed
- Deleted many SnipcartVariable methods after refactor.
- Cleaned up Orders interface, removing several methods.
- Removed ability to define custom product fields.
- Removed unused Packaging Types.

## 1.0.0-beta.16 - 2018-12-27

### Added
- Added Product Details field type for quick setup.
- Added control panel views for Discounts, Abandoned Carts, and Subscriptions.
- Added ability to create a Discount via control panel.

### Changed
- Improved plugin settings control panel layout.
- Refactored and expanded Events.
- References to `WebhookEvent` should now be `ShippingRateEvent`.

## 1.0.0-beta.15 - 2018-12-24

### Changed
- Refactored ShippingProvider to expose REST API methods.
- Various code quality improvements.

### Fixed
- Fixed incorrect item weights when converting a Snipcart order into a ShipStation order.

## 1.0.0-beta.14 - 2018-12-20

### Changed
- ShipStation’s `_getOrderNotes()` and `_getGiftNote()` will no longer return empty values.

## 1.0.0-beta.13 - 2018-12-20

### Changed
- **Breaking changes for everyone!**
- Massively refactored services and models, which will definitely break any services or models you’re using directly.
- Renamed all ShipStation models and moved them to their own namespace.
- Renamed all Snipcart models.
- `WebhookEvent`’s `packaging` property is now `package`.
- Abstracted ShipStation service into Shipments, meaning it’s now accessed via `Snipcart::$plugin->shipments->shipStation`. Note that the intent is for other services to interact directly with Shipments, to which `EVENT_BEFORE_RETURN_SHIPPING_RATES` has moved. Listeners should subscribe to `Shipments::EVENT_BEFORE_RETURN_SHIPPING_RATES`.
- Listeners should now subscribe to `Orders::EVENT_BEFORE_REQUEST_SHIPPING_RATES` instead of `SnipcartService::EVENT_BEFORE_REQUEST_SHIPPING_RATES`.
- Listeners should now subscribe to `Products::EVENT_PRODUCT_INVENTORY_CHANGE` instead of `SnipcartService::EVENT_PRODUCT_INVENTORY_CHANGE`.

## 1.0.0-beta.12 - 2018-12-18

### Fixed
- Fixed missing ShipStation fields, prevent wrapping additional email prices.

## 1.0.0-beta.11 - 2018-12-17

### Fixed
- Fixed token verification.

## 1.0.0-beta.10 - 2018-12-17

### Changed
- VerifyController requests un-cached Snipcart orders.

## 1.0.0-beta.9 - 2018-12-17

### Added
- Spiffed up and added re-feed attempt status to order failure notifications.

### Changed
- Added explicit type coercion in a few places.

### Fixed
- Fixed type error that impacted VerifyController.
- Reverted ShipStationOrderItem `fields()`.

## 1.0.0-beta.8 - 2018-12-17

### Added
- Separated parts of SnipcartService into new ApiService.

### Changed
- Changed the way API exceptions are handled to reduce disruption and log failures.
- Refactored SnipcartService to be cleaner.
- Renamed SnipcartService’s `processShippingRates()` to `getShippingRatesForOrder()`.
- Models now use proper DateTime values.
- Improved ShipStation order verifier accuracy.
- Updated webhook controller’s `handleOrderCompletedEvent()` to continue through problems and report errors by model. Any errors at all will result in `success: false`.
- Renamed `listAbandoned` template variable to `listAbandonedCarts`.

### Fixed
- Minor fix for mobile order email price wrapping.

## 1.0.0-beta.7 - 2018-12-15

### Added
- Added package detail to Snipcart rate response.

### Changed
- Use billingAddressName instead of cardholderName in order notification emails.
- Return JSON for all webhook requests.
- Keep ShipStation service from failing if Snipcart order has `null` value for custom fields.
- Rename webhook controller’s `badResponse()` to `badRequestResponse()`.

### Fixed
- Fix type issues with SnipcartOrder model.
- Return magic variables when SnipcartOrder is treated as an array.
- Respond calmly to missing webhook event names or content and don’t allow logging.

## 1.0.0-beta.6 - 2018-12-14

### Added
- Added weight property to SnipcartItem model.
- Added hasPhysicalDimensions() for both Snipcart and ShipStation item models.

### Changed
- Changed ShipStation service method names to better reflect what they do.

### Fixed
- Fixed incorrect docblock details.

## 1.0.0-beta.5 - 2018-12-13

### Changed
- ShipStationService’s getWeightFromSnipcartData() is now getWeightFromSnipcartOrder().

## 1.0.0-beta.4 - 2018-12-13

### Changed
- Improved code quality throughout models.

### Fixed
- Fixed SnipStation gift setting detection.

## 1.0.0-beta.3 - 2018-12-13

### Changed
- Made cosmetic fixes to console order verification tool.
- ShipStation order model no longer limits string length; longer customer and gift messages won’t cause webhook failure.

### Fixed
- Fixed webhook and service bugs.

## 1.0.0-beta.2 - 2018-12-13

### Changed
- Improved class documentation.
- Improved console verification tool.
- Improved code quality with optimizations and type hints.

### Fixed
- Fixed several incorrect references.

## 1.0.0-beta.1 - 2018-12-10

### Added
- Initial GitHub release.
