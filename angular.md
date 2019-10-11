- Program type already present: uk.co.senab.photoview.BuildConfig

      vi platforms/android/cordova-plugin-imagepicker/starter-imagepicker.gradle
      查找并注释掉 implementation 'com.github.chrisbanes.photoview:library:1.+'

- giantss/cordova-plugin-ImagePicker 拍照自动压缩 bug

      vi platforms/android/app/src/main/java/com/giants/imagepicker/ImagePickerMain.java
      boolean isOrigin = data.getBooleanExtra(ImagePicker.EXTRAS_ISORIGIN, false); // 原图 false 改为 true

- giantss/cordova-plugin-ImagePicker 出现 bug

     开启 4G 热点，下载速度快
     重新安装 cordova plugin add https://github.com/giantss/cordova-plugin-ImagePicker.git
     查找并注释掉 implementation 'com.github.chrisbanes.photoview:library:1.+'
     boolean isOrigin = data.getBooleanExtra(ImagePicker.EXTRAS_ISORIGIN, false); // 原图 false 改为 true

- Program type already present: android.support.v4.app.INotificationSideChannel

      rm -rf platforms
      ../sign-apk.sh
      vi platforms/android/cordova-plugin-imagepicker/starter-imagepicker.gradle // line 17
      注释掉 implementation 'com.github.chrisbanes.photoview:library:1.+'
      vi platforms/android/app/src/main/java/com/giants/imagepicker/ImagePickerMain.java // line 126
      boolean isOrigin = data.getBooleanExtra(ImagePicker.EXTRAS_ISORIGIN, false); // 原图 false 改为 true
