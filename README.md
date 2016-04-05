# SimpleHttp
[![Release](https://jitpack.io/v/joecheatham/SimpleHttp.svg)](https://jitpack.io/#joecheatham/SimpleHttp)

A simple and easy to use HTTP requests library for Android.

## Quick Start
### Include the following in your root build.gradle file
```
allprojects {
		repositories {
			...
			maven { url "https://jitpack.io" }
		}
	}
```
### Add the following dependency to your app's build.gradle file
```
dependencies {
	        compile 'com.github.joecheatham:SimpleHttp:v1.0'
	}
```
## Usage
First, make sure that you add
```
<uses-permission android:name="android.permission.INTERNET" /> 
```
to your Manifest file.

To make a `GET` request:
```
SimpleHttp.get("http://example.com", new SimpleHttpResponseHandler() {
	@Override
    onResponse(int resultCode, String responseBody) {
    	// to handle response as a JSONObject:
        JSONObject json = new JSONObject(responseBody);
        // to handle response as a JSONArray:
        JSONArray json = new JSONArray(responseBody);
    }
});
```

To make a `POST` request:
```
Map<String, String> params = new HashMap<String, String>();
params.put("paramName", "paramValue");
SimpleHttp.post("http://example.com", params, new SimpleHttpResponseHandler() {
	@Override
    onResponse(int resultCode, String responseBody) {
    	// to handle response as a JSONObject:
        JSONObject json = new JSONObject(responseBody);
        // to handle response as a JSONArray:
        JSONArray json = new JSONArray(responseBody);
    }
});
```