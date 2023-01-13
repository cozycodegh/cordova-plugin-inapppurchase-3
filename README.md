# cordova-plugin-inapppurchase-3 📱💰

Repository: [https://github.com/cozycodegh/cordova-plugin-inapppurchases](https://github.com/cozycodegh/cordova-plugin-inapppurchases)

```
cordova plugin add cordova-plugin-inapppurchases
```

Updated __2023__ for [Cordova](https://cordova.apache.org/) with current:<br>
__Android__: *Billing Library 5* (released May 2022) (verifies receipts internally)<br>
__iOS__: *StoreKit* (not StoreKit 2, released 2021, which is only available for iOS 15 and up) (does not verify receipts currently - but returns them)<br>
__Amazon Fire__: compatible, but untested <br>
__Browser__: not implemented<br>
__Windows__: not implemented <br>

***Cordova*** plugin to add ***in-app purchases*** (and ***subscriptions***) into an app. <br>
Use javascript to view, make, and complete purchases.

If you notice any issues, submit here: [github issues](https://github.com/cozycodegh/cordova-plugin-inapppurchases/issues)<br>
Based on the original plugin working for many years made by Alex Disler, it is out of date for the latest apps:<br> [`cordova-plugin-inapppurchase`](https://github.com/AlexDisler/cordova-plugin-inapppurchase)<br>
Forked from another plugin, which is kept updated as well, if this plugin is broken, try this plugin:<br> [`cordova-plugin-inapppurchase2`](https://github.com/wccrawford/cordova-plugin-inapppurchase-2)<br>

<hr/>

See more from `cordova-plugin-inapppurchases` (3rd plugin based on cordova-plugin-inapppurchase-2):

[https://github.com/cozycodegh/cordova-plugin-inapppurchases](https://github.com/cozycodegh/cordova-plugin-inapppurchases)

<hr/>

Forked from `cordova-plugin-inapppurchase-2`:

A lightweight Cordova plugin for in app purchases on iOS/Android. See [demo app](https://github.com/AlexDisler/cordova-inapppurchases-app) and [blog post](https://alexdisler.com/2016/02/29/in-app-purchases-ionic-cordova/).

## Features

- Simple, promise-based API
- Support for consumable/non-consumable products and paid/free subscriptions
- Support for restoring purchases
- Uses well tested native libraries internally - [RMStore](https://github.com/robotmedia/RMStore) for iOS

## Configuration

### iOS

No configuration is necessary.

### Android

You must create a ```manifest.json``` in your project's ```www``` folder with your Android Billing Key:

    { "play_store_key": "<Base64-encoded public key from the Google Play Store>" }

You can get this key from the Google Play Store (under "Services & APIs") after uploading your app.

## Setting up and testing purchases

- [Configuring Cordova in app purchases on iOS and Android](https://alexdisler.com/2016/04/30/configuring-in-app-purchases-cordova-ionic-ios-android/)
- [Testing in app purchases](https://alexdisler.com/2016/04/04/testing-cordova-in-app-purchases-on-ios-android/)
- [Tips for signing and running Cordova apps on Android to test in app purchases locally](https://alexdisler.com/2016/04/01/tips-for-signing-installing-cordova-apps-on-android/)

See [Differences Between Product Types](https://developer.apple.com/library/ios/documentation/NetworkingInternet/Conceptual/StoreKitGuide/Chapters/Products.html)

<!--
### Get Receipt

#### inAppPurchase.getReceipt()

On ***iOS***, you can get the receipt at any moment by calling the getReceipt() function. Note that on iOS the receipt can contain multiple transactions. If successful, the promise returned by this function will resolve to a string with the receipt.

On ***Android*** this function will always return an empty string since it's not needed for Android purchases.

___Example:___

```js
inAppPurchase
  .getReceipt()
  .then(function (receipt) {
    console.log(receipt);
  })
  .catch(function (err) {
    console.log(err);
  });
``` -->

## Debugging

- Are you testing on a real device? In App purchases are not supported in emulators/simulators.
- Have you enabled In-App Purchases for your App ID?
- Have you checked Cleared for Sale for your product?
- Does your project’s .plist Bundle ID match your App ID?
- Have you generated and installed a new provisioning profile for the new App ID?
- Have you configured your project to code sign using this new provisioning profile?
- Have you waited several hours since adding your product to iTunes Connect?
- Have you tried deleting the app from your device and reinstalling?
- Have you accepted contracts for IAPs in iTunes connect?
- Is your device jailbroken? If so, you need to revert the jailbreak for IAP to work.

## Thanks / Credits

- [Robot Media](https://github.com/robotmedia)

## License

The MIT License

Copyright (c) 2016, Alex Disler

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
