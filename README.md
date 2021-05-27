# [MINI](https://github.com/fail0verflow/mini)-based titleID Loader

A Homebrew loader to load ANY titleID from nand

## About

While using gumboot, i couldnt find any easy way to just autoboot, or boot, to the system menu, so im using this code(based on [ppcskel](https://github.com/AndrewPiroli/ppcskel), a barebones MINI homebrew) to load the system menu using boot2_run(in theory)

## Usage

This was acomplished by using MINI to load a ppcboot file which loads a TID provided at compilation time. This can __NOT__ be built using the normal devkitpro compilers, you need the compiler AndyRogi found, it can be extracted anywhere and you need to set the `DEVKITAMATEUR` enviornment variable to point to the directory containing the files in the zip found [Here](http://gh.andrewtech.net/assets/static/ppc-cross.tar.7z)

To build the ppcboot file run `make`, by default it loads the system menu, you can change the title by compiling with `make TID_HI=0x00000000 TID_LO=0x00000000`, where TID\_HI equals the high-bit for the TID and TID\_LO equals the low-bit for the TID 

## Credits

Andyrogi for most of the heavy lifting when it came to coding, developing, and testing

A friend who loaned his time to test our code with a USBGecko, allowing Andy to find a bugged header and fix it

Lewurm & co for the original ppcskel, which Andy has fixed up for use with the compiler linked above