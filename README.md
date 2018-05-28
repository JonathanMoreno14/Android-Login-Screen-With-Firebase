
# Android Login Screen with Firebase

* The application allows users to signup for a new account
* Login in to their new created account profile
* Sign out of the account
* Reset password if needed


![webp net-gifmaker 2](https://user-images.githubusercontent.com/11635523/40630177-f2482fa4-6295-11e8-99d2-1df3f71d9f44.gif)


**Dependencies**
```gradle

implementation 'com.android.support:cardview-v7:27.1.1'
implementation 'com.google.firebase:firebase-core:15.0.2'
implementation 'com.google.firebase:firebase-auth:15.1.0'

```

**Permissions**

```xml

 <uses-permission android:name="android.permission.INTERNET"/>

```

You will need a **google-services.json** from Firebase


Adding **FirebaseAuth** in the **LoginActivity.java**, **SignupActivity.java**, **ProfileActivity**, and **ResetPasswordActivity**

```java

private FirebaseAuth firebaseAuth;

```
Add the **FirebaseAuth** instance in the **onCreate()** methods of all 4 activities

```java

firebaseAuth = FirebaseAuth.getInstance();

```

To Sign out a user

```java

FirebaseAuth.getInstance().signOut();

```


It's optional but you can configure ProGuard **proguard-rules.pro**

```
-keepattributes Signature
-keepattributes *Annotation*

```

Add color design for the background **app/res/drawable/main_color_selector.xml**

```xml

<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item>
        <shape>
            <gradient
                android:angle="90"
                android:startColor="@color/colorPrimaryDark"
                android:endColor="@color/colorAccent"
                android:type="linear" />
        </shape>
    </item>
</selector>

```


Adding a custom theme to  the **app/res/values/styles.xml**

```xml

<!--Custom Theme with no ActionBar-->
  <style name="AppThemefull" parent="Theme.AppCompat.Light.NoActionBar">
      <item name="colorPrimaryDark">@color/colorPrimaryDark</item>
      <item name = "android:windowActionBar">false</item>
      <item name = "android:windowNoTitle">true</item>
  </style>

```
