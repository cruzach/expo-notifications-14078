# expo-notifications-14078

This is a reproduction of this GH issue: https://github.com/expo/expo/issues/14078, but it includes a `patch-package` fix detailed [here](https://github.com/expo/expo/issues/14078#issuecomment-957795014).

To test this repo:

- clone it
- run `yarn` in the root of the project
- run `expo run:android --variant release -d` (with your android device connected)
- in a separate window, run `adb logcat -s "ReactNativeJS"` (this is going to be used for us to confirm that the listener is running. FYI- the `-s` filters by tag, which is very useful)
- In the app, tap the button to schedule the notification, and tap the notification. Check your `adb logcat` window and confirm you see a "response received" message
- Now, tap the button to schedule the notification, background your app, and tap the notification. Confirm that you've recieved another "response received" message.
- Finally, tap the button to schedule the notification, kill your app, and tap the notification. Confirm that you've recieved another "response received" message.
