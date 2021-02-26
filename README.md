# houston_ios_push_sample


## getting device token Swift

```
func application(_ application: UIApplication, didRegisterForRemoteNotificationsWithDeviceToken deviceToken: Data) {
    let deviceTokenString = deviceToken.reduce("", {$0 + String(format: "%02X", $1)})
    print("device_token = \(deviceTokenString)")
}
```


## gem 'houston'

```
$ bundler init  
$ bundle install --path vendor/bundle  
```

## pem

```
$  openssl pkcs12 -in xxxx.p12 -out xxxx.pem -nodes -clcerts
```

## do

```
$ bundle exec ruby houston_push.rb
```

## Other confirmation methods

- development 

```
curl -v -d '{"aps":{"alert":"hello"}}' -H "apns-topic: [Bundle ID]" --http2 --cert [pem file] https://api.sandbox.push.apple.com/3/device/[device token]
```

- production
```
curl -v -d '{"aps":{"alert":"hello"}}' -H "apns-topic: [Bundle ID]" --http2 --cert [pem file] https://api.push.apple.com/3/device/[device token]
```
