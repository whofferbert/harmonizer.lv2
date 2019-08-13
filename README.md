harmonizer.lv2 - Audio to Midi
==============================

harmonizer.lv2  uses the aubio toolkit for note onset and pitch detection on audio input and outputs midi notes.

Currently only scoped for monophonic inputs.

Originally by Daniel Sheeler; <dsheeler@pobox.com>

Updated and further modified by William Hofferbert <will@hbert.com>

Install
-------
This fork has been redesigned to build on a Raspberry Pi 3.

Compiling harmonizer requires the LV2 SDK, bash, gnu-make, and a c-compiler.

Somewhere on your Raspberry Pi 3B/3B+; do the following:
```bash
  git clone git://github.com/whofferbert/harmonizer.lv2.git
  cd harmonizer.lv2
  # something about aubio submodule here
  make
```

If you are using MODEP and want to use this, then also do:
```bash
sudo ln -s $(pwd)/build /usr/local/modep/.lv2/harmonizer.lv2
```

Note to packagers: The Makefile honors PREFIX and DESTDIR variables as well
 as CFLAGS, LDFLAGS and OPTIMIZATIONS (additions to CFLAGS).
