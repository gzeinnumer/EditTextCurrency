<p align="center">
  <img src="https://github.com/gzeinnumer/EditTextCurrency/blob/master/preview/example100.jpg" width="400"/>
</p>

<h1 align="center">
    EditTextCurrency
</h1>

<p align="center">
    <a><img src="https://img.shields.io/badge/Version-5.2.1-alpha-brightgreen.svg?style=flat"></a>
    <a><img src="https://img.shields.io/badge/ID-gzeinnumer-blue.svg?style=flat"></a>
    <a><img src="https://img.shields.io/badge/Java-Suport-green?logo=java&style=flat"></a>
    <a><img src="https://img.shields.io/badge/Kotlin-Suport-green?logo=kotlin&style=flat"></a>
    <a href="https://github.com/gzeinnumer"><img src="https://img.shields.io/github/followers/gzeinnumer?label=follow&style=social"></a>
    <br>
    <p>Simple way to convert 1000000 to 1,000,000 .</p>
</p>

---
# Content List
* [Download](#download)
* [Feature List](#feature-list)
* [Tech stack and 3rd library](#tech-stack-and-3rd-library)
* [Usage](#usage)
* [Example Code/App](#example-codeapp)
* [Version](#version)
* [Contribution](#contribution)

---
# Download
Add maven `jitpack.io` and `dependencies` in build.gradle (Project) :
```gradle
// build.gradle project
allprojects {
  repositories {
    ...
    maven { url 'https://jitpack.io' }
  }
}

// build.gradle app/module
dependencies {
  ...
  implementation 'com.github.gzeinnumer:EditTextCurrency:version'
  implementation 'com.google.android.material:material:1.2.0'
}
```

---
# Feature List
- [x] [CurrencyConverter Programatically](#currencyconverter-programatically).

---
# Tech stack and 3rd library
- TextWatcher ([docs](https://developer.android.com/reference/android/text/TextWatcher))
- Material.io ([docs](https://material.io/develop/android/docs/getting-started))

---
# Usage

**First Step**. Use `MaterialComponents` in your style :
```xml
<style name="AppTheme" parent="Theme.MaterialComponents.Light.NoActionBar">
    <!-- Customize your theme here. -->
</style>
```

#
* **Sample 1** -> Simple `TextWacher`
```java
editText.addTextChangedListener(new CurrencyConverter(editText));

button.setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        String str = editText.getText().toString();
        Log.d(TAG, "onClick: " + StringTools.trimCommaOfString(str));

        textView.setText(StringTools.trimCommaOfString(str));
    }
});
```

#
* **Sample 2** -> Simple `TextWacher` With `CallBack`
```java
editText.addTextChangedListener(new CurrencyConverter(editText, new CurrencyConverter.StringCallBack() {
    @Override
    public void realString(String value) {
        textView.setText("(Real Value) : " + value + " && (Preview) : " + editText.getText().toString());
    }
}));
```

#
Preview For **Sample 1-4**:
|<img src="https://github.com/gzeinnumer/EditTextCurrency/blob/master/preview/example100.jpg" width="400"/>|
|---|
|**Sample 1 & Sample 2**|

---
# Example Code/App

**FullCode [MainActivity](https://github.com/gzeinnumer/EditTextCurrency/blob/master/app/src/main/java/com/gzeinnumer/edittextcurrency/MainActivity.java)  & [XML](https://github.com/gzeinnumer/EditTextCurrency/blob/master/app/src/main/res/layout/activity_main.xml)**

[Sample Code And App](https://github.com/gzeinnumer/MyLibCurrencyConverterExample)

---
# Version
- **4.0.0**
  - First Release
- **4.0.1**
  - Take Out Useless Method
- **5.0.1**
  - Support SDK 16
- **5.0.2**
  - Bug Fixing
- **5.0.3**
  - Bug Fixing
- **5.1.0**
  - Take Out CurrencyEditText & CurrencyEditTextFilledBox & CurrencyEditTextOutlinedBox
- **5.2.0**
  - More Simple

---
# Contribution
You can sent your constibution to `branch` `open-pull`.

---

```
Copyright 2020 M. Fadli Zein
```
