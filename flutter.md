- Run flutter

      flutter run
      r // hot reload
      p // display construction lines
      c // clean the screen
      q // quit
      h // list all commands

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

- Create with package name

      flutter create --org com.my_cool_org project_name

- Flutter emulator camera mode

      Hold Alt to control camera via the following methods:
      rotate with mouse
      move with WASDQE

- Cascades (..) allow you to make a sequence of operations on the same object

      List list = [];
      list.add(color1);
      list.add(color2);
      list.add(color3);
      list.add(color4);

      // with cascade
      List list = [];
      list
        ..add(color1)
        ..add(color2)
        ..add(color3)
        ..add(color4);

- Updating package dependencies

      flutter pub upgrade

- Bottom bar

      DefaultTabController(
        length: 3,
        child: Scaffold(
          body: Column(
            children: <Widget>[
              Expanded(
                child: TabBarView(
                  children: [
                    Icon(Icons.directions_car),
                    Icon(Icons.directions_transit),
                    Icon(Icons.directions_bike),
                  ],
                ),
              ),
              Material(
                color: Colors.blue,
                child: TabBar(
                  tabs: [
                    Tab(icon: Icon(Icons.directions_car)),
                    Tab(icon: Icon(Icons.directions_transit)),
                    Tab(icon: Icon(Icons.directions_bike)),
                  ],
                ),
              ),
            ],
          ),
        ),
      );
