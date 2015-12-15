# Material Design Android Template

First of all, a few screenshots:

Smartphone          |  Tablet
:-------------------------:|:-------------------------:
![Smartphones](http://www.andreas-schrade.de/assets/external/screen-nexus5.jpg)  |  ![Tablet](http://www.andreas-schrade.de/assets/external/screen-tablet.jpg)

Collapsing Toolbar          |  Navigation Drawer
:-------------------------:|:-------------------------: 
![Smartphones](http://www.andreas-schrade.de/assets/external/animation1.gif)  |  ![Smartphones](http://www.andreas-schrade.de/assets/external/screen-nexus5-2.jpg) 

Support Design Library Views          |  Preferences
:-------------------------:|:-------------------------: 
![Smartphones](http://www.andreas-schrade.de/assets/external/animation2.gif)  |  ![Smartphones](http://www.andreas-schrade.de/assets/external/screen-nexus5-3.jpg) 


## What is this?

This is a State of the Art Android Material Design template. You can use this project as a template for upcoming App projects. Just clone the project, change package name and make all necessary customisations. 


## Dependencies

The focus of this project lies on the view layer and app navigation. It uses the following dependencies:

- AppCompat Support Library
- Support Design Library
- Support Card View Library
- Butterknife
- Glide 

## Supported devices

The template support every device with a SDK level of at least 14 (Android 4+).


## Quick walkthrough

### Gradle

Nothing special here. Please note that the version of the support library is extracted to *gradle.properties*:

```xml
    compile "com.android.support:appcompat-v7:${android_support_lib_version}"
    compile "com.android.support:design:${android_support_lib_version}"
    compile "com.android.support:cardview-v7:${android_support_lib_version}"

    compile 'com.github.bumptech.glide:glide:3.6.1'
    compile 'com.jakewharton:butterknife:7.0.1'
```

### Manifest

There are only three Activities declared. The main theme is *@style/Theme.Main*.

### Theme

The project contains three *styles.xml*.

1. res/values/styles.xml  (basic colors, styles)
2. res/values-v21/styles.xml  (contains Android 5 statusbar/systembar features)
3. res/values-sw600dp-land/styles.xml (used for tablet layout)

You can easily change the colors of your app. You only have to set the color values in colors.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="theme_primary_accent">#8BC34A</color>
    <color name="theme_primary_dark">#1976D2</color>
    <color name="theme_primary_light">#2196F3</color>
    <color name="theme_window_background">#FFF5F5F5</color>
    <color name="theme_divider">#B6B6B6</color>

    <color name="primary_text">#212121</color>
    <color name="secondary_text">#727272</color>
</resources>
```

### Navigation

The navigation drawer is configured in *menu/drawer_view.xml*:

```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <group android:checkableBehavior="single">
        <item
            android:id="@+id/nav_quotes"
            android:icon="@drawable/ic_discuss"
            android:title="@string/navigation_quotes" />
        <item
            android:id="@+id/nav_samples"
            android:icon="@drawable/ic_forum"
            android:title="@string/navigation_samples" />
            ... 
```



### Base classes

*BaseActivity* is the parent class for every *Activity* inside this template. This class creates and provides the navigation drawer and toolbar.

*BaseFragment* is the parent for every *Fragment* class. It is responsible for view inflating and view binding (via ButterKnife).

### Quotes View

The *ListActivity* is the start *Activity* and supports two differend layout modes:

1. One pane mode: Used on devices with a small screen size. The Activity shows only a list of all available quotes.
2. Two pane mode: Used on tablets and every device with a high screen size (>= 600dp width). The Activity shows the list of quotes and displays the selected item in a seperate Fragment.

### Settings

The *SettingsActivity* represents some dummy preferences. You can easily configure your settings by modifying the *settings_prefs.xml*.

### View Samples

The *ViewSamplesActivity* shows some stuff from the Support Design Library.

Butterknife is not only used for view binding, furthermore it is also used for configuring click listeners:

```java
    @OnClick(R.id.fab)
    public void onFabClicked(View view) {
       // floating action button clicked
    }
```

For example, the following snippet (ArticleDetailFragment.java) binds automatically the view:
```java
    @Bind(R.id.quote)
    TextView quote;

    @Bind(R.id.author)
    TextView author;

    @Bind(R.id.backdrop)
    ImageView backdropImg;

    @Bind(R.id.collapsing_toolbar)
    CollapsingToolbarLayout collapsingToolbar;
```

## About
My name is <a href="http://www.andreas-schrade.de">Andreas Schrade</a> and I am a freelance software developer with an interest in Android and Java backend development.







 

