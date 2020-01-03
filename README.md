# CircleIndicator
### this is Custom Layout for Android, It can be used in like ViewPager.
---
#### Example


((https://ifh.cc/g/AkfME.jpg))
((https://ifh.cc/g/ZIeZA.jpg))


---
#### How to use
###### Step 1. Add the JitPack repository to your Project file (build.gradle)

    allprojects {
		    repositories {
			    ...
			    maven { url 'https://jitpack.io' }
		    }
    }
  
###### Step 2. Add the dependency to your Application module (build.gradle)

    dependencies {
        implementation 'com.github.mhwan:CircleIndicatorLibrary:0.1'
    }
    
###### Step 3. Add CircleIndicator in your Layout XML

    <com.mhwan.circleindicatorlibrary.CircleIndicator
        android:id="@+id/indicator"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
    </com.mhwan.circleindicatorlibrary.CircleIndicator>

* And you must create 2 Circle(Drawable Xml, one resource for on, the other resource for off)

Example : on_indicator.xml

    <shape
        xmlns:android="http://schemas.android.com/apk/res/android"
        android:shape= "oval">
        <solid android:color="@android:color/holo_blue_dark"/>
    </shape>
then, you put `app:select_circle_resource="@drawable/on_indicator"`, `app:non_select_circle_resource="@drawable/off_indicator"` tag in your layout

* And you must put your count of circle
    
    `app:circle_count="2"`
    
* If you want change circle Size
    
    `app:circle_size="8dp"`
    
* If you want change margin circle
   
    `app:circle_margin="6dp"`

###### Step 4. Add this java code in your viewpager's pageChangeListener (OnPageChangeListener)

    `circleindicator.selectDot(i);`
    
- java
    
    
		viewPager.addOnPageChangeListener(new ViewPager.OnPageChangeListener() {
            @Override
            public void onPageScrolled(int i, float v, int i1) {

            }

            @Override
            public void onPageSelected(int i) {
                circleindicator.selectDot(i);
            }

            @Override
            public void onPageScrollStateChanged(int i) {

            }
        });
