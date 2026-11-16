### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/2026/2026-11-17-Immersive_Web_Community_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [model-element#58 Interactions with HTMLCanvasElement](https://github.com/immersive-web/model-element/issues/58) [requested by cabanier](https://github.com/immersive-web/model-element/issues/58#issuecomment-6465836582)
> We need to define how models render for HTML-to-Canvas and drawImage or their WebGL and WebGPU equivalents.
>I propose that it uses fallback content in those cases. We may also decide the show the left eye view of the current animation frame which may be difficult to implement...

* [model-element#68 Specify fallback model for performance issues](https://github.com/immersive-web/model-element/issues/68) [requested by cabanier](https://github.com/immersive-web/model-element/issues/68#issuecomment-6453423567)
> We should make sure the spec says something about the browser being able to drop the model on the floor if it's consuming too many resources or will make the user uncomfortable.

* [model-element#91 Exposing computed boundingBox information](https://github.com/immersive-web/model-element/issues/91) [requested by cabanier](https://github.com/immersive-web/model-element/issues/91#issuecomment-6453784830)
> The spec currently calculates the boundingbox based on the [first frame of the animation](https://immersive-web.github.io/model-element/#bounding-box-calculation-algorithm) so it doesn't cover if the animation change the model's dimension.
>Apple is currently not exposing the model's bounds. Are they still interesting in doing so?

* [proposals#96 Discuss approach to OpenXR spatial containers](https://github.com/immersive-web/proposals/issues/96) [requested by toji](https://github.com/immersive-web/proposals/issues/96#issuecomment-6807099853)
> ### Title of proposal
 >

* [model-element#117 Environment map rotation](https://github.com/immersive-web/model-element/issues/117) [requested by cabanier](https://github.com/immersive-web/model-element/issues/117#issuecomment-6454534048)
> Model element supports setting a environment map via the `environmentMap` attribute.
 >

* [model-element#186 Define model source selection and mutation handling](https://github.com/immersive-web/model-element/pull/186) [requested by cabanier](https://github.com/immersive-web/model-element/pull/186#issuecomment-6494752634)
> Review how model picks its resource.

### Immersive Web Community Group Teleconference - 2026-11-17

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, November 17 at 11:00 AM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, November 17 at 2:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday, November 17 at 7:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, November 17 at 8:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, November 18 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, November 17 at 7:00 PM UTC
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


              
