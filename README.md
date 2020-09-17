Build
=============

- Download and install a compatible driver from the NVIDIA [web site](https://www.nvidia.com/download/index.aspx?lang=en-us)
- Download and install the [CUDA toolkit](https://developer.nvidia.com/cuda-toolkit) 
- Execute the following commands under the root of this repository to build the debian package

  ```
  $ export DEB_CFLAGS_APPEND="-O3 -fdevirtualize-at-ltrans -fipa-pta"; \
    export DEB_CXXFLAGS_APPEND="-O3 -fdevirtualize-at-ltrans -fipa-pta"; \
    export DEB_LDFLAGS_APPEND="-O3 -fdevirtualize-at-ltrans -fipa-pta"
  ```

  ```
  $ sudo apt install devscripts
  $ mk-build-deps -s sudo -i 
  $ dpkg-buildpacket -b --no-sign
  ```
- More info, see https://developer.nvidia.com/blog/nvidia-ffmpeg-transcoding-guide/

- Caveats: The current setup seems not to work for i386

FFmpeg README
=============

FFmpeg is a collection of libraries and tools to process multimedia content
such as audio, video, subtitles and related metadata.

## Libraries

* `libavcodec` provides implementation of a wider range of codecs.
* `libavformat` implements streaming protocols, container formats and basic I/O access.
* `libavutil` includes hashers, decompressors and miscellaneous utility functions.
* `libavfilter` provides a mean to alter decoded Audio and Video through chain of filters.
* `libavdevice` provides an abstraction to access capture and playback devices.
* `libswresample` implements audio mixing and resampling routines.
* `libswscale` implements color conversion and scaling routines.

## Tools

* [ffmpeg](https://ffmpeg.org/ffmpeg.html) is a command line toolbox to
  manipulate, convert and stream multimedia content.
* [ffplay](https://ffmpeg.org/ffplay.html) is a minimalistic multimedia player.
* [ffprobe](https://ffmpeg.org/ffprobe.html) is a simple analysis tool to inspect
  multimedia content.
* Additional small tools such as `aviocat`, `ismindex` and `qt-faststart`.

## Documentation

The offline documentation is available in the **doc/** directory.

The online documentation is available in the main [website](https://ffmpeg.org)
and in the [wiki](https://trac.ffmpeg.org).

### Examples

Coding examples are available in the **doc/examples** directory.

## License

FFmpeg codebase is mainly LGPL-licensed with optional components licensed under
GPL. Please refer to the LICENSE file for detailed information.

## Contributing

Patches should be submitted to the ffmpeg-devel mailing list using
`git format-patch` or `git send-email`. Github pull requests should be
avoided because they are not part of our review process and will be ignored.
