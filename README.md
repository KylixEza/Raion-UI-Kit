[![platform](https://img.shields.io/badge/platform-Android-green.svg)](https://www.android.com)
[![License](https://img.shields.io/badge/license-MIT-EA4235.svg)](https://www.apache.org/licenses/LICENSE-2.0.html)
[![jitpack](https://jitpack.io/v/KylixEza/Raion-UI-Kit.svg)](https://jitpack.io/#KylixEza/Raion-UI-Kit)

<div align="center">
<img width="50%" height = "50%" src="https://user-images.githubusercontent.com/58837451/166941873-5e93e57a-d3c9-4183-96c1-a9bf5e7cfd8a.png" />
</div>

# Raion-UI-Kitπ

### Prerequisites

- For old version of gradle (before arctic fox update)

  Add this in your root `build.gradle` file (project scope) :

```gradle
allprojects {
	repositories {
		...
		maven { url "https://jitpack.io" }
	}
}
```
- For gradle version 7 or latest
  
  Add this in your root `setting.gradle` file :
```gradle
dependencyResolutionManagement {
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)
    repositories {
        ...
        maven { url 'https://jitpack.io' }
    }
}
```

### Dependency

Add this to your module's `build.gradle` file :

```gradle
dependencies {
	...
	implementation 'com.github.KylixEza:Raion-UI-Kit:version'
}
```
you can check the version on jitpack badge above or on release tag

# RaionToast π

### Usage

```kotlin
RaionToast.Builder()
    .setContext(this@MainActivity)
    .setText("Hello there this is RaionToast")
    .setLogoVisibility(true)
    .setDuration(Toast.LENGTH_SHORT)
    .setToastType(ToastType.INFO)
    .setToastShape(ToastShape.RECTANGLE)
    .build().show()
 ```
 
 | Method / Class | Parameter | Usage | Attribute Default Value |
| ------ | :---------: | ----- | :-------------------: | 
| ```Builder```| - | Build the toast | No default value because it's mandatory |
| ```setText``` | ```String``` | To set message that will shown from toast | ```""``` |
| ```setToastType``` | ```ToastType``` | To set type of toast | ```ToastType.NORMAL``` |
| ```setLogoVisibility``` | ```Boolean``` | To set visibility of Raion logo  | ```true``` |
| ```setDuration``` | ```Int```| To set duration of toast | ```Toast.LENGTH_SHORT``` |
| ```setToastShape``` | ```ToastShape``` | To set shape of toast | ```ToastShape.ROUNDED``` |
| ```build``` | - | To create the toast => returns toast object | - |

# RaionSneeze (Snackbar) π₯¨ 

### Usage

- To display a normal Snackbar:

```kotlin
RaionSneeze.makeNormalSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG).show()
RaionSneeze.showNormalSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG)
```

- To display a success Snackbar:

``` kotlin
RaionSneeze.makeSuccessSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG).show()
RaionSneeze.showSuccessSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG)
```
- To display an error Snackbar:

``` kotlin 
RaionSneeze.makeErrorSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG).show()
RaionSneeze.showErrorSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG)
```

- To display an warning Snackbar:

``` kotlin
RaionSneeze.makeWarningSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG).show()
RaionSneeze.showWarningSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG)
```
- To display an info Snackbar:

``` kotlin
RaionSneeze.makeInfoSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG).show()
RaionSneeze.showInfoSneeze(findViewById(R.id.content), "Hello there this is raion snackbar", Snackbar.LENGTH_LONG)
```

# RaionDialog π

> Dialog type currently available: `Confirmation dialog`<br/>
> More dialog type will added soon. Insya'allah

### Confirmation Dialog Usage
- Is Dialog type which has `Icon, Main text, Confirm Button, Cancel Button`<br/>

<p align="center">
  <img src="https://github.com/KylixEza/Raion-UI-Kit/blob/1.1.1/raiondialog/sample%20gif/confirmation%20dialog.gif" width="240">
</p>

- Default basic function
```
val dialog = RaionDialog
    		.Confirmation()
    		.build(context, onYesBtnClick = {...},onNoBtnClick = {...})
dialog.show()
```
- Available costumization function
  | Function  |  Parameter Type | Usage | Default Parameter Value  |
  | ------------ | ------------ | ------------ | ------------ |
  |  `setButtonColor` | `yesColorId:Int` & `noColorId:Int`  | to set colors of Yes & No button  |  `R.color.DefaultCyan`, `R.color.DefaultRed` |
  |  `setButtonText` | `leftText:String`, `rightText:String`, `leftTextColor:Int`,  `rightTextColor:Int`  | to set text of each button, and set the color of the text  | `"yes"`, `"no"`, `R.color.DefaultBlack`, `R.color.DefaultBlack`  |
  | `setText` | `text:String` & `textColor:Int` | to set the main text and its color  | `"Confirm?"`, `R.color.DefaultBlack`  |
  |  `setBackgroundColor` | `colorId:Int`  | to set background color of the dialog  | `R.color.DefaultWhite`  |
  | `setIcon` | `iconId:Int` |  to set main icon of dialog, the default is Raion Logo | `R.drawable.icon_raion`  |
  |  `setType` | `dialogType:DialogType`  | to change the dialog type, such as TOP, CENTER, and BOTTOM  | `DialogType.CENTER`  |
  | `build`  | `context:Context`, `onYesBtnClick:Unit`, `onNoBtnClick:Unit`  | to build the dialog. This function must be called last  | no default parameter, all parameter must be implemented  |



**>> You can costumize the dialog by calling available function before calling `build` function**

## Licenses

Raion-UI-Kit is under MIT License and Raion Community License

```
Raion Community License

Copyright (c) 2022 Raion Community Faculty of Computer Science University of Brawijaya

This project belongs to Raion Community

Raion-UI-Kit is partially open. This project open to use for everyone but 
close for any changes from outside Raion Community. If any developers are 
interested to contribute in this project but are not the part of Raion Community, 
they must contact the Project Lead or Raion Community through social media
(Recommend to contact via Instagram or LinkedIn).

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of this project.
```

## Contributors
<p>
<img src="https://images.weserv.nl/?url=avatars.githubusercontent.com/u/58837451?v=4&h=100&w=100&fit=cover&mask=circle&maxage=7d"/>
 &nbsp
<img src="https://images.weserv.nl/?url=avatars.githubusercontent.com/u/74236720?v=4&h=100&w=100&fit=cover&mask=circle&maxage=7d"/>
&nbsp
<img src="https://images.weserv.nl/?url=avatars.githubusercontent.com/u/89689111?v=4&h=100&w=100&fit=cover&mask=circle&maxage=7d"/>
	
</p>
  
## Contact
<a href="https://www.linkedin.com/company/raioncommunity" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="kylix-eza-saputra-1bb1b7192" height="30" width="40" /></a>
<a href="https://www.instagram.com/raion_community/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="k_ylix" height="30" width="40" /></a>

<p>
Don't forget to β­this repository to motivates me to share more open source library
</p>
