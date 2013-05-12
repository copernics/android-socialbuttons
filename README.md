Facebook Like Button
=============================

A simple Facebook Like Button for Android, with shares count.

![Screenshot](https://github.com/gcacace/android-facebook-sharesbutton/raw/master/screenshot.png)

## Features
 * No Facebook SDK needed
 * No tricky WebView
 * Native Facebook App detection
 * Shares count in a formatted Facebook style
 * Localized in english, french, german, italian and spanish

Android 2.2+ support
 
## Quick Setup

#### 1. Include library

**Manual:**
 * Clone this GIT repository
 * Import both library and demo to Eclipse
 * In Eclipse, right click on your personal project and go to Properties, then to the Android tab
 * Add the library to the dependency list

or

**Maven dependency:**
``` xml
<dependency>
	<groupId>it.gcacace.facebook.sharesbutton</groupId>
	<artifactId>library</artifactId>
	<version>0.1</version>
</dependency>
```

#### 2. Android Manifest
``` xml
<manifest>
	<uses-permission android:name="android.permission.INTERNET" />
	...
	<application android:name="MyApplication">
		...
	</application>
</manifest>
```

### 3. Add view to your application

**With URL inside XML:**
``` xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    xmlns:fbshares="http://schemas.android.com/apk/res/it.gcacace.facebook.sharesbutton.demo">
	...
    <it.gcacace.facebook.sharesbutton.SharesButton
        android:id="@+id/sharesButton1"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        fbshares:sharesUrl="http://www.facebook.com/" >
    </it.gcacace.facebook.sharesbutton.SharesButton>
	...
</LinearLayout>
```

or

**With URL specified programmatically:**
``` java
@Override
protected void onCreate(Bundle savedInstanceState) {
	super.onCreate(savedInstanceState);
	setContentView(R.layout.activity_main);
	...
	// Find the second SharesButton from the inflated layout
	SharesButton sharesButton = (SharesButton) findViewById(R.id.sharesButton2);
	
	// Set sharesUrl to an URL
	sharesButton.setSharesUrl("http://mobile.fanpage.it/segui-la-diretta-del-google-i-o-2103/");
	
	// Fetch the shares count (this call is asynchronous)
	sharesButton.fetchShares();
	...
}
```

## License

    Copyright 2013 Gianluca Cacace

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

       http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.