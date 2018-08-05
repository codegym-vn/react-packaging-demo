# Thực hành đóng gói ứng dụng React Native

## Mục tiêu

- Biết cách config và đóng gói 1 ứng dụng React Native ra bundle.
- Hướng dẫn này sẽ sử dụng `Expo` đã cài đặt sẵn khi tạo project với `create-react-native-app`.

## Mô tả

- Yêu cầu cài đặt: [Create React Native App](https://github.com/react-community/create-react-native-app).
- Cài đặt Expo cli.
- Để build ra 1 app đối với `iOS` thì bạn cần có tài khoản ** App Developer ** nên ở hướng dẫn này chỉ hướng dẫn đầy đủ cho việc build trên Android.
- Tạo 1 app demo với `create-react-app-native`.
- Configure `app.json`.
- Build standalone app với lệnh của `Expo`.

Note: Với `iOS` app bạn có thể tham khảo thêm chi tiết tại: https://bit.ly/2vD87s8

## Hướng dẫn

### Bước 1

- Tạo 1 ứng dụng React Native app với `create-react-native-app` với lệnh:

```
create-react-native-app your-app
```

`your-app` là tên project của bạn.


Hoặc sử dụng app có sẵn tại đây: https://github.com/tutv/rn-hacker-news-navigation

### Bước 2

- Cài đặt `Expo cli` với lệnh:
```
npm install -g exp
```

- Đăng ký tài khoản tại https://expo.io

- Sau đó login với **Expo cli** với lệnh:

```
exp login

//Sau đó bạn sẽ đăng nhập tài khoản tại đây.
```

### Bước 3

Config file `app.json` ở trong thư mục gốc.

```
{
  "expo": {
    "name": "RN Demo App",
    "icon": "./src/assets/logo.png",
    "version": "1.0.0",
    "slug": "rn-demo-app",
    "sdkVersion": "27.0.0",
    "ios": {
      "bundleIdentifier": "com.codegym.rn.demo-app"
    },
    "android": {
      "package": "com.codegym.rn.demo-app"
    }
  }
}
```

Note: `bundleIdentifier` và `package` là chỗ điền tên gói của bạn trên **App Store** và **Google Play**.

### Bước 4

- Build standalone app với lệnh:

```
//Dành cho Android
exp build:android

//Dành cho iOS
exp build:ios
```

Note: Đối với iOS bạn bắt buộc phải có tài khoản `Apple Developer` để build được app.

## Kết quả

```
[00:55:44] Uploading assets
[00:55:47] No assets changed, skipped.
[00:55:47] Uploading JavaScript bundles
[00:56:02] Published
[00:56:02] Your URL is

https://exp.host/@tutv95/rn-demo-app

[00:56:03] Building...
[00:56:04] Build started, it may take a few minutes to complete.
[00:56:04] You can monitor the build at

 https://expo.io/builds/2002df8c-4b8e-4bed-b171-206d7a43e3a9
```

- Sau khi chạy xong sẽ nhận được output như trên là thành công.
- Link file `apk` tải tại link cuối cùng: `https://expo.io/builds/2002df8c-4b8e-4bed-b171-206d7a43e3a9`

![Demo](/demo/download.png)

- File apk đã build: [App.apk](/demo/app.apk)