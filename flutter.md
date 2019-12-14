- Run flutter

      flutter run
      r // hot reload
      p // display construction lines

- Vim plug

      // .vimrc
      call plug#begin()
      "... <snip other plugins>
      Plug 'dart-lang/dart-vim-plugin'

      call plug#end()
      // Then invoke :PlugInstall to install the plugin.

- Print

      print('name: ${name}');

- Install package

      flutter packages get

- List emulators

      flutter emulators

- Typeof

      print("HELLO".runtimeType);

- ADB logcat

      adb logcat | grep 'flutter'
