# AdsPro Module for Android Applications

This README provides instructions on how to integrate the AdsPro module into your Android application. This module helps you to display various types of advertisements in your app, such as interstitial, native, banner, and app open ads. Follow the steps below to implement the AdsPro module in your project.

[![N|Solid](https://i.ibb.co/pxWCrh4/Frame-23.png)](https://hkapps.io)
> [![version](https://img.shields.io/badge/version-3.6-pass.svg)](https://hkapps.io)


## Prerequisites
* Android Studio
* An existing Android application project

## Installation

### Step 1: Add the dependency to your project's `build.gradle` file
> To add the AdsPro module as a dependency, insert the following line in your project's `build.gradle` file under the `dependencies` section:

```
implementation(group: 'com.hkapps', name: 'adsprolib', version: '3.6', ext: 'aar') {
    transitive = true;
}
```

### Step 2: Initialize the module in your Splash or Launcher Activity
> Add the following code snippet to your Splash or Launcher activity's `onCreate` method:

```
MobileAds.initialize(this, () -> {
    MobileAds.showSplashAd(SplashActivity.this, new MobileAds.OnResult() {
        @Override
        public void onResult(String value) {
            // Goto another activity or continue work
        }
    });
});

```

## Usage

### Show Interstitial Ads
> To display interstitial ads, add the following code snippets to your desired activity:
> Forward:

```
MobileAds.showInter(this, new MobileAds.OnResult() {
    @Override
    public void onResult(String value) {
        // TODO NEXT TO CALL
    }
});
```

> Backward:

```
MobileAds.showBackInter(MainActivity.this, new MobileAds.OnResult() {
    @Override
    public void onResult(String value) {
        // TODO NEXT TO CALL
    }
});
```

### Show Native Ads
> To display native ads with different sizes and layouts, add the following code snippets to your desired activity. Replace `yourLayoutReference` with the reference to your layout:

```
MobileAds.showNative(this, yourLayoutReference, "BIG_NATIVE");
MobileAds.showNative(this, yourLayoutReference, R.layout.customise_big_layout, "BIG_NATIVE");
MobileAds.showNative(this, yourLayoutReference, "SMALL_NATIVE");
MobileAds.showNative(this, yourLayoutReference, R.layout.customise_small_side, "SMALL_NATIVE");
```

### Show Banner Ads
> To display banner ads with different sizes and layouts, add the following code snippet to your desired activity. Replace `yourLayoutReference` with the reference to your layout:

```
MobileAds.showBanner(this, yourLayoutReference, "BIG_NATIVE");
MobileAds.showBanner(this, binding.bannerContain, "SMALL_NATIVE");
```

### Show App Open Ads
> Caution: Do not implement this ad directly. If needed, discuss with the admin first.

```
MobileAds.showOpenAd(this);
```

### Get App Settings
> To get app settings from the server, use the following code snippet:

```
MobileAds.getAppSetting("PrivacyPolicy"); // Add the key you need to get the value from the server
```

## That's it! You have successfully integrated the AdsPro module into your Android application. Now you can easily display various types of advertisements within your app.
