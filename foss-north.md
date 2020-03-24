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

OBS works with scenes. Each scene consists of media sources. For foss-north we use five basic scenes (and some variants):

- **Intro Splash** shown on the stream before the stream begins. This scene contains logo, link to the schedule, and a text element where we note when the next session starts.
- **Session Intro** shown in the beginning of each session. This scene contains a prerecorded video where the sponsors are thanked. It ends in out *Pause Screen* scene (or the same still picture).
- **Pause Screen** shown when doing background stuff, e.g. getting speaker's screensharing up.
- **Presentation** shows the presentation from the Zoom session. This is a screen capture of the separate screen showing the full screen Zoom session.
- **QA Screen** shown during the QA session. This scene consists of a Browser source referring to the sli.do presentation URL that can be retieved from the sli.do event administration page. This means that we do not have to capture the output of a Browser. The OBS scene contains the actual browser.

In addition to these scenes, the various audio sources can be individually muted. This includes the Zoom session with the speaker (desktop sounds), the voice of the broadcaster (mic sound), and in the *Session Intro* the prerecorded sound that comes with the clip.

Notice that the voice of the person controlling the broadcast can be muted separately in Zoom and OBS, meaning that you can speak either to the viewers, the speaker, or both.

## YouTube

T.B.D.

## Zoom

We capture a full screen version of Zoom. This means that we have a full screen zoom session on a full HD monitor that we capture using OBS.

We use a single zoom session for all speakers, which means that the next speaker joins during the end of the previous talk. This has not been a problem this far, but it is worth noting that the meeting host can mute all participants, so any noise can be removed.

It is also possible for the meeting host to revoke screen sharing to make handover between speakers easier.

Zoom usually goes full screen when someone shares the screen. Make sure to manually go to full screen before this happens, to avoid the window popping back to an ordinary window if the speaker stops sharing or drops from the call.

For the foss-north background, the desktop background behind the Zoom window is the same graphics as is used in the OBS *Pause Screen*, so if Zoom crashes, it looks to the broadcast as if we go to the *Pause Screen*.

# The Broadcast

T.B.D

* Recording in YT
* Recording in Zoom (contains the voice of the broadcast host)

* Muting of various sources
* The cut scene

# Post Event Editing

For foss-north we have prerecorded intro and exit clips consisting of full screen slides with a voice over. These intro is the same as is used in the live broadcast and this part can usually be reused. The exit clip is added after each speaker in the post production.

For editing, kdenlive is used. The YT broadcast is used as the primary video. In some cases, the Zoom recording can be used as a fallback. Various hickups (e.g. technical issues, silence during QA, bad audio) are cut out.

All screen transitions are handled with a short fade in / fade out (usually 0.5s), and all audio is also faded in and out (usually 0.25 s) to avoid clicks and pops.

# Open Issues

The following issues are left to resolve:

* Hard to notify the speaker of time left using Zoom
* YouTube comments and QA needs to be synced
