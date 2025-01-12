# harmonizer.lv2 - Audio to Midi

harmonizer.lv2  uses the aubio toolkit for note onset and pitch detection on audio input and outputs midi notes.

Currently only scoped for monophonic inputs.

Originally by Daniel Sheeler; <dsheeler@pobox.com>

Updated and further modified by William Hofferbert; <will@hbert.com>

## Requirements

This fork has been redesigned to build on a Raspberry Pi 3.

Compiling harmonizer requires the LV2 SDK, bash, gnu-make, and a c-compiler (probably all default installed on the pi, except the c compiler, let me know/PR the README.md!).

## Install

Somewhere on your Raspberry Pi 3B/3B+; do the following:
```bash
  git clone git://github.com/whofferbert/harmonizer.lv2.git
  cd harmonizer.lv2
  git submodule init
  git submodule update
  make
```

If you are using MODEP and want to use this, then also do the following, which will symlink the built plugin in to the lv2 directory that MODEP looks at:
```bash
sudo ln -s $(pwd)/build /usr/local/modep/.lv2/harmonizer.lv2
```

Reboot your pi afterward, and you should be able to find the Harmonizer plugin in the list.

## Tweaking

If you have the build dir symlinked to the proper lv2 location, it makes tweaking and testing things a bit easier.

Adjust whatever things you need to in the source, and simply do:
```bash
make clean
make
```

The reboot your pi, or relaunch your DAW software, etc. and test again!

Happy hacking!

## Notes

Note to packagers: The Makefile honors PREFIX and DESTDIR variables as well
 as CFLAGS, LDFLAGS and OPTIMIZATIONS (additions to CFLAGS).
