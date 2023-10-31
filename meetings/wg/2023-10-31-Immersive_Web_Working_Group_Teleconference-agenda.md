### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2023-10-31-Immersive_Web_Working_Group_Teleconference-agenda.md). [Minutes](https://www.w3.org/2023/10/31-immersive-web-minutes.html) are available through scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [depth-sensing#37 WebXR Depth Sensing Module: What is DepthInfo.normDepthBufferFromNormView matrix? ](https://github.com/immersive-web/depth-sensing/issues/37) [requested by cabanier](https://github.com/immersive-web/depth-sensing/issues/37#issuecomment-1758641246)
> do we need normDepthBufferFromNormView?

* [real-world-geometry#40 Providing a clear signal for when we should call initiateRoomCapture](https://github.com/immersive-web/real-world-geometry/issues/40) [requested by cabanier](https://github.com/immersive-web/real-world-geometry/issues/40#issuecomment-1783615036)
> define a signal to tell the developer that room setup finished iniitializing

* [depth-sensing#43 Add depthNear and depthFar to XRDepthInformation ](https://github.com/immersive-web/depth-sensing/issues/43) - cabanier
> I noticed that the IDL for XRDepthInformation in Chromium has `depthNear` and `depthFar` but they are not defined in the spec. @bialpio, should we document those?
 >OpenXR depth sensing also exposes them so it seems they're needed.

* [layers#304 Create algorithm to assign indices for texture arrays](https://github.com/immersive-web/layers/issues/304) - cabanier
> While writing the depth sensing spec, @toji remarked that we need to handle the case where there can be more than 2 textures for certain devices. Currently the spec only handles at more 2.
 >/agenda how should we assign indices for texture arrays if there are more than 2 views?


### Immersive Web Working Group Teleconference - 2023-10-31

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, October 31 at 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, October 31 at 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, October 31 at 7:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, October 31 at 8:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, November 1 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, October 31 at 7:00 PM UTC
</table>

### Logistics

Chair: Ayşegül Yönet

Scribe:

IRC: [irc.w3.org](https://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/main/IRC.md)

Call Details can be found in the Immersive Web Event Calendars: [WG](https://www.w3.org/groups/wg/immersive-web/calendar/)/[CG](https://www.w3.org/groups/cg/immersive-web/calendar/)

You subscribe to these calendars with your calendar application of choice for more convenient access to the call details. See details at Export options section in [WG](https://www.w3.org/groups/wg/immersive-web/calendar/#export)/[CG](https://www.w3.org/groups/cg/immersive-web/calendar/#export).

If you are unable to login to view the call details please ask on the IRC before the call.

### Help Wanted

Here are some issues which are good issues to get involved in, if you have taken responsibility for one leave a comment in the issue:

- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69) [<small>[Future]</small>](https://api.github.com/repos/immersive-web/webxr-input-profiles/milestones/4)
- [webxr#953 Typescript definitions](https://github.com/immersive-web/webxr/issues/953) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#1115 Explicitly spec when inline animation frame loops are suspended](https://github.com/immersive-web/webxr/issues/1115) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [proposals#82 Some sort of local shared space](https://github.com/immersive-web/proposals/issues/82)


              
