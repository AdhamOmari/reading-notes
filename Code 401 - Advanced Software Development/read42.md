# Read: 42 - Location

- Using the Google Play services location APIs, your app can request the last known location of the user's device.

### Set up Google Play services

- To access the fused location provider, your app's development project must include Google Play services.

- Download and install the Google Play services component via the SDK Manager and add the library to your project.

### Specify app permissions

- Apps whose features use location services must request location permissions, depending on the use cases of those features.

### Create location services client

- In your activity's onCreate() method, create an instance of the Fused Location Provider Client

### Get the last known location

- Once you have created the Location Services client you can get the last known location of a user's device. When your app is connected to these you can use the fused location provider's getLastLocation() method to retrieve the device location.

### Get the last known location

### Create location services client

- In your activity's `onCreate()` method, create an instance of the Fused Location Provider Client as the following code snippet shows.

```java
private FusedLocationProviderClient fusedLocationClient;


## Choose the best location estimate

- The FusedLocationProviderClient provides several methods to retrieve device location information. Choose from one of the following, depending on your app's use case:

- getLastLocation() gets a location estimate more quickly and minimizes battery usage that can be attributed to your app. However, the location information might be out of date, if no other clients have actively used location recently.
getCurrentLocation() gets a fresher, more accurate location more consistently. However, this method can cause active location computation to occur on the device

- This is the recommended way to get a fresh location, whenever possible, and is safer than alternatives like starting and managing location updates yourself using requestLocationUpdates(). If your app calls requestLocationUpdates(), your app can sometimes consume large amounts of power if location isn't available, or if the request isn't stopped correctly after obtaining a fresh location.