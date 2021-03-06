sc_audio_mixer
..............

:Stable release:  unreleased

:Status:  first port to github

:Maintainer: xross

:Description:  Audio mixer component and examples


Key Features
============

* Build-time configurable input/output count mixer thread.
* Mixer threa takes samples in via a channel, and outputs mixes via another channel
* Control commands come in from a third control channel
* Includes saturation 
* Includes example use application

To Do
=====

* Add routing
* Add dB control

Firmware Overview
=================

This repo contains audio mixer and example application.

There is an example application included in this module:

    * app_example_mixer - This is a self contained test application for testing the mixer.  It passes sin waves into the mixer.

The primary module is module_audio_mixer. This contains the audio mixer module which provides mixing functionality along with an API for using it.

Issues
======

* When compiled on 11.2.2 tools the program traps on termination:
    TRAP ET: 4, SPC: 000103ee, SSR: 0, ED: 00000002 (ILLEGAL_RESOURCE: Src chanend in use)

    This appears to be an issue with the 11.2.2 tools release.

    Possible work-arounds:
        - Use platform.h and stdcore[] syntax. This enforces mapper generation on channel allocation rather than compiler
        - Use beta release of XMOS tools (available from xmos.com)

* See github issue tracking for other issues

Required Repositories
=====================

* xcommon git\@github.com:xcore/xcommon.git

Support
=======

Issues may be submitted via the Issues tab in this github repo. Response to any issues submitted as at the discretion of the maintainer for this line.
