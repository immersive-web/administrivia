### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/2026/2026-03-24-Immersive_Web_Community_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [anchors#78 Proposal to allow management of persistent anchors](https://github.com/immersive-web/anchors/pull/78) [requested by alcooper91](https://github.com/immersive-web/anchors/pull/78#issuecomment-4111548373)
> Should this be addressed?

* [anchors#87 Clarify RestorePersistentAnchors logic](https://github.com/immersive-web/anchors/issues/87) - alcooper91
> The algorithm for [RestorePersistentAnchor](https://immersive-web.github.io/anchors/#ref-for-dom-xrsession-restorepersistentanchor), makes reference to throwing if the page does not have the UUID in it's list of persistent anchors. However, if I understand correctly the premise of the persistent anchor portion of the API is that it would allow sites to restore these anchors across multiple sessions. Thus, it seems highly plausible to me that a common use case would be the site *not* having this UUID in it's list of persistent anchors and fetching the anchor from the device? Any reference to the list of persistent anchors for restoration should be either to short-circuit restoring an already restored anchor (or throwing), or to add the UUID to the list of known persistent anchors?
 >

* [proposals#92 Add waveform input to the gamepad haptics](https://github.com/immersive-web/proposals/issues/92) - cabanier
> In https://github.com/immersive-web/webxr/issues/1423 I asked about better haptics support.
 >A lot of movement happened in haptics since I made that suggestion and it seems that most platforms now support some sort of audio based haptics API.

* [layers#324 Width and height of XRQuadLayer are actually half width and half height](https://github.com/immersive-web/layers/issues/324) [requested by cabanier](https://github.com/immersive-web/layers/issues/324#issuecomment-4047649412)
> discuss incorrect width/height behavior

* [webxr#1396 Confusion around actual and internal visiblity](https://github.com/immersive-web/webxr/issues/1396) [requested by ibytergj](https://github.com/immersive-web/webxr/issues/1396#issuecomment-4006379250)
> So my use case right now is in VR when the user takes off their headset. I want to signal to the system that the avatar should go into an idle pose so that the avatar is just not collapsing, whichever way the handset and controllers happen to be put down. If the headset supports the information like the quest  3 does, it would be very useful if this information was available to us to implement for a better user experience.

### Immersive Web Community Group Teleconference - 2026-03-24

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, March 24 at 11:00 AM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, March 24 at 2:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, March 24 at 6:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, March 24 at 7:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, March 25 at 3:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, March 24 at 6:00 PM UTC
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


              
