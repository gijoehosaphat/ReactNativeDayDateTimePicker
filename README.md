### Android
1. Add the following to `android/settings.gradle`:
  ```gradle

  include ':DayDateTimePickerAndroid', ':app'
  project(':DayDateTimePickerAndroid').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-day-date-time-pickers/android')
  ```
1. Add this dependency to `android/app/build.gradle`
  ```gradle

  dependencies {
      ...
      compile project(':DayDateTimePickerAndroid')
  }
  ```
1. Register `DayDateTimePackage` in your `MainActivity`:
  ```java
  
  protected List<ReactPackage> getPackages() {
      return Arrays.<ReactPackage>asList(
        new MainReactPackage(),
        ...
        new DayDateTimePackage(this)
        ...
        );
      }
  ```

### Javascript
You can then `import` the package into your code:
```javascript
  import { showTimePicker, showDatePicker, showDayPicker } from 'react-native-day-date-time-pickers'
```
And use it like this basic example:
```javascript
  const props = {
    title: 'This is a custom title.',
    ok: 'OK',
    cancel: 'Cancel',
    items: [
      'Sunday',
      'Monday',
      'Tuesday',
      'Wednesday',
      'Thursday',
      'Friday',
      'Saturday'
    ]
  }
  showDayPicker(props, (selectedIndex) => {
    console.log(selectedIndex)
  })
```
