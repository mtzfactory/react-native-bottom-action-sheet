
<p align="center">
  <img src="https://storage.googleapis.com/material-design/publish/material_v_12/assets/0B7WCemMG6e0VVWZzZ1FIN09XWGc/components-bottom-sheets.png" height="300" width="300" />
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/react-native-bottom-action-sheet"><img src="http://img.shields.io/npm/v/react-native-bottom-action-sheet.svg?style=flat" /></a>
  <a href="https://github.com/prscX/react-native-bottom-action-sheet/pulls"><img alt="PRs Welcome" src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" /></a>
  <a href="https://github.com/prscX/react-native-bottom-action-sheet#License"><img src="https://img.shields.io/npm/l/react-native-bottom-action-sheet.svg?style=flat" /></a>
</p>


# React Native: Bottom Action Sheet (Android/iOS)

A simple library that creates BottomSheets according to the [Material Design Specs](https://material.google.com/components/bottom-sheets.html) 
## Android


| **Sheet View**             |
| ----------------- |
| <img src="https://github.com/rubensousa/BottomSheetBuilder/raw/master/screens/normal_demo.gif" width="600" height="600" />                  |

| **Grid View**             |
| ----------------- |
| <img src="https://github.com/rubensousa/BottomSheetBuilder/raw/master/screens/tablet_grid.png" width="600" height="600" />                  |


| **Alert View**             |
| ----------------- |
| <img src="https://raw.githubusercontent.com/javiersantos/BottomDialogs/master/Screenshots/gif-1.gif" width="600" height="600" />                  |


## iOS

| **Sheet View**             |
| ----------------- |
| <img src="https://github.com/sagiwei/SGActionView/raw/master/sheet.png" width="600" height="600" />                  |

| **Grid View**             |
| ----------------- |
| <img src="https://github.com/sagiwei/SGActionView/raw/master/grid.png" width="600" height="600" />                  |


| **Alert View**             |
| ----------------- |
| <img src="https://github.com/sagiwei/SGActionView/raw/master/alert.png" width="600" height="600" />                  |


It is a React Native Bridge around below native Android & iOS Libraries

- [rubensousa/BottomSheetBuilder](https://github.com/rubensousa/BottomSheetBuilder)
- [javiersantos/BottomDialogs](https://github.com/javiersantos/BottomDialogs)
- [sagiwei/SGActionView](https://github.com/sagiwei/SGActionView)

## Getting started

`$ npm install react-native-bottom-action-sheet --save`

`$ react-native link react-native-bottom-action-sheet`

`$ react-native link react-native-vector-icons`

- **iOS**

`$ cd ./node_modules/react-native-bottom-action-sheet/ios/ && pod install`

- **Android**

Please add below snippet into your app `build.gradle`

```
allprojects {
    repositories {
        maven { url 'https://jitpack.io' }
    }
}
```

## Usage

```javascript
import RNBottomActionSheet from 'react-native-bottom-action-sheet';

import Icon from 'react-native-vector-icons'

```

- **Sheet View**

	- **API Way**

	```javascript

	let facebook = <Icon family={'FontAwesome'} name={'facebook'} color={'#000000'} size={30} />
	let instagram = <Icon family={'FontAwesome'} name={'instagram'} color={'#000000'} size={30} />

	let SheetView = RNBottomActionSheet.SheetView
	SheetView.Show({
		title: "Awesome!",
		items: [
			{ title: "Facebook", subTitle: "Facebook Description", icon: facebook },
			{ title: "Instagram", subTitle: "Instagram Description", icon: instagram },
		],
		theme: "light",
		selection: 3,
		onSelection: selection => {
			console.log("selection: " + selection);
		}
	});

	```

	- **React Way**

	```javascript
	let facebook = <Icon family={'FontAwesome'} name={'facebook'} color={'#000000'} size={30} />
	let instagram = <Icon family={'FontAwesome'} name={'instagram'} color={'#000000'} size={30} />

	<RNBottomActionSheet.SheetView visible={this.state.sheetView} title={"Awesome!"} theme={"light"} onSelection={selection => {
		console.log("selection: " + selection);
	}}>
		<RNBottomActionSheet.SheetView.Item title={"Facebook"} subTitle={"Facebook Description"} icon={facebook} />
		<RNBottomActionSheet.SheetView.Item title={"Instagram"} subTitle={"Instagram Description"} icon={instagram} />
	</RNBottomActionSheet.SheetView>

	```

> **Note:**
> - We have added `family` prop for `Icon` class, please make sure that you pass the props


- **Grid View**

	- **API Way**

	```javascript
	let facebook = <Icon family={'FontAwesome'} name={'facebook'} color={'#000000'} size={30} />
	let instagram = <Icon family={'FontAwesome'} name={'instagram'} color={'#000000'} size={30} />

	let GridView = RNBottomActionSheet.GridView
		GridView.Show({
			title: "Awesome!",
			items: [
			{ title: "Facebook", icon: facebook },
			{ title: "Instagram", icon: instagram }
			],
			theme: 'light',
			onSelection: (selection) => {
			console.log('selection: ' + selection)
			}
		});
	```

	- **React Way**

	```javascript
	let facebook = <Icon family={'FontAwesome'} name={'facebook'} color={'#000000'} size={30} />
	let instagram = <Icon family={'FontAwesome'} name={'instagram'} color={'#000000'} size={30} />

	<RNBottomActionSheet.GridView visible={this.state.gridView} title={"Awesome!"} theme={"light"} selection={3} onSelection={selection => {
		console.log("selection: " + selection);
		}}>
		<RNBottomActionSheet.GridView.Item title={"Facebook"} icon={facebook} />
		<RNBottomActionSheet.GridView.Item title={"Instagram"} icon={instagram} />
	</RNBottomActionSheet.GridView>

	```

> **Note:**
> - We have added `family` prop for `Icon` class, please make sure that you pass the props


- **Alert View**

	- **API Way**

	```javascript
	let AlertView = RNBottomActionSheet.AlertView
		AlertView.Show({
		title: "Awesome!",
		message: "What can we improve? Your feedback is always welcome.",
		positiveText: "OK",
		positiveBackgroundColor: "#eeffee",
		positiveTextColor: "#006500",
		negativeText: "Exit",
		negativeBackgroundColor: "#ffebeb",
		negativeTextColor: "#760000",
		theme: 'light',
		onPositive: () => {
			console.log('positive clicked')
		},
		onNegative: () => {
			console.log('negative clicked')
		}
		})
	```

	- **React Way**

	```javascript
	<RNBottomActionSheet.AlertView
		visible={this.state.alterView}
		title={"Awesome!"}
		message={"What can we improve? Your feedback is always welcome."}
		positiveText={"OK"}
		positiveBackgroundColor={"#eeffee"}
		positiveTextColor={"#006500"}
		negativeText={"Exit"}
		negativeBackgroundColor={"#ffebeb"}
		negativeTextColor={"#760000"}
		theme={"light"}
		onPositive={() => {
			console.log("positive clicked");
		}}
		onNegative={() => {
			console.log("negative clicked");
		}} />
	```

## API's

- **Sheet View**
	- `title(title: string)`
	- `items(title: string, subTitle: string, icon: image) - subTitle: iOS Only`
	- `onSelection(selcFunc: function)`
	- `Show()`
	- `titleTextColor(color: string) - Android Only` 
	- `itemTextColor(color: string) - Android Only`
	- `itemTintColor(color: string) - Android Only`
	- `backgroundColor(color: string) - Android Only`
	- `delayDismissOnItemClick(flag: bool) - Android Only`
	- `dividerItem(title: string) - Android Only`
	- `theme(theme: string) - iOS Only`
	- `selection(selc: int) - iOS Only`

- **Grid View**
	- `title(title: string)`
	- `ttems(title: string, icon: image)`
	- `selection(selcFunc: function)`
	- `Show()`
	- `itemTextColor(color: string) - Android Only`
	- `itemTintColor(color: string) - Android Only`
	- `backgroundColor(color: string) - Android Only`
	- `delayDismissOnItemClick(flag: bool) - Android Only`
	- `theme(theme: string): iOS Only`

- **Alert View**
	- `title(title: string)`
	- `message(message: string)`
	- `positiveText(text: string)`
	- `positiveBackgroundColor(color: string)`
	- `positiveTextColor(color: string)`
	- `negativeText(text: string)`
	- `negativeBackgroundColor(color: string)`
	- `negativeTextColor(color: string)`
	- `onPositive(selcFunc: function)`
	- `onNegative(selcFunc: function)`
	- `theme(theme: string) - iOS Only`
	- `Show()`

## TO DO
- Enable Android customization features for iOS platform as well

## Credits

- Android BottomSheetBuilder: [rubensousa/BottomSheetBuilder](https://github.com/rubensousa/BottomSheetBuilder)
- Android BottomDialogs: [javiersantos/BottomDialogs](https://github.com/javiersantos/BottomDialogs)
- iOS BottomSheet: [sagiwei/SGActionView](https://github.com/sagiwei/SGActionView)

## Contribution
Contributions are welcome and are greatly appreciated! Every little bit helps, and credit will always be given.

## License
This library is provided under the Apache 2 License.

RNBottomActionSheet @ Pranav Raj Singh Chauhan

