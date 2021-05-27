# [MINI](https://github.com/fail0verflow/mini)-based titleID Loader

A Homebrew loader to load ANY titleID from nand

## About

While using gumboot, I couldnt find any easy way to just autoboot, or boot, to the system menu, so I'm using this code(based on [ppcskel][1], (a barebones MINI homebrew) to load the system menu using mini's `boot2_run` feature.

## Usage

This was acomplished by using MINI to load a ppcboot file which loads a title provided at compilation time. This can __NOT__ be built using the normal devkitpro compilers, you need a powerpc-elf cross-compiler, instructions for building one are available in the ppcskel repo or you can extract a [prebuilt version][2] (your miliage may vary).

To build the ppcboot file run set the `DEVKITAMATEUR` env variable to the directory containing the cross-compiler and run `make`. By default it loads the system menu, you can change the title by compiling with `make TID_HI=0x00000000 TID_LO=0x00000000`, where TID\_HI equals the high-bit for the TID and TID\_LO equals the low-bit for the title ID.

## Credits

AndyRogi for most of the heavy lifting when it came to coding, developing, and testing

A friend who loaned his time to test our code with a USBGecko, allowing Andy to find a bugged header and fix it

Lewurm & co for the original ppcskel, which Andy has fixed up for use with the compiler linked above

[1](https://github.com/AndrewPiroli/ppcskel)
[2](http://gh.andrewtech.net/assets/static/ppc-cross.tar.7z)
