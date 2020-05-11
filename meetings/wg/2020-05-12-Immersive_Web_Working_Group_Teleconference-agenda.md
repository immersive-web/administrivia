
We're getting really close it the Pre-CR milestone for WebXR, please take a look
at some of the issues in the footer of this email
to see if there are any you can handle.

### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2020-05-12-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.


* [webxr#674 Should requestReferenceSpace() wait until getViewerPose() won't be null?](https://github.com/immersive-web/webxr/issues/674) [requested by toji](https://github.com/immersive-web/webxr/issues/674#issuecomment-625929786)
> to try and clear out some of the older pre-CR issues.

* [webxr#743 Allow sensitive UI to make use of the `visible-blurred` state](https://github.com/immersive-web/webxr/issues/743) [requested by Manishearth](https://github.com/immersive-web/webxr/issues/743#issuecomment-625932705)
> So a lot has changed since this issue was filed. We do have a more concrete concept of trusted UI.
>
>_Currently_, the spec says:
>
>> The ability to read input information (head pose, input pose, etc) poses a risk to the integrity of trusted UI as the page may use this information to snoop on the choices made by the user while interacting with the trusted UI. To prevent this risk the user agent MUST set the visibility state of all XRSessions to "hidden" when the user is interacting with trusted UI (immersive or non-immersive) such as URL bars or system dialogs. 
>
>This would essentially involve allowing visible-blurred in this paragraph, which allows for head pose (and no input) to be read.
>
> Are we okay with applications knowing head poses (and head poses only) while displaying trusted UI?
>
>cc @avadacatavra

* [webxr#980 Add XRInputSourceEvent::{screenX, screenY}](https://github.com/immersive-web/webxr/pull/980) [requested by AdaRoseCannon](https://github.com/immersive-web/webxr/pull/980#issuecomment-625104537)
> to run by the group again before merging

### Immersive Web Working Group Teleconference - 2020-05-12

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, May 12, 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, May 12, 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, May 12, 8:00 PM GMT+1
<tr><td> Paris (France) <td> Tuesday, May 12, 9:00 PM GMT+2
<tr><td> Tokyo (Japan) <td> Wednesday, May 13, 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, May 12, 7:00 PM UTC
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
- [webxr#363 Clarification of mouse behavior when in an exclusive view](https://github.com/immersive-web/webxr/issues/363) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#603 What happens if a canvas with an xrCompatible context is attached to the DOM?](https://github.com/immersive-web/webxr/issues/603) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#736 Should calling XRSession.requestAnimationFrame in a Window.animationFrameCallback be banned?](https://github.com/immersive-web/webxr/issues/736) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69) [<small>[Future]</small>](https://api.github.com/repos/immersive-web/webxr-input-profiles/milestones/4)
- [webxr-gamepads-module#16 Add link to the registry](https://github.com/immersive-web/webxr-gamepads-module/issues/16) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr-gamepads-module/milestones/1)
- [webxr#854 Result of calling checkFramebufferStatus on an opaque framebuffer](https://github.com/immersive-web/webxr/issues/854) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#880 Corrections and clarifications for description/steps for updateRenderState()](https://github.com/immersive-web/webxr/issues/880) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#913 Context loss handling in makeXRCompatible does not make sense](https://github.com/immersive-web/webxr/issues/913) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#933 Clarify that offset spaces inherit reset events and bounds changes](https://github.com/immersive-web/webxr/issues/933) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#1014 Document possible side effects of making a context xrCompatible](https://github.com/immersive-web/webxr/issues/1014) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)


              
