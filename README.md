# ByterubWP
A WooCommerce extension for accepting ByteRub

## Dependencies
This plugin is rather simple but there are a few things that need to be set up beforehand.

* A web server! Ideally with the most recent versions of PHP and mysql

* A ByteRub wallet. You can find the official wallet [here](https://byterub.org)

* [WordPress](https://wordpress.org)
WordPress is the backend tool that is needed to use WooCommerce and this ByteRub plugin

* [WooCommerce](https://woocommerce.com)
This ByteRub plugin is an extension of WooCommerce, which works with WordPress

* [BCMath](http://php.net/manual/en/book.bc.php)
A PHP extension used for arbitrary precision maths

## Step 1: Activating the plugin
* Downloading: First of all, you will need to download the plugin. You can download the latest release as a .zip file. If you wish, you can also download the latest source code from GitHub. This can be done with the command `git clone` or can be downloaded as a zip file from the GitHub web page.

* Unzip the file byterubwp_release.zip if you downloaded the zip from the releases page.

* Put the plugin in the correct directory: You will need to put the folder named `byterub` from this repo/unzipped release into the WordPress plugins directory. This can be found at `path/to/wordpress/folder/wp-content/plugins`

* Activate the plugin from the WordPress admin panel: Once you login to the admin panel in WordPress, click on "Installed Plugins" under "Plugins". Then simply click "Activate" where it says "ByteRub - WooCommerce Gateway"

## Step 2 Option 1: Use your wallet address and viewkey

* Get your ByteRub wallet address starting with '4'
* Get your wallet secret viewkey from your wallet

A note on privacy: When you validate transactions with your private viewkey, your viewkey is sent to (but not stored on) byterubexplorer.com over HTTPS. This could potentially allow an attacker to see your incoming, but not outgoing, transactions if he were to get his hands on your viewkey. Even if this were to happen, your funds would still be safe and it would be impossible for somebody to steal your money. For maximum privacy use your own byterub-wallet-rpc instance.

## Step 2 Option 2: Get a ByteRub daemon to connect to

### Option 1: Running a full node yourself

To do this: start the ByteRub daemon on your server and leave it running in the background. This can be accomplished by running `./byterubd` inside your ByteRub downloads folder. The first time that you start your node, the ByteRub daemon will download and sync the entire ByteRub blockchain. This can take several hours and is best done on a machine with at least 4GB of ram, an SSD hard drive (with at least 40GB of free space), and a high speed internet connection.

### Option 2: Connecting to a remote node
It is probably easiest to use the official remote node which will automatically connect you to a random node.

### Setup your ByteRub wallet-rpc

* Setup a ByteRub wallet using the byterub-wallet-cli tool. 

* Create a view-only wallet from that wallet for security.

* Start the Wallet RPC and leave it running in the background. This can be accomplished by running `./byterub-wallet-rpc --rpc-bind-port 19092 --disable-rpc-login --log-level 2 --wallet-file /path/viewOnlyWalletFile` where "/path/viewOnlyWalletFile" is the wallet file for your view-only wallet. If you wish to use a remote node you can add the `--daemon-address` flag followed by the address of the node. 

## Step 4: Setup ByteRub Gateway in WooCommerce

* Navigate to the "settings" panel in the WooCommerce widget in the WordPress admin panel.

* Click on "Checkout"

* Select "ByteRub GateWay"

* Check the box labeled "Enable this payment gateway"

* Check either "Use ViewKey" or "Use byterub-wallet-rpc"

If You chose to use viewkey:

* Enter your ByteRub wallet address in the box labeled "ByteRub Address". If you do not know your address, you can run the `address` command in your ByteRub wallet

* Enter your secret viewkey in the box labeled "ViewKey"

If you chose to use byterub-wallet-rpc:

* Enter your ByteRub wallet address in the box labeled "ByteRub Address". If you do not know your address, you can run the `address` command in your ByteRub wallet

* Enter the IP address of your server in the box labeled "ByteRub wallet RPC Host/IP"

* Enter the port number of the Wallet RPC in the box labeled "ByteRub wallet RPC port" (will be `19092` if you used the above example).

Finally:

* Click on "Save changes"


