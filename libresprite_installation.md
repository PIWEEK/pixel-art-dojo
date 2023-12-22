# LibreSprite installation guide

[LibreSprite](https://libresprite.github.io/#!/#page-top) is a free and open source program for creating and animating sprites, originated as a fork of [Aseprite](https://www.aseprite.org/).

This guide will cover how to install it in **Linux** for _Debian/Ubuntu_ distributions.
Basically, you have two options:

- **Grab an executable image**: easy installation, but an older version (v1.0-dev, Nov 17, 2021)
- **Compile the source code**: less easy, but with the latest changes (v1.1-dev, Dec 3, 2023)

You can check the [changelog](https://github.com/LibreSprite/LibreSprite/releases) to find which features are included in each version, and which installation option suits you more.

## Grab an executable image

This option it's as easy as to download your image from [here](https://github.com/LibreSprite/LibreSprite/releases) (v1.0 > Assets) and make it executable. It's a prepared binary you should be able to execute directly.

The version you may probably need it's the [libresprite-Linux-x86_64-Debian_10.AppImage](https://github.com/LibreSprite/LibreSprite/releases/download/v1.0/libresprite-Linux-x86_64-Debian_10.AppImage)

To make it executable, you can make it executable [using the UI](https://askubuntu.com/questions/484718/how-to-make-a-file-executable), or by executing `chmod +x ./libresprite-Linux-x86_64-Debian_10.AppImage` from the same directory where you downloaded the image.

Then just run it by doble click, or executing `./libresprite-Linux-x86_64-Debian_10.AppImage` in the terminal.

That's it!

## Compile the source code

This option includes the latests features and it'll should cost you not more than five minutes. I'll try to sum up the most important steps (taken from its [guide](https://github.com/LibreSprite/LibreSprite/blob/master/INSTALL.md)):

### Step 1: Install dependencies

Open a terminal and install the required dependencies:

```bash
sudo apt-get install cmake g++ libcurl4-gnutls-dev libfreetype6-dev libgif-dev libgtest-dev libjpeg-dev libpixman-1-dev libpng-dev libsdl2-dev libsdl2-image-dev libtinyxml2-dev libnode-dev ninja-build zlib1g-dev libarchive-dev
```

### Step 2: Clone the repository

Browse to the directory where you want to compile LibreAsprite.

> It won't be installed here, it's just temporary.

Get the source code:

```bash
git clone --recursive https://github.com/LibreSprite/LibreSprite
```

> NOTE: Use this exact command (with `--recursive`) to clone the repository.
>
> It'll create a new directory called "LibreSprite".

### Step 3: Compile the source

Enter the directory and create a new `build` directory inside:

```bash
cd LibreSprite
mkdir build
cd build
```

Compile the downloaded source code (from the `build`directory):

```bash
cmake -G Ninja ../usr/local/bin/libresprite
ninja libresprite
```

### Step 4: Install LibreSprite in your system

Install it with `ninja`.

```bash
sudo ninja install
```

> NOTE: `sudo` is needed because it will access `/usr/local/`.

### Step 5: Run LibreSprite

By default, the binary is placed in `/usr/local/bin` and you can execute it directly from the terminal:

```bash
/usr/local/bin/libresprite & > nohup
```

> NOTE: `nohup` will keep LibreSprite running even if you close the terminal.

Even easier, from the desktop UI, just press `Alt + F2` , type `libresprite` and press `Enter` to execute it.
