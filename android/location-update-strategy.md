#Location Update Strategy

### Location API

Basically, there are two options to get location updates in Android: **Android’s Location API** and **Google’s Location Services API**. Google’s Location Services API is a part of the Google Play Services. They’re built on top of Android’s API. This provider automatically chooses what underlying provider to use, based on accuracy, battery usage, etc. It is fast because you get a location from a system-wide service that keeps updating it. Android recommends devs to use Google's Location Services, and LocationRequest particularly.


### Conditions 

> Every app's usecase is different and business need defines what constraints to use and how frequently app should request for location updates.

- You define an **UPDATE_INTERVAL** value and use it with **setInterval()**. This tells Location Services how often to send you updates.

- If another app is receiving location updates at the same time, Location Service could make them available to your app as well. You set an **FASTEST_UPDATE_INTERVAL** value that ensures that your app never receives updates faster than this value. (It may happen if another app uses GPS at the same time with faster update interval, for example, Google Maps. For example, you start your application and register it via setInterval(60*1000), that means that you'll get updates every 60 seconds. Now you call setFastestInterval(10*1000). If you are the only app which use the location services you will continue to receive updates every 60 seconds. If another app is using the location services with a higher rate of updates, you will get more location updates.)

- Finally, you use the **MAX_WAIT_TIME** value with **setMaxWaitTime().** This tells Location Services that it should batch location updates. I.e., it should collect location updates as specified in **setInterval()**, but deliver them to your app in batches. Using batching makes your app more battery friendly. (Basically, we can set an *interval* to, for example, 5 seconds, and *max wait time* to 1 minute. So each 1 minute we'll be getting a callback method `onLocationUpdate` called with a list of all locations (30 in this case), so we can process all of them at the same time. It will save battery, as we will not process each location update every 5 seconds using a database and so on.)