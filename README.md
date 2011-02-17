FFMpeg4iPhone - The Next Generation! 
Build scripts for ffmpeg on iPhone SDK 4.x (and iPhone Simulator SDK).

## Scripts 

- `build-ffmpeg`: Build script for ffmpeg; Run this first and then `combine-libs`
- `combine-libs`: Creates universal binaries; Runs lipo -create on each of the ffmpeg static libs

- `build-x264`: x264 build scripts; Run these before normal build script to include x264 support
- `build-xvid`: xvid build scripts; Run these before normal build script to include xvid support
- `build-vorbis`: xvid build scripts; Run these before normal build script to include xvid support

You can set the ARCHS environment variable to limit which architectues 

e.g. export ARCHS="armv7 i386"

You can create build-local to customise your build environemnt and ffmpeg-options to set the configure options for ffmpeg. See build-local.example and ffmpeg-conf.example for examples.

## Background

For background, follow this thread:
http://lists.mplayerhq.hu/pipermail/ffmpeg-devel/2009-October/076618.html

To make lipo'able libraries, you need to use gcc-4.2 with extra cflags instead of the specific arm-apple-darwin10-gcc-4.2.1 compiler.

The armv6 arch doesn't seem to be working properly so you can force building via armv7 on your 3GS until we figure that out.

## X264, Xvid, Vorbis

For x264, Xvid, and Vorbis support in ffmpeg, run those build scripts first, and the ffmpeg build scripts will include it.

## Gas preprocessor

Uses a gas preprocessor via http://github.com/yuvi/gas-preprocessor/

