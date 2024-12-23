### <mark style="background: #AD21D9;">Geographical Co-ordinates:</mark>

To locate object on Earth’s surface, geographical coordinates are needed.  

<mark style="background: #AD21D9;">Most common solution assigns 3 coordinates to each location:</mark> 
- latitude, 
- longitude 
- altitude (km above sea level).  

Earth assumed to be perfect sphere with known radius R.  

Latitude and longitude represents angles (in degrees) of location on surface, with respect to Earth centre.

### <mark style="background: #AD21D9;">Latitude:</mark>

- Equator: 0°  
- North Pole: 90°  
- South Pole: - 90°

![](https://i.imgur.com/uW4lOvH.png)

Loosely speaking, latitude contributes to y (or vertical) component of location.

### <mark style="background: #AD21D9;">Longitude:</mark>

Longitude measures x (or <mark style="background: #AD21D9;">horizontal</mark>) component

Longitude measures x (or horizontal) component.  

Imaginary line that connects Poles passing through Greenwich called Prime Meridian.

![](https://i.imgur.com/5svtV71.png)

Prime Meridian 0°  

Increases <mark style="background: #AD21D9;">Eastwards</mark> to Antipodal Prime Meridian  
at 180°  

Decreases <mark style="background: #AD21D9;">Westwards</mark> Antipodal Prime Meridian: at -180°

![](https://i.imgur.com/9nkqjnJ.png)

### <mark style="background: #AD21D9;">Geographical Co-ordinates:</mark>

![](https://i.imgur.com/YX4wlYQ.png)

![](https://i.imgur.com/QLQvuni.png)

![](https://i.imgur.com/1cLgWmg.png)

### <mark style="background: #AD21D9;">Location:</mark>

Finding location in space of object <mark style="background: #AD21D9;">difficult</mark>.  

No traditional sensor able to locate an object.  

What most sensors do is <mark style="background: #AD21D9;">estimate</mark> distance from target object.  

Sonars and radars send out sound waves and calculate distance by detecting <mark style="background: #AD21D9;">how long</mark> it takes for their signal to bounce back.  

Satellites basically do the same, but using radio waves.

### <mark style="background: #AD21D9;">Solution:</mark>

Solution to locate object relies on <mark style="background: #AD21D9;">several</mark> distance measurements, taken by different <mark style="background: #AD21D9;">sensors</mark>.  

<mark style="background: #AD21D9;">Trilateration</mark>, common technique used to calculate position of object given distance measurements.  

<mark style="background: #AD21D9;">Note:</mark> Another technique called <mark style="background: #AD21D9;">Triangulation</mark> works with angles instead of distances.

### <mark style="background: #AD21D9;">How it Works:</mark>

Suppose we want to find location <mark style="background: #AD21D9;">P</mark>  

Our 1st try uses beacon L, at <mark style="background: #AD21D9;">known</mark> position.  

L can estimate its distance to P, d  

Cannot identify <mark style="background: #AD21D9;">exact</mark> position of P.

![](https://i.imgur.com/ZKKhYFW.png)

Each point at distance d from L is <mark style="background: #AD21D9;">potential</mark> candidate for P.  

Guess for P limited to circle of <mark style="background: #AD21D9;">radius</mark> d around P.

![](https://i.imgur.com/HKIZ15f.png)

Situation <mark style="background: #AD21D9;">improved</mark> by using 2 beacons, L1 & L2.  

We <mark style="background: #AD21D9;">know</mark> P lies along circumference of red circle.  

Similarly, <mark style="background: #AD21D9;">must</mark> be on circumference of green circle

![](https://i.imgur.com/v7CbJrH.png)

Means it has to be at <mark style="background: #AD21D9;">intersections</mark> of 2 circles.  

This suddenly restricts our guess to <mark style="background: #AD21D9;">only two</mark> possible locations.

![](https://i.imgur.com/F3c9uL2.png)

To be absolutely precise, need a 3rd station, L3.  

3 circles will meet at only one point i.e. location of P

![](https://i.imgur.com/pByoVzR.png)

### <mark style="background: #AD21D9;">Global Positioning System GPS:</mark>

Constellation of 27 Earth-orbiting satellites 24 operational + 3 extras  

1½ ton solar-powered units circle globe twice daily at 19,300 km.  

Orbits arranged so, at any time, in any place, at least 4 satellites "visible" in sky.  

GPS receiver's job to locate 4 or more of satellites, figure out distance to each, and use information to estimate its location.

<mark style="background: #AD21D9;">Trilateration Principle also applies in 3D:</mark>

![](https://i.imgur.com/GL0c2KH.png)

At given time (e.g. midnight), satellite begins <mark style="background: #AD21D9;">transmitting</mark> long, digital pattern called a pseudo-random code.  

Receiver begins running <mark style="background: #AD21D9;">same</mark> digital pattern also exactly at midnight.  

When satellite's signal reaches receiver, its transmission of the pattern will <mark style="background: #AD21D9;">lag</mark> a bit behind receiver's playing of pattern.  

Length of <mark style="background: #AD21D9;">delay</mark> is equal to signal's travel time.

Receiver multiplies this time by <mark style="background: #AD21D9;">speed of light</mark> to determine how far signal travelled.  

Assuming signal travelled in <mark style="background: #AD21D9;">straight line</mark>, this is distance from receiver to satellite.  

NOTE: A GPS receiver has to have clear <mark style="background: #AD21D9;">line of sight</mark> to satellite to operate, so dense tree cover and buildings can keep it from getting fix on location.

### <mark style="background: #AD21D9;">WiFi Positioning System (WPS):</mark>

WPS is geolocation system that uses characteristics of WiFi hotspots and other wireless access points to discover where device located.  

Used when satellite navigation such as GPS inadequate:  
1. Multipath <mark style="background: #AD21D9;">interference</mark> / signal blockage indoors.  
2. Establishing a satellite fix would take too long.  

Viable due to <mark style="background: #AD21D9;">rapid growth</mark> of wireless access points in urban areas.

Typical data useful to geolocate wireless access point include its SSID and MAC address:
![](https://i.imgur.com/pgvVwjE.png)

Accuracy depends on number of nearby access points whose positions have been entered into <mark style="background: #AD21D9;">database</mark>

<mark style="background: #AD21D9;">Sample WiFi Hotspots London:</mark>
![](https://i.imgur.com/ZC3XGcl.png)

Many techniques exist to determine <mark style="background: #AD21D9;">distance</mark> or <mark style="background: #AD21D9;">angle</mark> of client devices with respect to access points.  
1. Received signal strength indication (RSSI)  
2. Fingerprinting  
3. Angle of arrival (AoA)  
4. Time of flight (ToF)  

Trilateration or Triangulation <mark style="background: #AD21D9;">algorithms</mark> then be used to determine position of target device.

Database links BSSID to Latitude and Longitude location.  

Then used with e.g. trilateration to get device position.

### <mark style="background: #AD21D9;">Overview:</mark>

A unique feature of mobile apps is location <mark style="background: #AD21D9;">awareness</mark>.  

Users take devices with them everywhere, so app can detect and use device location to customise experience for them.  

Location <mark style="background: #AD21D9;">APIs</mark> available in Google <mark style="background: #AD21D9;">Play</mark> Services for adding:  
1. Location Tracking  
2. Geofencing  
3. Activity Recognition

![](https://i.imgur.com/dEf4Oau.png)

### <mark style="background: #AD21D9;">Battery Drain:</mark>

Location gathering and battery drain are directly related as follows:  
1. <mark style="background: #AD21D9;">Accuracy:</mark> Precision of location data. Higher accuracy, higher battery drain.  
2. <mark style="background: #AD21D9;">Frequency:</mark> How often location is computed. Frequent location computations, more battery used.  
3. <mark style="background: #AD21D9;">Delay:</mark> How quickly location data is delivered. Less delay requires more battery.

### <mark style="background: #AD21D9;">Accuracy:</mark>

In <mark style="background: #AD21D9;">Request</mark> to <mark style="background: #AD21D9;">FusedLocation</mark> API for location updates, use ``setPriority()``  

![](https://i.imgur.com/2k0JRu6.png)

Most accurate location. Computed using as many inputs as necessary e.g. GPS, Wi-Fi, cell and other sensors. May cause significant battery drain

![](https://i.imgur.com/rkRnKC5.png)

Accurate location (within 100m) while optimising for power. Very rarely uses GPS. Typically combination of Wi-Fi and Cell information.

![](https://i.imgur.com/4TqesaZ.png)

Largely relies on cell towers and avoids GPS and Wi-Fi inputs, providing coarse (city-level, within 10km) accuracy with minimal battery drain.

![](https://i.imgur.com/Y06I5ZB.png)
Receives locations passively from other apps for which location has already been computed.

Location needs of most apps can be <mark style="background: #AD21D9;">satisfied</mark> using balanced power or low power options.  

High accuracy should be reserved for apps running in <mark style="background: #AD21D9;">foreground</mark> and require <mark style="background: #AD21D9;">real time</mark> location updates (e.g. Mapping app).

### <mark style="background: #AD21D9;">Frequency:</mark>

In <mark style="background: #AD21D9;">Request</mark> to Fused Location API for location updates configure ``setinterval()`` with interval at which location is computed for your app.  

Use <mark style="background: #AD21D9;">largest</mark> possible value for the interval.  

Especially true for <mark style="background: #AD21D9;">background</mark> location gathering, often a source of unwelcome battery drain.  

Intervals of a few seconds should be <mark style="background: #AD21D9;">reserved</mark> for foreground use cases.

### <mark style="background: #AD21D9;">Delay:</mark>

In Request to Fused Location API for location updates use ``setMaxWaitTime()``  

Pass a value several times larger than interval used in ``setInterval()``  

Locations determined at ``setInterval()`` rate, but delivered in batch after interval set in this method.

### <mark style="background: #AD21D9;">Location Updates:</mark>

![](https://i.imgur.com/QwfDIil.png)

1.) Create Request to store details of  
location updates.

![](https://i.imgur.com/0yqQ3yM.png)

2.) Implement callback for action when location updates arrive.

![](https://i.imgur.com/ulJ859p.png)

3.) Get hold of Location Services.

![](https://i.imgur.com/kCMwqna.png)

4.) Ask it for Fused Location Provider Client.

![](https://i.imgur.com/DPCfQ8g.png)

5.) Request Location Updates with Request and Callback as arguments.

![](https://i.imgur.com/2RPrual.png)

6.) Hardware feeds location data into system and Location object created.
![](https://i.imgur.com/FBT8i6n.png)

7.) Gets stored in list with Locations recorded at other times.
![](https://i.imgur.com/x5DdkNn.png)

8.) Based on delay settings callback called by system with Location Result.

![](https://i.imgur.com/wqtQMwC.png)

9.) Perform action e.g. draw marker on a map
![](https://i.imgur.com/Sz25frX.png)

10.) When no longer needed, best practice to remove updates.
![](https://i.imgur.com/n6yBZud.png)

### <mark style="background: #AD21D9;">Best Practices</mark>

<mark style="background: #AD21D9;">Remove Location Updates:</mark>  
- Common source of unnecessary battery drain is failure to remove location updates when no longer needed.  
- Can happen if activity’s ``onStart()`` or ``onResume()`` methods request location updates without call to remove them in ``onStop()`` or ``onPause()``

<mark style="background: #AD21D9;">Set Timeouts:</mark> 
- Set reasonable timeout when location updates should <mark style="background: #AD21D9;">stop</mark>.  
- Timeout ensures updates don't continue <mark style="background: #AD21D9;">indefinitely</mark> e.g. in scenarios where updates requested but not removed (due to a bug).  
- In Request, add timeout using ``setExpirationDuration()``, which takes value for time in milliseconds <mark style="background: #AD21D9;">since</mark> method was last called.

<mark style="background: #AD21D9;">Batch Requests:</mark>  
- For non-foreground use cases, batch multiple requests together.  
- Use ``setInterval()`` to specify interval at which location be computed.  
- Then, ``setMaxWaitTime()`` to set interval at which location is delivered to app.  
- Value passed to ``setMaxWaitTime()`` multiple of that for ``setInterval()``

![](https://i.imgur.com/JRfQQO1.png)

Location computed roughly every 10 mins. and 6 location data points delivered in batch per hour.  

Still get location updates every 10 minutes, battery conserved because device woken up only once an hour.

### <mark style="background: #AD21D9;">Permissions:</mark>

Apps must request location permission in Manifest:
![](https://i.imgur.com/iPq0IYZ.png)

``ACCESS_COARSE_LOCATION`` for location accurate to within city block  

``ACCESS_FINE_LOCATION`` for precise location

<mark style="background: #AD21D9;">From Marshmallow onwards:</mark>  
- Users grant or deny access to their location for each app.  
- Users can change access permission at any time.  
- Your app can prompt user to grant permission to use location.

![](https://i.imgur.com/EUMyRWZ.png)

User can revoke permission at <mark style="background: #AD21D9;">any time</mark>.  

Check for permission <mark style="background: #AD21D9;">each time</mark> your app uses location

### <mark style="background: #AD21D9;">Things to note about the code:</mark>

A careful choice of these values can make a difference to power consumption and to how your application works:  

``minTime``:  Specifies frequency of location checks 
- Wise choice of value for ``minTime`` will help you reduce power consumption.  
- Elapsed time between location updates will never be less than ``minTime``.  

``minDistance``: This parameter can be turned off by setting its value to 0. However, if ``minDistance`` is set to a value greater than 0, location provider will only send updates to your application if location has changed at least by given distance.  

This parameter is driven by functional requirement of the app

### <mark style="background: #AD21D9;">EXAMPLE:</mark>

Location set up to ``minTime`` of 5 minutes, and using a minimum distance of 1 kilometres

Write the “requestupdates” statement code to set this up

Android app location locates a user at point A, at 9am.  

When does ``onLocationChanged`` method trigger :  
- At 9:02am, the user has moved 10 kilometres to point B;  
- At 9:03, the user is returning back to A and is 5 kilometres away.  
- At 9:05am, the user has moved back to point A again;  
- At 9:07am, the user has moved 20 kilometres from point A  
- At 9:10am, the user has moved 40 kilometres from point A

### <mark style="background: #AD21D9;">Beware of the battery:</mark> 

Battery life limited  

Location updates ``very Power hungry``  

Each provider – GPS, Wifi, Cell based location – separately absorbing battery life  

Only check location when your activity needs to. e.g. Hidden activity doesn’t.  

Use lifecycle methods to stop and start location updates - see code sample:  
- ``onPause()`` - stop updates  
- ``onResume()`` – start up updates again

### <mark style="background: #AD21D9;">Permissions:</mark>

Every Android app runs in a limited-access sandbox.  

App needs permissions to user resource or info outside its sandbox -e.g. sending SMS, location tracking, contacts, Access  

All permissions must be published/listed in the manifest file

![](https://i.imgur.com/lIiXRM1.png)

### <mark style="background: #AD21D9;">Permissions – pre API 23:</mark>

<mark style="background: #AD21D9;">All permissions were dealt with at install time:</mark>  
- All permissions were listed in manifest 
- User prompted at install time  
- User couldn’t revoke  
- Developers started to abuse by asking for too many!

### <mark style="background: #AD21D9;">Permissions – 2 types (API 23 onwards):</mark>

<mark style="background: #AD21D9;">Normal permissions:</mark>  
- Permission needed to get outside user sandbox
- Low risk to user privacy e.g. connecting to the internet, Bluetooth, wifi, and NFC information, setting alarms & wallpapers, modifying audio settings on a device etc.  
- Automatically granted at install time – no user prompt  

<mark style="background: #AD21D9;">Runtime (also called Dangerous):</mark>  
- Dangerous permissions = permissions which could potentially affect the user’s privacy;  
- The user must explicitly agree to grant those permissions. E.g. camera, contacts, location
- Declare in the manifest file
- User can revoke permissions at any run session (i.e. Change their mind...)  
- Must check permission at run time

### <mark style="background: #AD21D9;">Run time check for Dangerous permission (inc location)</mark>

e.g. for location tracking:
![](https://i.imgur.com/jjpZ1ix.png)

### <mark style="background: #AD21D9;">Handle the permissions request response:</mark>

When the user responds to your app's permission request, the system invokes the ``onRequestPermissionsResult()`` method, passing it the user response.  

Need to override that method to find out whether the permission was granted.

![](https://i.imgur.com/bMWHENO.png)

### <mark style="background: #AD21D9;">Location tracking permission:</mark>

<mark style="background: #AD21D9;">ACCESS_COARSE_LOCATION</mark>  
- E.g. Cell_ID, Wifi – 1K-ish  
- ``<uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />``
- (If you don’t, security violation error not well flagged... Difficult to diagnose!)  
- Two AndroidManifest.XML permissions involved:

<mark style="background: #AD21D9;">ACCESS_FINE_LOCATION</mark>  
- More specific e.g. 10m  
- e.g. GPS  
- ``<uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />``

### <mark style="background: #AD21D9;">Emulator: Mocking up location</mark>

It’s not a real device  

Need to artificially feed in mocked up GPS coordinates  

This tests the location tracker, location listener etc.

![](https://i.imgur.com/bVcvBsa.png)

### <mark style="background: #AD21D9;">GeoCoding:</mark>

![](https://i.imgur.com/8FGgBiT.png)

Longitude: -122.0840  
Latitude: 37.4220  

Reverse Geocoded to:  “1600, Mountview, California, United States”  

<mark style="background: #AD21D9;">Geocoded:</mark>  
- Longitude: -122.0840  
- Latitude: 37.4220

![](https://i.imgur.com/eoJXdx9.png)

<mark style="background: #AD21D9;">Sample Code:</mark>
```Kotlin
// get a geocoder object  
Geocoder geo = new Geocoder(MainActivity.this.getApplicationContext(),  
Locale.getDefault());  
// call the method to translate GPS to address(es)..  
List<Address> addresses = geo.getFromLocation(location.getLatitude(),  
location.getLongitude(), 1);  
if (addresses.size() > 0)  
{  
String addressName = addresses.get(0).getFeatureName() + ", " +  
addresses.get(0).getLocality() + ", " +  
addresses.get(0).getAdminArea() + ", " +  
addresses.get(0).getCountryName();  
}
```

### <mark style="background: #AD21D9;">GeoCode class:</mark>

To use geocoding, get a GeoCode object of the Geocode class

``Geocoder(Context context, Locale locale)`` : Constructs a Geocoder whose responses will be localised for the given Locale

Then, pass in the latitude, longitude to the ``getFromLocation`` method of this class

``getFromLocation(double latitude, double longitude, int maxResults)``: Returns an array of Addresses that are known to describe the area immediately surrounding the given latitude and longitude

### <mark style="background: #AD21D9;">Summary</mark>

Location aware app examples  

<mark style="background: #AD21D9;">Implementing location awareness:</mark>  
- Location providers – GPS, Wifi, Cell  
- LocationManager 
- Criteria/ Best provider..  

minTime/ maxtime  

Battery life – use onPause() and onResume()  

Emulator - mocking up location  

GeoCoding