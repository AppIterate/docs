# Android SDK - API Documentation

## SDK setup

### Copy Files

* Copy `appiteratesdk.jar` to project's lib folder and add its path in your build path
* Copy `httpmime` and `gson` library from the jar to project's lib folder if not already present in the project.

### Create settings file

Create `appiterate.xml` in project's resources in xml folder

### Strings in appiterate.xml

```XML
<appiterate>
    <appkey>{{APP_KEY}}</appkey>
    <debug>true</debug>
    <variables>
        <key>variable1</key>
        <key>variable2</key>
</appiterate>
```

* APP_KEY: Retrieve your application key from the 
<a href="http://dashboard.appiterate.com" target="_blank">dashboard</a>
* debug: set this to 'true' during development and 'false' for production
* variables: variables you will use for DDT testing

### Adding Required Permission in AndroidManifest.xml

```XML
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE"/>
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE"/>
<uses-permission android:name="android.permission.INTERNET"/>
<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
```

### Data Driven Tests

Create a test on the dashboard. Keep a note of Short name, which you mention at the time of creating a test. To retrieve parameters defined on your "Test Details" page, use getValue function defined in our SDK.

```JAVA
getValue(Context context, String variableName, String defaultValue) : String
```
