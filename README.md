Cordova plugin for ShowKit
================

Integrate video chat and screensharing into your Cordova application in less than 10 minutes!

Supported platforms
---

* IOS

Installation and running the example/demo
----

Replace the `cordova` command with `ionic` to get the same results for an Ionic based project.
Note that demo and plugin is tested on Cordova CLI 4.0.0 and Ionic CLI 1.2.8.

1. Create/start a new Cordova app by typing into Terminal:  
`cordova create showkit-test` or for Ionic `ionic start showkit-test`

2. Change working directory to your newly created application
`cd showkit-test`

3. Install ShowKit plugin into your application:
`cordova plugin add https://github.com/showkit/cordova-plugin-showkit.git`
> If you get an error that the plugin already exists, do the following to remove the plugin and update it:: `cordova plugin remove com.showkit.cordova.showkit`

4. Add IOS as a platform
`cordova platform add ios`

5. Copy the contents from 'plugins/com.showkit.cordova.showkit/example/www/' to your projects 'www' directory (showkit-test/www)
> **NOTE:** Ionic users should at least clean the projects 'www' directory first

6. Add you ShowKit API key to the file 'showkit-test/www/js/index.js' 
    ```
        onDeviceReady: function() {
            app.receivedEvent('deviceready');        
            var apiKey = "INSERT_YOUR_API_KEY_HERE";
            ShowKit.initializeShowKit(apiKey);
        },
    ```
7. Prepare project for IOS build
`cordova prepare ios`

8. Open the file 'showkit-test/platforms/ios/showkit-test.xcodeproj' in Xcode and **add** `-lc++` to the `Other Linker Flags`, see next:
> **NOTE:** Change this settings for the showkit-test target (not project)
![Building IOS project, solve linker errors](http://oi58.tinypic.com/2sbtyqd.jpg)

9. Go to http://showkit.com/releases and download the latest ShowKit iOS Framework.  Unzip and drag the ShowKit.framework and ShowKitResources.bundle file to your XCode project Frameworks
![Manually copy framework and bundle files](http://i59.tinypic.com/8x7kap.png)
