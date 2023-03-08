### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2023-02-28-Immersive_Web_Working_Group_Teleconference-agenda.md). [minutes](https://www.w3.org/2023/02/21-immersive-web-minutes.html) are avilable through irc scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [layers#275 Allow higher quality filtering](https://github.com/immersive-web/layers/issues/275) [requested by cabanier](https://github.com/immersive-web/layers/issues/275#issuecomment-1416998318)
> [Meta added support](https://registry.khronos.org/OpenXR/specs/1.0/html/xrspec.html#XR_FB_composition_layer_settings) to enhance the quality of composition layers (this includes projection).
>I don't remember where we left this but when I turned this on as an experiment, video layers were visibly improved
>
> add support to layers for different quality settings

* [layers#298 Add option to skip the clearing of textures](https://github.com/immersive-web/layers/issues/298) - cabanier
> The WebXR layers spec [defines](https://immersive-web.github.io/layers/#opaque-texture) that the textures that are returned from the binding are always cleared to opaque black.
 >This feature is hard to implement without incurring GPU overhead especially when dealing with multiple layers.

* [layers#299 Remove chromaticAberrationCorrection option](https://github.com/immersive-web/layers/issues/299) - cabanier
> As far as I know, no experience has ever used this feature and it is not even hooked up in the browser anymore as OpenXR doesn't support it.
 >

* [webxr#1310 Add support for 'palmspace'](https://github.com/immersive-web/webxr/issues/1310) - cabanier
> OpenXR added support for a [palm pose](https://registry.khronos.org/OpenXR/specs/1.0/html/xrspec.html#XR_EXT_palm_pose). This allows an experience to figure out where the user's hand/palm would be when they use the standard OS controller.
 >

* [webxr#1311 Duplicated controllers behind trusted UIs](https://github.com/immersive-web/webxr/issues/1311) - emmanueljl
> If an experience doesn't hide its custom controllers when trusted/system UIs are shown, a duplicate pair of controllers will be displayed. Many experiences don't handle this properly, even when blur visibility-change is fired. It was made more apparent with our soft release of system keyboard support.[[1](https://twitter.com/emmanueljlee/status/1603550385230299136)] Currently this scenario isn't addressed in the spec, e.g. in [the Trusted UI section](https://www.w3.org/TR/webxr/#trustedenvironment-security).
 >

### Immersive Web Working Group Teleconference - 2023-02-28

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, February 28 at 11:00 AM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, February 28 at 2:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday, February 28 at 7:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, February 28 at 8:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, March 1 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, February 28 at 7:00 PM UTC
</table>

### Logistics

Chair: Ada Rose Cannon

Scribe:

IRC: [irc.w3.org](http://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/main/IRC.md)

Call Details can be found on the [Internal Mailing List](https://lists.w3.org/Archives/Member/internal-immersive-web/2019Feb/0002.html)

If you are unable to login to view the call details please ask on the IRC before the call.

For assistance go to https://mit.webex.com/mit/mc  and on the left navigation bar, click "Support".

### Help Wanted

Here are some issues which are good issues to get involved in, if you have taken responsibility for one leave a comment in the issue:

- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69) [<small>[Future]</small>](https://api.github.com/repos/immersive-web/webxr-input-profiles/milestones/4)
- [webxr#953 Typescript definitions](https://github.com/immersive-web/webxr/issues/953) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#1115 Explicitly spec when inline animation frame loops are suspended](https://github.com/immersive-web/webxr/issues/1115) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)


              
