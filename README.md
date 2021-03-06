cfAudio [![Build Status](https://travis-ci.org/sanford1/cfAudio.svg?branch=master)](https://travis-ci.org/sanford1/cfAudio)
=======

Simple C++11 Audio Library. Built on top of OpenAL and libsndfile.

Basic Usage
===========

Dependencies are OpenAL, libsndfile, and the [ninja](https://martine.github.io/ninja/) build system. To build the library, run

    python bootstrap.py && ninja

Be sure to link cfAudio and make sure your compiler can find the header files in the `cfaudio` directory.

Initialize Listener:

    Listener::init();

Playing Music:

    Music music("data/MySong.ogg");
    music.play();
    music.pause();
    music.setVolume(0.5f);

Playing a Sample:

    Sample sample1("data/Coin.wav");
    sample1.play();

    Sample sample2("data/Powerup.wav");
    sample2.play();

Deinitialize Listener when done:

    Listener::deinit();

Since this library depends on libsndfile, [here](http://www.mega-nerd.com/libsndfile/#Features) is a list of compatible file formats.

Issues
===========

Playing OGG files results in some crackling noises in the background. From what I've researched, this seems to be a libsndfile problem.

Perhaps in the future, I'll switch from libsndfile to [libavformat](https://www.ffmpeg.org/libavformat.html) and [libavcodec](https://www.ffmpeg.org/libavcodec.html)
