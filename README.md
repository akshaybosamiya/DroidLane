# DroidLane
[![Build Status](https://travis-ci.org/Jintin/DroidLane.svg?branch=master)](https://travis-ci.org/Jintin/DroidLane)
[![JetBrains compatible](https://img.shields.io/badge/JetBrains-compatible-brightgreen.svg)](https://plugins.jetbrains.com/plugin/8068)
[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/JStumpp/awesome-android)

DroidLane is an deploy tool help you upload your apk to Google Play from Android Studio or IntelliJ IDEA. An Android Studio / Intellij plug-in help you upload your apk file to Google Play

## Installation
- Open Android Studio or IntelliJ IDEA
- Open [Preferences] -> [Plugins] -> [Browse repositories], search DroidLane to install and restart

## Usage
- Go to Google Play **[Settings] -> [API access] -> [Create OAuth Client]** and keep your [CLIENT ID] and [CLIENT SECRET]
- Go to your project root dir create `.droidlane/[profile_name]/data.json` with content:

  ```json
  {
  "client_id": "[CLIENT ID]",
  "package": "[PACKAGE NAME]",
  "apk": "[APK PATH]",
  "track": "['alpha', 'beta' or 'production'](optional)"
  }
  ```

- Run DroidLane command in **[Build] -> [Upload Apk]**
- Select track if not define in data.json
- Set [CLIENT SECRET] and encrypt with password
- OAuth permission accept in browser

After first-time setup, you only need click button and key-in password to upload apk.

### Recent Change Text support
Create the recent change file with content in flowing directory

```
  └── .droidlane
      └── [profile_name]
          ├── data.json
          └── recentChange
              ├── en_US
              ├── zh_TW
              │   ...
              └── (other language)
```

### Multiple profile support
You can also add multiple profile in flowing format.

```
└── .droidlane
    ├── [profile_name1]
    │   └── data.json
    └── [profile_name2]
        └── data.json
```

### Multiple apk support
You can also add multiple apk in one profile to upload at the same time. Just chane the data.json from JSONObject to JSONArray.(Notice it will share the Recent Change Text)

```json
[
  {
    "client_id": "[CLIENT ID1]",
    "package": "[PACKAGE NAME1]",
    "apk": "[APK PATH1]",
    "track": "[TRACK1](optional)"
  },
  {
    "client_id": "[CLIENT ID2]",
    "package": "[PACKAGE NAME2]",
    "apk": "[APK PATH2]",
    "track": "[TRACK2](optional)"
  }
]
```

## Contributing
Bug reports and pull requests are welcome on GitHub at [https://github.com/Jintin/DroidLane](https://github.com/Jintin/DroidLane).

## License
The module is available as open source under the terms of the [MIT License](http://opensource.org/licenses/MIT).
