---
layout: page
title: Downloader
permalink: /document/downloader/downloader
menu: false
---

## Downloader

The downloader lets you download any files with any extension.

Start with creating a new instance from downloader builder class.

#### builder
Return new instance from builder

    argument:
        Context context
        String url

```java
Downloader.Builder builder = new Downloader.Builder(getApplicationContext(), "someUrl.....");
```

***
#### setDownloadDir
Set directory for store downloaded files

    argument:
        String directory

```java
builder.setDownloadDir(String.valueOf(getExternalFilesDir("download")));
```

***
#### setTimeOut
Set connection timeOut (default 2 min)

    argument:
        Intger milliseconds

```java
builder.setTimeOut(60 * 2000);
```

***
#### setFileName
Set fileName and extension

Default downloader get from webServer fileName and fileExtension

if the name is null or cannot find this set current time instead of name
and if the extension is null or cannot find this set '.unkonw' instead of extension

    argument:
        String fileName
        String fileExtension

```java
builder.setFileName("someName", "png");
```

***
#### setHeader
Set header for request

    argument:
        Map<String, String> header

```java
Map<String, String> header = new HashMap<>();
header.put("Access-Token", "1234567890ABC");

builder.setHeader(header);
```

***
#### setDownloadListener
Set listener for alarm any action on the downloader

    argument:
        OnDownloadListener listener

```java
builder.setDownloadListener(new OnDownloadListener() {
        @Override
        public void onCompleted(File file) {
            Logger.d(TAG, "onCompleted:");
            Util.showToast(getApplicationContext(), "onCompleted", Toast.LENGTH_LONG);
        }

        @Override
        public void onFailure(String reason) {
            Logger.d(TAG, "onFailure:" + reason);
            Util.showToast(getApplicationContext(), "onFailure:" + reason, Toast.LENGTH_LONG);
        }

        @Override
        public void progressUpdate(int percent, int downloadedSize, int totalSize) {
            Logger.d(TAG, "progressUpdate:" + percent);
        }

        @Override
        public void onCancel() {
            Logger.d(TAG, "onCancel:" + "canceled");
            Util.showToast(getApplicationContext(), "onCancel:" + "canceled", Toast.LENGTH_LONG);
        }
    });
```

***
#### build
Build new instance of Downloader

```java
builder.build();
```

***
#### downaloder
Start downloading new file

```java
downloader.download();
```

***
#### cancelDownload
Cancel downloading file

```java
builder.cancelDownload();
```

***
#### pauseDownload
Pause current downloading file

```java
builder.pauseDownload();
```

***
#### resumeDownload
Resune downloading file

```java
builder.resumeDownload();
```

***
#### Notice
rebuild new instance after (pause or cancel)
because must be created new request
