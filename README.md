# Android SliderView Sample App
This is a sample Android project to demonstrate how to use Android Slider library created by sung2063.<br/>
The sample app includes using of <b>Horizontal and Vertical CarouselViews</b> and <b>SlideshowView</b>.

## Screenshots

<center>
  <table>
    <tr style="border-collapse: collapse;">
      <td><img src="screenshots/horizontal_carousel.jpg" width="275"/></td>
      <td><img src="screenshots/vertical_carousel.jpg" width="275"/></td>
      <td><img src="screenshots/slideshow.jpg" width="275" /></td>
    </tr>
    <tr>
      <td>Horizontal Carousel</td>
      <td>Vertical Carousel</td>
      <td>Slideshow</td>
    </tr>
   </table>
 </center>
 
 
 ## GIF Images

<center>
  <table>
    <tr style="border-collapse: collapse;">
      <td><img src="gifs/horizontal_carousel.gif" width="250" /></td>
      <td><img src="gifs/vertical_carousel.gif" width="250" /></td>
    </tr>
    <tr>
      <td>Horizontal Carousel</td>
      <td>Vertical Carousel</td>
    </tr>
   </table>
 </center>


## Instruction

1) Clone the AndroidSliderViewSample repository to your local computer
2) Open the project on Android Studio
3) Run the program either on Android virtual device or your Android device 

## How To Use Slider Views

<b>1. Setup your Android project setting</b>

Minimum SDK Version: 21 or greater (Update in your <i>app level</i> `build.gradle`)<br/>
Supported Programming Language: Java
Add following snippet code in your <i>project level</i> `build.gradle`.
```gradle
android {
    compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
    }
}
```
<br/><br/>
<b>2. Add required library</b>

First, include following jitpack url inside maven block in your <i>project level</i> `build.gradle`.
```gradle
allprojects {
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

Next, add the SliderViews and required libraries in <i>app level</i> `build.gradle` and sync the gradle file. 
```gradle
implementation 'com.github.sung2063:AndroidSliderViewsLibrary:1.3'
implementation 'com.google.android.material:material:1.1.0'
```

Now you are ready to use SliderView Library. You can start creating CarouselView and SlideshowView.<br/>

### CarouselView

CarouselView can be used for your application intro and show multiple images or videos in one layout with scrolling. CarouselView by Sliders library supports both horizontal and vertical scrolls.

First, create a CarouselView in your xml file.
```xml
<com.sung2063.sliders.carousel.CarouselView
        android:id="@+id/carousel_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:scrollDirection="horizontal"
        app:showIndicator="true"
        app:showSlideNumber="true"
        app:slideNumberTextSize="40" />
```
Set `scrollDirection` attribution to `horizontal` for creating horizontal carousel and `vertical` for vertical carousel.

In your `onCreate()` method in Activity, create your own custom layouts, add layouts to List<ViewGroup>, and start the carousel. You can add up to 10 layouts in the CarouselView. 
```java
CarouselView carouselView = findViewById(R.id.carousel_view);

// Create your own layouts...
// Create List<ViewGroup> object...
// Add your layouts to list object...

carouselView.setSlideList(layoutList);
carouselView.launch();
```

Your CarouselView is now displayed on your app! 👏<br/>

### SlideshowView

SlideshowView can be used to show the multiple layouts by certain period of time. You can set how much time you want to show each layout to the user.

First, create a SlideshowView in your xml file.
```xml
<com.sung2063.sliders.slideshow.SlideshowView
        android:id="@+id/slideshow_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        app:showIndicator="true"
        app:indicatorScale="1"
        app:delayTimePeriod="5"
        app:showSlideNumber="true"
        app:slideNumberTextSize="40" />
```

In your `onCreate()` method in Activity, create your own custom layouts, add layouts to List<ViewGroup>, and start the slideshow. You can add up to 10 layouts in the SlideshowView. 

```java
SlideshowView slideshowView = findViewById(R.id.slideshow_view);

// Create your own layouts...
// Create List<ViewGroup> object...
// Add your layouts to list object...

slideshowView.setSlideList(layoutList);
slideshowView.launch();
```

Your SlideshowView is now displayed on your app! 👏<br/>

Check out my <a href="https://github.com/sung2063/AndroidSliderViewSample">Android Slide Sample App</a> project for more example on using SliderView library.

## Attributions

Here are available attributions you can use to modify your slider views.

### CarouselView

<center>
  <table>
    <tr>
      <th>Attribution</th>
      <th>Value</th>
      <th>Description</th>
    </tr>
    <tr>
      <td rowspan="2">scrollDirection</td>
      <td>horizontal</td>
      <td>Display the carousel horizontally. <i>Field value is 0.</i></td>
    </tr>
    <tr>
      <td>vertical</td>
      <td>Display the carousel vertically. <i>Field value is 1.</i></td>
    </tr>
    <tr>
      <td>showIndicator</td>
      <td>boolean</td>
      <td>Show the dot indicator on the slide if the value true, otherwise do not show.</td>
    </tr>
    <tr>
      <td>indicatorScale</td>
      <td>float</td>
      <td>Used for resize the indicator scale from 0 - 1.5.</td>
    </tr>
    <tr>
      <td>showSlideNumber</td>
      <td>boolean</td>
      <td>Show the slide number text if the value is true, otherwise do not show.</td>
    </tr>
    <tr>
      <td>slideNumberTextSize</td>
      <td>int</td>
      <td>Set the slide number text size in px.</td>
    </tr>
   </table>
 </center>

### SlideshowView

<center>
  <table>
    <tr>
      <th>Attribution</th>
      <th>Value</th>
      <th>Description</th>
    </tr>
    <tr>
      <td>showIndicator</td>
      <td>boolean</td>
      <td>Show the dot indicator on the slide if the value true, otherwise do not show.</td>
    </tr>
    <tr>
      <td>indicatorScale</td>
      <td>float</td>
      <td>Used for resize the indicator scale from 0 - 1.5.</td>
    </tr>
    <tr>
      <td>showSlideNumber</td>
      <td>boolean</td>
      <td>Show the slide number text if the value is true, otherwise do not show.</td>
    </tr>
    <tr>
      <td>slideNumberTextSize</td>
      <td>int</td>
      <td>Set the slide number text size in px.</td>
    </tr>
    <tr>
      <td>delayTimePeriod</td>
      <td>int</td>
      <td>The slide delay time in second. Default is 5 seconds.</td>
    </tr>
   </table>
 </center>

 ## Contributor 🌟
 
 Sung Hyun Back (@sung2063)

 ## Sponsorship
 
 Please sponsor me to my GitHub sponsorship page at https://github.com/sponsors/sung2063.
 Your valueable sponsorship helps me contributing more innovative projects and libraries. ❤️
