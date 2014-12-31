# AppIterate - API Documentation

Welcome to the AppIterate API docs page. These pages contain the reference materials for Android and iOS SDK.
The documentation is organized into sections which contain instruction to setup and use the SDK. These sections are DDT tests, WYSIWYG tests, Push Notifications, In-App Messages, Inbox.

## Android

### SDK setup

#### Copy Files

* Copy appiteratesdk.jar to project's lib folder and add its path in your build path
* Copy httpmime library and gson library from the jar to project’s lib folder if not already present in the project.

#### Create settings file

Create appiterate.xml in project's resources in xml folder

#### Strings in appiterate.xml

```XML
<appiterate>
    <appkey>{{APP_KEY}}</appkey>
    <debug>true</debug>
    <variables>
        <key>variable1</key>
        <key>variable2</key>
</appiterate>
```

* APP_KEY: Retrieve your application key from the dashboard
* debug: set this to 'true' during development and 'false' for production
* variables: variables you will use for DDT testing

#### Adding Required Permission in AndroidManifest.xml

```XML
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
```

#### Data Driven Tests

Create a test on the dashboard. Keep a note of Short name, which you mention at the time of creating a test. To retrieve parameters defined on your "Test Details" page, use getValue function defined in our SDK.

```JAVA
getValue(Context context, String variableName, String defaultValue) : String
```

## iOS