### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2020-08-11-Immersive_Web_Working_Group_Teleconference-agenda.md). [Minutes](https://www.w3.org/2020/08/11-immersive-web-minutes.html) are available from the IRC scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [webxr-hand-input#36 Standardize the base set of joints](https://github.com/immersive-web/webxr-hand-input/issues/36) [requested by Manishearth](https://github.com/immersive-web/webxr-hand-input/issues/36#issuecomment-666470539)
> to quickly check with the group

* [webxr#1091 Bring back requestViewportScaling?](https://github.com/immersive-web/webxr/issues/1091) [requested by klausw](https://github.com/immersive-web/webxr/issues/1091#issuecomment-670792576)
> @thetuvix , does comment https://github.com/immersive-web/webxr/issues/1091#issuecomment-663778266 address your concerns?
>
>To move this forward, can we revisit this in one of the next meetings? We had a few API variants under discussion, I'd propose the following to make it more concrete:
>
>* modify the existing `XRWebGLLayer.getViewport(XRView)` method to optionally take an additional numeric scale argument. A missing argument or undefined scale value is treated as using the default scale.
>* Add an optional read-only `XRView.recommendedViewportScale` numeric attribute where the UA can provide a suggested value for the current frame's viewport scale based on performance heuristics. UAs can leave this undefined if they don't have such a heuristic. (Application must not assume that this is a defined numeric value.)
>
>I think this should be forwards and backwards compatible. If an application uses `xrWebGLLayer.getViewport(xrView, xrView.recommendedViewportScale)` on a UA that doesn't support viewport scaling, the UA ignores the extra argument, and looking up the recommended viewport scale harmlessly returns _undefined_. Conversely, an application that's unaware of using viewport scaling can continue to call `xrWebGLLayer.getViewport(xrView)` to get default-sized viewports.
>
>As far as the specification is concerned, I think the needed changes would be something like this (handwavingly):
>
>* reinterpret the currently described _list of viewports_ for the _XRWebGLLayer_ as the _list of full-sized viewports_ corresponding to scale=1.0. These stay unchanged for the lifetime of a session.
>* add a _list of scaled viewports_, where each entry consists of:
>  * a _scaled viewport_ which is a sub-rectangle of the _full-sized viewport_ for that view, initially full-sized 
>  * a _modifiable_ boolean, initially false 
>* before the _update the viewports_ step at the start of an animation frame, if the UA supports viewport scaling, mark each viewport in the _list of scaled viewports_ as modifiable
>* in the _getViewport(view, scale)_ method:
>  * get the viewport from the _list of scaled viewports_
>  * if the viewport is modifiable:
>    * calculate a new _viewport scale_ based on the supplied scale (or default 1.0 if the requested scale is undefined), and applying any applicable UA constraints such as a minimum scale. Maximum scale is 1.0.
>    * update the viewport's x/y/width/height attributes based on the new scale, using a subrectangle of the corresponding _full-sized viewport_ chosen by the UA
>    * set _modifiable_ to false for this viewport
>  * return the _scaled viewport_. (Its current scale may be different from the requested scale if it wasn't modifiable.)
>
>The goal of this is that a viewport's scale is only modifiable once within a given animation frame, and is then locked in for the rest of the animation frame. Also, a view's viewport will only change as a result of calling `getViewport` for that view, and will remain the same for future frames. As long as an application follows each `getViewport` call with a matching `gl.viewport` setting, it'll get correct rendering even if it is inconsistent about requested scale factors or if it only applies scaling to some views.
>
>I added the constraint that the scaled viewports must each be fully contained within the corresponding original full-sized viewport. This ensures that each view can always be resized individually even if the other views aren't getting changed in this frame. Initially I thought it might be useful to let the UA change locations more freely, i.e. to keep two undersized eye views packed together in the top left corner of the framebuffer, but that would require moving other views to avoid overlap even if the application didn't call getViewport for them. UAs could still get contiguous viewports in some cases if desired, i.e. by arranging left/right eye views symmetrically around the middle of the framebuffer.
>
> to discuss this proposal and potential alternatives

### Immersive Web Working Group Teleconference - 2020-08-11

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, August 11, 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, August 11, 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, August 11, 8:00 PM GMT+1
<tr><td> Paris (France) <td> Tuesday, August 11, 9:00 PM GMT+2
<tr><td> Tokyo (Japan) <td> Wednesday, August 12, 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, August 11, 7:00 PM UTC
</table>

### Logistics

Chair: Ayşegül Yönet

Scribe:

IRC: [irc.w3.org](http://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/main/IRC.md)

Call Details can be found on the [Internal Mailing List](https://lists.w3.org/Archives/Member/internal-immersive-web/2019Feb/0002.html)

If you are unable to login to view the call details please ask on the IRC before the call.

For assistance go to https://mit.webex.com/mit/mc  and on the left navigation bar, click "Support".

### Help Wanted

Here are some issues which are good issues to get involved in, if you have taken responsibility for one leave a comment in the issue:

- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69) [<small>[Future]</small>](https://api.github.com/repos/immersive-web/webxr-input-profiles/milestones/4)
- [webxr-gamepads-module#16 Add link to the registry](https://github.com/immersive-web/webxr-gamepads-module/issues/16) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr-gamepads-module/milestones/1)
- [webxr#953 Typescript definitions](https://github.com/immersive-web/webxr/issues/953) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#1110 Update the reference to Feature Policy](https://github.com/immersive-web/webxr/issues/1110) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)


              
