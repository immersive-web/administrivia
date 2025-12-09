### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/2025/2025-12-09-Immersive_Web_Working_Group_Teleconference-agenda.md). [Minutes](https://www.w3.org/2025/12/09-immersive-web-minutes.html) are available through scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [plane-detection#54 initiateRoomCapture returns a promise but throws](https://github.com/immersive-web/plane-detection/issues/54) [requested by alcooper91](https://github.com/immersive-web/plane-detection/issues/54#issuecomment-3628303412)
> It feels a bit weird to throw from a method that returns a promise. Wasn't there a complaint from the TAG in the past around the `isSessionSupported` method that lead to us rejecting with the given errors instead of throwing?
>
> tentatively to discuss with the broader group.


* [webxr-hand-input#127 Surface hand meshes](https://github.com/immersive-web/webxr-hand-input/issues/127) [requested by AdaRoseCannon](https://github.com/immersive-web/webxr-hand-input/issues/127#issuecomment-3565112426)
> sorry didn't get to it during the face to face

* [webxr#1420 Dynamic Foveation](https://github.com/immersive-web/webxr/issues/1420) [requested by AdaRoseCannon](https://github.com/immersive-web/webxr/issues/1420#issuecomment-3565082272)
> For WebGL this could just be a boolean we develop under WebXR
>
>For WebGPU we will need support for VRR and it would just happen there, then in WebXR we state how we would produce a resource to be compatible with this.

* [webxr#1423 Better haptics support](https://github.com/immersive-web/webxr/issues/1423) - cabanier
> We've been waiting for several years for better support for haptics.
 >It seems that only immersive devices are interested in this feature so maybe we should just implement this in WebXR?

### Immersive Web Working Group Teleconference - 2025-12-09

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, December 9 at 11:00 AM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, December 9 at 2:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday, December 9 at 7:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, December 9 at 8:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, December 10 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, December 9 at 7:00 PM UTC
</table>

### Logistics

Chair: Ada Rose Cannon

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


              
