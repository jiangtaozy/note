- Configuration file

      ~/.xmonad/xmonad.hs
- Ibus

      spawnOnce "ibus-daemon --xim -r -d"
      ibus engine
      ibus engine libpinyin
      ibus-setup

- Fedora Java applications blank, grey windows problems

      export _JAVA_AWT_WM_NONREPARENTING=1
