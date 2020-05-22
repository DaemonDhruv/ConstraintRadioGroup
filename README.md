ConstraintLayout RadioGroup
===========================

![Version](https://img.shields.io/github/v/release/DaemonDhruv/ConstraintRadioGroup?include_prereleases&style=flat-square)
![License](https://img.shields.io/github/license/Daemondhruv/ConstraintRadioGroup?style=flat-square)
[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg?style=flat-square)](https://saythanks.io/to/dhruv.bindoria@gmail.com)

##### _Intro_
This is a custom `RadioGroup` which extends `ConstraintLayout`.
With this you can align `RadioButton`s in a `RadioGroup` like you would normally do when adding any Views to your `ConstraintLayout`.

##### _Background_
The `RadioGroup` is a child of `LinearLayout`, which makes it very difficult to arrange Radio Buttions in complex designs and at the same time you might want them to be bound to the same `RadioGroup`. So as when one button is checked others must be unchecked.

Now, there are similar libraries available out there, but the problem was, when you make a radio button checked by default, it doesn't get unchecked when you check another button.

For these reasons I had to make my custom `RadioGroup` i.e., `ConstraintRadioGroup`


To get this library into your build
-------------------------------------

**Step 1:** Add it in your root build.gradle at the end of repositories:

```gradle
allprojects {
	repositories {
		...
		maven { url 'https://jitpack.io' }
	}
}
```

**Step 2:** Add the dependency

```gradle
dependencies {
        implementation 'com.github.DaemonDhruv:ConstraintRadioGroup:0.1.0-alpha'
}
```
Or check [jitpack](https://jitpack.io/#DaemonDhruv/ConstraintRadioGroup/0.1.0-alpha) for versions...

Usage
--------------------------------

1. Add all your `RadioButton`s in between `<in.daemondhruv.customviewgroup.ConstraintRadioGroup>` tags.

2. Add constraints to the `RadioButton` like you would normally do in a `ConstraintLayout`

3. Done! :smile:

    ##### activity_main.xml

    ```xml
    <?xml version="1.0" encoding="utf-8"?>
    <androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://   schemas.android.com/apk/res/android"
        xmlns:app="http://schemas.android.com/apk/res-auto"
        xmlns:tools="http://schemas.android.com/tools"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MainActivity">

        <in.daemondhruv.customviewgroup.ConstraintRadioGroup
            android:layout_width="0dp"
            android:layout_height="200dp"
            android:layout_marginTop="64dp"
            app:layout_constraintEnd_toEndOf="parent"
            app:layout_constraintStart_toStartOf="parent"
            app:layout_constraintTop_toBottomOf="parent">


            <RadioButton
                android:id="@+id/radioButton"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginStart="64dp"
                android:layout_marginTop="16dp"
                android:checked="true"
                android:text="PC"
                app:layout_constraintStart_toStartOf="parent"
                app:layout_constraintTop_toTopOf="parent" />

            <RadioButton
                android:id="@+id/radioButton2"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_marginStart="28dp"
                android:layout_marginTop="16dp"
                android:text="Xbox"
                app:layout_constraintStart_toEndOf="@+id/radioButton"
                app:layout_constraintTop_toTopOf="parent" />

        </in.daemondhruv.customviewgroup.ConstraintRadioGroup>


    </androidx.constraintlayout.widget.ConstraintLayout>
    ```

    _To work with java/kotlin... Import:_
    ##### MainActivity.java

    ```java
    import in.daemondhruv.customviewgroup.ConstraintRadioGroup;
    ```

    ##### MainActivity.kt

    ```kotlin
    import in.daemondhruv.customviewgroup.ConstraintRadioGroup
    ```

License
-------
    This is free and unencumbered software released into the public domain.
    
    Anyone is free to copy, modify, publish, use, compile, sell, or
    distribute this software, either in source code form or as a compiled
    binary, for any purpose, commercial or non-commercial, and by any
    means.
    
    In jurisdictions that recognize copyright laws, the author or authors
    of this software dedicate any and all copyright interest in the
    software to the public domain. We make this dedication for the benefit
    of the public at large and to the detriment of our heirs and
    successors. We intend this dedication to be an overt act of
    relinquishment in perpetuity of all present and future rights to this
    software under copyright law.
    
    THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
    EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
    MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
    IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
    OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
    ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
    OTHER DEALINGS IN THE SOFTWARE.
    
    For more information, please refer to <https://unlicense.org>


References
----------

- Actuall `RadioGroup` sourcecode [android.googlesource.com](https://android.googlesource.com/platform/frameworks/base/+/master/core/java/android/widget/RadioGroup.java)

- RadioGroup extending RelativeLayout? [Stackoverflow](https://stackoverflow.com/a/6320518/9365773)

- Flat-Radio-Group - Radio Group for ConstraintLayout [Medium.com](https://medium.com/@uditverma5602/flat-radio-group-radio-group-for-constraintlayout-a38226b2ecdb)
