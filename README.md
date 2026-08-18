# acquire-sdk-maven

Public Maven repository for the AcquireSDK Android library (`com.acquireio:core`),

## Using the SDK in your app

Video installation guide: https://youtu.be/TQUzOvgazS0

```groovy
repositories {
    maven { url 'https://acquireio.github.io/acquire-sdk-maven' }
}

dependencies {
    implementation 'com.acquireio:core:2.4.3'
}
```


Initialize it from your `Application` subclass:

```java
public class TestApp extends Application {
    @Override
    public void onCreate() {
        super.onCreate();
        AcquireApp.setShowDefaultFAB(true);
        AcquireApp.init(this, "YOUR_ACCOUNT_ID");
    }
}
```

- `AcquireApp.init(this, "YOUR_ACCOUNT_ID")` — replace with your Acquire account ID.
- `AcquireApp.setShowDefaultFAB(true)` — shows the SDK's built-in floating chat
  button; it's off by default. Requires your app's theme to be `Theme.AppCompat`
  (or a descendant) — otherwise it crashes on inflation.
