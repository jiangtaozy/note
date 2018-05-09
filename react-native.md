- 19002 bug:

      手机开启USB网络共享

- Start the build

      npm start
      exp build:android 
      exp build:ios

- sudo sysctl -w fs.inotify.max_user_instances=1024 bug

      git clone https://github.com/facebook/watchman.git
      cd watchman/
      sudo apt-get install -y autoconf automake build-essential python-dev libssl-dev libtool
      ./autogen.sh
      ./configure
      make
      sudo make install

- Watchman crawl failed. Retrying once with node crawler. bug

      echo fs.inotify.max_user_instances=524288 | sudo tee -a /etc/sysctl.conf
      echo fs.inotify.max_user_watches=524288 | sudo tee -a /etc/sysctl.conf
      echo fs.inotify.max_queued_events=524288 | sudo tee -a /etc/sysctl.conf
      sudo sysctl -p

- 高德地图

      cd ~/.android
      keytool -list -v -keystore debug.keystore // 获取SHA1
      Ejecting to ExpoKit 
      > React Native: I'd like a regular React Native project.
      npm i -g react-native-cli
      Android
      react-native link react-native-amap3d
      rm yarn.lock
      shake your phone, enable live reload
      reload
      open react-native-debugger
      start remote js debugging
      toggle inspector
