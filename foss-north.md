# The foss-north Setup

This page describes the virtual conference setup of foss-north. This was deployed during [foss-north 2020](https://foss-north.se/2020).

# Overview

The foss-north was conducted as a live event with QA after each talk, but all sessions where also published for non-live consumption after the event.

The setup is illustrated in the figure below:

![Image fo the foss-north setup](images/fn-overview.png)

The setup consists of the following services:

Service | Web site | Usage
--------|----------|------
![Zoom](images/logo-zm.png) Zoom | https://zoom.us | Video conferencing system for live talks
![sli.do](images/logo-sdo.png) sli.do | https://sli.do | QA system
![VLC](images/logo-vlc.png) VLC | https://www.videolan.org/vlc/ | Media player for pre-recorded talks
![OBS](images/logo-obs.png) OBS | https://obsproject.com/ | Broadcasting and recording program
![YouTube](images/logo-yt.png) YouTube | https://youtube.com | Video streaming and hosting service
![ConfTube](images/logo-pt.png) ConfTube | https://conf.tube | Video hosting service

The live event is broadcasted to YouTube. After the event, the videos are published to YouTube and ConfTube after editing.

During the live event, each speaker joins a Zoom conference with the broadcaster. The Zoom conference is captured using OBS for broadcasting.

The OBS program also captures a view of sli.do, as well as various clips.

For pre-recorded sessions, VLC is used to play back the clip. The speaker is then joining the Zoom conference for the QA part.

The QA consists of questions entered into sli.do by the viewers, which are read to the speaker in the Zoom conference. This has turned out to be the best way to ask questions, as the live broadcasting introduces a lag.

# Tool Configurations

## OBS

T.B.D.

## YouTube

T.B.D.

## Zoom

T.B.D.

# The Broadcast

T.B.D

* Muting of various sources
* The cut scene

# Post Event Editing

T.B.D.

# Open Issues

The following issues are left to resolve:

* Hard to notify the speaker of time left using Zoom
* YouTube comments and QA needs to be synced
