# Permission-Checker
**• Permission Checker for Android java •**
> ဒီ Package လေးက Android applications တွေ ရေးတဲ့နေရာမှာ ဖန်တရာတေနေအောင် သုံးရတဲ့ permission တွေတောင်းတဲ့နေရာမှာ လွယ်လွယ်ကူကူ သုံးလို့ရအောင်လုပ်ထားတဲ့ package လေးဖြစ်ပါတယ်ဗျ။

> Library တစ်ခုအနေနဲ့ဖန်တီးချင်ပေမယ့် PC မရှိတဲ့အတွက် ( Android Studio မှာပဲအဆင်ပြေလို့ပါ ) ရိုးရိုး package တစ်ခုအနေနဲ့ပဲလုပ်ထားရပါတယ်ဗျ။

## Usage
### 1. Put the package in your project (watch video) 
### 2. Instantiate checker class first 
```java
Checker checker = Checker.withActivity(this).withPermission(Manifest.permission.ACCESS_FINE_LOCATION).withRequestCode(<REQUEST CODE HERE>)
				.withListener(new PermissionListener(){
					@Override
					public void onPermissionGranted() {
        //Your code here to continue when prrmission granted				//ခွင့်ပြုချက်ရရင်
     }

					@Override
					public void onPermissionDenied() {
						//Your code here when permission denied
        //ခွင့်ပြုချက်မရခဲ့ရင်
     }

					@Override
					public void onPermissionNever() {
						//Your code to explain why you should give permission when user never allow permission
        //အသုံးပြုသူမှ ဘယ်တော့မှ permission မပေးသောအခါ ရှင်းပြရန်
     }
				});
				

```
### 3. you can check from wherever you like
```java
checker.check();
```
### 4. put this code inside onRequestPermissionResults event
```java
checker.onRequestPermissionsResult(<REQUEST CODE FROM EVENT>,<GRANTRESULTS FROM EVENT>);
```
