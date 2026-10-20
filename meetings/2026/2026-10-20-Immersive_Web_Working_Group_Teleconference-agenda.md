### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/2026/2026-10-21-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [webxr-hand-input#129 Hand tracking frequency hint](https://github.com/immersive-web/webxr-hand-input/pull/129) [requested by cabanier](https://github.com/immersive-web/webxr-hand-input/pull/129#issuecomment-6274607963)
> We'd like to add the option to get high frequency tracking.
 >Currently, we request the default from the OS but for certain experiences that requires precise movements, high frequence tracking is required. This makes it an optional session parameter in the same way we do options for depth sensing.

* [webxr-webgpu-binding#41 WebGPU equivalent of foveateBoundTexture](https://github.com/immersive-web/webxr-webgpu-binding/issues/41) - mwyrzykowski
> The WebGL backend has this function:
 >[ foveateBoundTexture](https://www.w3.org/TR/webxrlayers-1/#dom-xrwebglbinding-foveateboundtexture)

* [model-element#109 Require HTTPS?](https://github.com/immersive-web/model-element/issues/109) [requested by cabanier](https://github.com/immersive-web/model-element/issues/109#issuecomment-6258627691)
> One of the goals of Model is to not require any sensitive data from the user/UA to display the content. On the other hand, it seems like there is a general enthusiasm for encouraging new features to require HTTPS. It's also the case that model content (be it USDZ, glTF or any other rich definition) is also a more complicated resource to parse and pull apart, so it might be understood to need HTTPS for that reason too. 
 >

* [model-element#130 What role, if any, should `poster` play?](https://github.com/immersive-web/model-element/issues/130) [requested by cabanier](https://github.com/immersive-web/model-element/issues/130#issuecomment-6258636808)
> I'm personally concerned that `poster` is under-specified for the things that an author will want to do to represent a `<model>`. First, the syntax doesn't allow for alternative file formats, for different resolutions or aspect ratios or `prefers-color-scheme` etc. Add to that the possibility that a good poster/placeholder for a `model` element _may even be another model_, and it makes me wonder whether there's an appropriate way to meet these needs at all. What does everyone else think?
 >

* [model-element#143 Environment maps: Add cubemap support alongside equirectangular images](https://github.com/immersive-web/model-element/issues/143) [requested by cabanier](https://github.com/immersive-web/model-element/issues/143#issuecomment-6161206915)
> In the [explainer](https://github.com/immersive-web/model-element/blob/main/explainer.md#dom-api), it indicates the environment map is specified as an equirectangular image.
 >

* [model-element#152 Default environment map](https://github.com/immersive-web/model-element/issues/152) [requested by cabanier](https://github.com/immersive-web/model-element/issues/152#issuecomment-6258634611)
> A `model` with no author-provided environment map is rendered with a default environment map. And `model` should render consistently across platforms, _roughly_. For this consistent rendering we would need to specify the default environment map.
 >

### Immersive Web Working Group Teleconference - 2026-10-21

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Wednesday, October 21 at 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Wednesday, October 21 at 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Wednesday, October 21 at 8:00 PM GMT+1
<tr><td> Paris (France) <td> Wednesday, October 21 at 9:00 PM GMT+2
<tr><td> Tokyo (Japan) <td> Thursday, October 22 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Wednesday, October 21 at 7:00 PM UTC
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


              
