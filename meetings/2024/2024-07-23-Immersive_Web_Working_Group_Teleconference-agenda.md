### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/2024/2024-07-23-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [depth-sensing#45 `normDepthBufferFromNormView` in XRDepthInformation is not a rigid transform](https://github.com/immersive-web/depth-sensing/issues/45) [requested by cabanier](https://github.com/immersive-web/depth-sensing/issues/45#issuecomment-2192481837)
> After talking to our people working on depth sensing, we potentially need another change to the interface and we *might* need update to how occlusion is implemented.
>I invited one of the engineers to come talk to us during a weekly call
>
> discuss needed changes to depth sensing spec + implementation

* [webxr-gamepads-module#60 Address contradiction on whether XRInputSource gamepads are exposed](https://github.com/immersive-web/webxr-gamepads-module/pull/60) [requested by toji](https://github.com/immersive-web/webxr-gamepads-module/pull/60#issuecomment-2237331223)
> Hm... this is a bit more complex that it may appear at first.
>
>For the record the text from the "Navigator" section has been in this repo since commit #1, so there's no obvious paper trail as to the discussion that led to it. The other text was merged in #49, which points to #19, which also is unfortunately light on discussion but at least provides some context: Browsers wanted to ability to use controllers as more traditional gamepads for non-XR content. The group agreed that this was a good idea and the text was added to support that use case.
>
>The complication comes from this: Yes, you can show XR controllers as standard gamepads if the user agent wants to. But can you have them in the gamepads array AND as an XRInputSource on an active session at the same time? I'm inclined to say no, and I think that's what this (admittedly confusing) apparent text contradiction is trying to say.
>
>When the text says "An XRInputSource's associated Gamepad MAY be exposed via navigator.getGamepads()" I think it's using "XRInputSource" not necessarily as an actual `XRInputSource` instance attached to an `XRSession` but as a more abstract "Input source for an XR device that may be exposed as an `XRInputSource` instance at some point." (Yes, that's confusing. I blame myself.) It would make sense to me to say that a controller can be exposed as a typical gamepad if the UA wants up until an `XRSession` is started. If the controller then shows up as an input source for that session it MUST NOT appear in the normal gamepad list until the session has ended. That way we avoid getting accidental double-processing of inputs and it's very clear which interfaces developers should be looking to in order to handle XR input.
>
>That being said, this obviously needs some clearer text all around, and regardless of my speculating above I think the more important consideration at this point is what are implementations currently doing and how might existing content break if we make changes here. As such I think this is a great topic for our next meeting.

* [model-element#88 Fresh run at the introduction section](https://github.com/immersive-web/model-element/pull/88) [requested by zachernuk](https://github.com/immersive-web/model-element/pull/88#issuecomment-2215469193)
> Re-framed the scope of what a declarative element being managed directly by the user agent actually has the ability to achieve!
 >

* [model-element#89 Expand and revise examples section](https://github.com/immersive-web/model-element/pull/89) [requested by zachernuk](https://github.com/immersive-web/model-element/pull/89#issuecomment-2215496417)
> Added the examples already sketched out in the document and added some more based on a tentative approach to MVP functionality.
 >

* [hit-test#117 Use of FrozenArray<>s for return types of methods is probably unnecessary](https://github.com/immersive-web/hit-test/issues/117) [requested by toji](https://github.com/immersive-web/hit-test/issues/117#issuecomment-2150866464)
> I think the intent WAS for this to be an optimization. It's worth discussing with the larger group, so queuing this topic up for a future call.

* [administrivia#207 TPAC 2024 Meetings](https://github.com/immersive-web/administrivia/issues/207) - Yonet
> Remind to Sign up link:  https://www.w3.org/2024/09/TPAC/
 >

* [webxr#1377 Spec is unclear how a reference space event is handled](https://github.com/immersive-web/webxr/issues/1377) - cabanier
> A reference space even is supposed to have a event that fires if it is reset (ie by holding down the meta button on quest).
 >This event has a transform that indicates the delta pose between the previous space.

### Immersive Web Working Group Teleconference - 2024-07-23

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, July 23 at 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, July 23 at 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, July 23 at 8:00 PM GMT+1
<tr><td> Paris (France) <td> Tuesday, July 23 at 9:00 PM GMT+2
<tr><td> Tokyo (Japan) <td> Wednesday, July 24 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, July 23 at 7:00 PM UTC
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


              Agenda has been copied to clip board, paste here.
