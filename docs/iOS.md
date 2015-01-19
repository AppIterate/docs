# iOS SDK - API Documentation

## SDK setup

* Download the [iOS SDK](http://appiterate.com/ios/latest)
* The SDK comes with two files: `Appiterate.h` and `Appiterate.a`. Include both of them in your project.
* Add the following frameworks to your project:
    * libsqlite3.0.dylib
    * ibz.dylib
    * CoreLocation.framework
    * Security.framework
* Add the following compier flag:
    * ObjC

![alt text](img/ios-project.png "ios-project")

## Initialize SDK

* Add the following lines to the `AppDelegate` of the application.

```objective-c
[Appiterate initAppiterate:@"APP_KEY" isDebug:YES]
```

* The SDK must be initalized before initializing application window and user interfaces.
* `APP_KEY`: Retrieve your application key from the
<a href="http://dashboard.appiterate.com" target="_blank">dashboard</a>.
* isDebug: set this to `YES` during development and `NO` for production.

```objective-c
-(BOOL)application:(UIApplication *)application
 didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
 {
   //Appiterate SDK Initialization
   [Appiterate initAppiterate:@"b62d5a2057f21e5b465e5ccadc1c8f72" isDebug:YES];

   self.window = [[[UIWindow alloc] initWithFrame:[[UIScreenmainScreen] bounds]]autorelease];

   // Override point for customization after application launch.
   self.viewController = [[[ViewController alloc]
   initWithNibName:@"ViewController" bundle:nil] autorelease];
   self.window.rootViewController = self.viewController;

   [self.window makeKeyAndVisible];

   return YES;
 }
```

## Push Notifications