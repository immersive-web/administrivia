### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2020-02-25-Immersive_Web_Working_Group_Teleconference-agenda.md).
[Minutes](https://www.w3.org/2020/02/25-immersive-web-minutes.html) are avail from irc scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [layers#16 Should layer support be requested at session creation time?](https://github.com/immersive-web/layers/issues/16) [requested by cabanier](https://github.com/immersive-web/layers/issues/16#issuecomment-585940264)
> Should layer support be requested at session creation time?

* [webxr-input-profiles#162 Add Magic Leap Asset](https://github.com/immersive-web/webxr-input-profiles/pull/162) [requested by toji](https://github.com/immersive-web/webxr-input-profiles/pull/162#issuecomment-590488819)
> to talk about whether we should be delivering assets for AR-only devices to users.
>
>I'd love to have this asset in the repo and available for users if they have a need for it, but I'd like to have some further discussions on whether or not this is something that we should actively be pushing to users of the library, since it seems like you probably don't want to actually be rendering this asset on the intended device. If you did it would just end up rendering (probably imperfectly aligned) over the top of the real device.

### Immersive Web Working Group Teleconference - 2020-02-25

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, February 25, 12:00 PM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, February 25, 3:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday, February 25, 8:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, February 25, 9:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, February 26, 5:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, February 25, 8:00 PM UTC
</table>

### Logistics

Chair: Ada Rose Cannon

Scribe:

IRC: [irc.w3.org](http://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/master/IRC.md)

Call Details can be found on the [Internal Mailing List](https://lists.w3.org/Archives/Member/internal-immersive-web/2019Feb/0002.html)

If you are unable to login to view the call details please ask on the IRC before the call.

For assistance go to https://mit.webex.com/mit/mc  and on the left navigation bar, click "Support".

### Help Wanted

Here are some issues which are good issues to get involved in, if you have taken responsibility for one leave a comment in the issue:

- [webxr#225 Behavior of window.requestAnimationFrame and window.requestIdleCallback when presenting](https://github.com/immersive-web/webxr/issues/225) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr#603 What happens if a canvas with an xrCompatible context is attached to the DOM?](https://github.com/immersive-web/webxr/issues/603) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#736 Should calling XRSession.requestAnimationFrame in a Window.animationFrameCallback be banned?](https://github.com/immersive-web/webxr/issues/736) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#777 Requirements for native viewport size?](https://github.com/immersive-web/webxr/issues/777) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69) [<small>[Future]</small>](https://api.github.com/repos/immersive-web/webxr-input-profiles/milestones/4)
- [webxr-gamepads-module#16 Add link to the registry](https://github.com/immersive-web/webxr-gamepads-module/issues/16) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr-gamepads-module/milestones/1)
- [webxr#854 Result of calling checkFramebufferStatus on an opaque framebuffer](https://github.com/immersive-web/webxr/issues/854) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#856 Do opaque framebuffers have a reference to their XR session?](https://github.com/immersive-web/webxr/issues/856) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#860 What is a "valid feature descriptor"](https://github.com/immersive-web/webxr/issues/860) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#877 Note somewhere that you should be always be queueing up the next rAF within rAF](https://github.com/immersive-web/webxr/issues/877) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#880 Corrections and clarifications for description/steps for updateRenderState()](https://github.com/immersive-web/webxr/issues/880) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#891 Clarify semantics of preserveDrawingBuffer](https://github.com/immersive-web/webxr/issues/891) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#923 cancelAnimationFrame: clarify behavior when called from a frame callback](https://github.com/immersive-web/webxr/issues/923) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#956 Visibility state behavior is not clearly specified for inline sessions](https://github.com/immersive-web/webxr/issues/956) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)


              
