# ErgodoxEZ firmware compiler

[![](https://images.microbadger.com/badges/image/potz/ergodox-ez-compiler.svg)](https://microbadger.com/images/potz/ergodox-ez-compiler)

[![](https://images.microbadger.com/badges/version/publysher/automated-badger.svg)](http://microbadger.com/images/publysher/automated-badger)

This is a small [docker](https://www.docker.com/) image that has a script and all the dependencies needed to compile your [Ergodox EZ](http://www.ergodox-ez.com) firmware.

It uses the recommended build tools and instructions from [Jack Humbert's qmk firmware repo](https://github.com/jackhumbert/qmk_firmware/tree/a258358/keyboards/ergodox).

## Sample usage

You must mount a volume on `/keymap` to a folder containing your `keymap.c` file. When the compilation is finished, the resulting `ergodox_ez.hex` file will be placed in this same directory. If there's already a `ergodox_ez.hex` file in the directory, it will be overwritten.

Example: if you have your keymap in `~/keymaps/qwerty/keymap.c`, use the followig command line to compile it:

```
$ docker run --rm -v ~/keymaps/qwerty:/keymap potz/ergodox-ez-compiler
```

If everything goes well, The resulting .hex file will be on `~/keymaps/qwerty/ergodox_ez.hex`. You can then use this file to flash your keyboard.

## Licence

[MIT](https://opensource.org/licenses/MIT)
