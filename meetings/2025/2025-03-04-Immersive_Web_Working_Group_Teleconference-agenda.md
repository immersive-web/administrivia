### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/2025/2025-03-04-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [depth-sensing#51 Raw vs Smooth Depth](https://github.com/immersive-web/depth-sensing/issues/51) [requested by alcooper91](https://github.com/immersive-web/depth-sensing/issues/51#issuecomment-2679694705)
> to discuss Intro/Should we allow both simultaneously.

* [depth-sensing#52 Pause/Resume Depth Data](https://github.com/immersive-web/depth-sensing/issues/52) - alcooper91
> Processing Depth Data can be costly, and applications may only need it for part of the time (e.g. when a user is actively moving/placing an item). Should we add a pause/resume mechanism to the depth sensing spec?
 >

* [depth-sensing#53 Should we reconsider the API shape?](https://github.com/immersive-web/depth-sensing/issues/53) [requested by alcooper91](https://github.com/immersive-web/depth-sensing/issues/53#issuecomment-2679712524)
> @cabanier @bialpio FYI
>
> to raise awareness

* [layers#310 Add ability to foveate a render target](https://github.com/immersive-web/layers/issues/310) - cabanier
> [three.js](https://threejs.org/) is moving to a [2 (or more) pass solution](https://github.com/mrdoob/three.js/pull/30387).
 >This creates a problem for foveation since it's only applied to the textures of the swapchain. If we want to preserve foveation, we'd have to first render to the swapchain texture, then copy it to a regular one and then apply the second pass.

* [webxr#1401 Pages intentionally submitting clean/empty frames](https://github.com/immersive-web/webxr/issues/1401) - alcooper91
> We recently encountered an issue in Chrome where one of the test pages was pumping frames (e.g. successfully requesting animation frames), but not actually drawing anything. As a result, Chrome ended up showing our immersive equivalent of the "sad tab" page. This may be partially covered by: https://immersive-web.github.io/webxr/#ref-for-dom-xrrenderstate-baselayer%E2%91%A7
 >

### Immersive Web Working Group Teleconference - 2025-03-04

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, March 4 at 11:00 AM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, March 4 at 2:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday, March 4 at 7:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, March 4 at 8:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, March 5 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, March 4 at 7:00 PM UTC
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


         
