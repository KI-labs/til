
### Encountered Errors and Solutions



* Getting error when trying to run androidTest : `error: attribute 'android:name' in <instrumentation> tag must be a valid Java class name.`
  > Solution: You are not using `testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"` in your `app/build.gradle`
