# houston_ios_push_sample


## getting device token Swift

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
    let deviceTokenString = deviceToken.reduce("", {$0 + String(format: "%02X", $1)})
    print("device_token = \(deviceTokenString)")
}
```
