=== ByteRub WooCommerce Extension ===
Contributors: miltonf
Tags: byterub, woocommerce, integration, payment, merchant, cryptocurrency, accept monerv, byterub woocommerce
Requires at least: 4.0
Tested up to: 4.8
Stable tag: trunk
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html
 
ByteRub WooCommerce Extension is a Wordpress plugin that allows to accept bitcoins at WooCommerce-powered online stores.

== Description ==

An extension to WooCommerce for accepting ByteRub as payment in your store.

= Benefits =

* Accept payment directly into your personal ByteRub wallet.
* Accept payment in byterub for physical and digital downloadable products.
* Add byterub payments option to your existing online store with alternative main currency.
* Flexible exchange rate calculations fully managed via administrative settings.
* Zero fees and no commissions for byterub payments processing from any third party.
* Automatic conversion to ByteRub via real time exchange rate feed and calculations.
* Ability to set exchange rate calculation multiplier to compensate for any possible losses due to bank conversions and funds transfer fees.

== Installation ==

1. Install "ByteRub WooCommerce extension" WordPress plugin just like any other WordPress plugin.
2. Activate
3. Setup your byterub-wallet-rpc with a view-only wallet
4. Add your byterub-wallet-rpc host address and ByteRub address in the settings panel
5. Click “Enable this payment gateway”
6. Enjoy it!

== Remove plugin ==

1. Deactivate plugin through the 'Plugins' menu in WordPress
2. Delete plugin through the 'Plugins' menu in WordPress

== Screenshots == 
1. ByteRub Payment Box
2. ByteRub Options

== Changelog ==

= 0.1 =
* First version ! Yay!

= 0.2 =
* Bug fixes

== Upgrade Notice ==

soon

== Frequently Asked Questions ==

* What is ByteRub ?
ByteRub is a finite, completely private, cryptographically secure, digital cash used across the globe. See https://byterub.org for more information

* What is a ByteRub wallet?
A ByteRub wallet is a piece of software that allows you to store your funds and interact with the ByteRub network. 

* What is byterub-wallet-rpc ?
The byterub-wallet-rpc is an RPC server that will allow this plugin to communicate with the ByteRub network. 

* Why do I see `[ERROR] Failed to connect to byterub-wallet-rpc at localhost port 19090
Syntax error: Invalid response data structure: Request id: 1 is different from Response id: ` ?
This is most likely because this plugin can not reach your byterub-wallet-rpc. Make sure that you have supplied the correct host IP and port to the plugin in their fields. If your byterub-wallet-rpc is on a different server than your wordpress site, make sure that the appropriate port is open with port forwarding enabled.
