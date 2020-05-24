### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2020-05-26-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [administrivia#96 Virtual TPAC???](https://github.com/immersive-web/administrivia/issues/96) - AdaRoseCannon
> /agenda to work out what we want to do for tpac.

* [webxr#1036 "Ensure an immersive device" cannot be run in parallel](https://github.com/immersive-web/webxr/issues/1036) [requested by Manishearth](https://github.com/immersive-web/webxr/issues/1036#issuecomment-629598102)
> I see four rough options:
>
> 1. Remove the `xrCompatible` flag from `getContext()`, notify users that they should use `makeXRCompatible()` instead, which is asynchronous. This will break existing content unless we stop erroring when the [`XR compatible`](https://immersive-web.github.io/webxr/#xr-compatible)  flag is not set. 
> 2. Same as (1), but we also stop erroring when the [`XR compatible`](https://immersive-web.github.io/webxr/#xr-compatible) flag is not set. This will not break existing content because browsers do not do anything meaningful with this flag _yet_, but existing content may continue to obliviously use this flag and eventually break when browsers start handling this. Furthermore, the "context isn't xr compatible" error is _useful_On the other hand, it gets rid of the `partial dictionary` and the weird `getContext()`-patching we're doing which isn't very kosher anyway.
> 3. Allow `xrCompatible` to introduce slow sync behavior in `getContext()`, perhaps with a deprecation warning. This is not great; slow sync APIs are bad
> 4. Have `.getContext({xrCompatible: true})` behave like `.getContext()` + `makeXRCompatible()`, where we create a context for the device if we know what it is, otherwise create a normal context, and then trigger context loss/restore if it turns out that we were supposed to create a different context. This is slightly weird and applications may be forced to handle the context loss event in select cases on select devices. In a perfect world they would be doing this anyway, however I suspect a lot of content isn't. This puts us in a similar bucket as 2., where this is not a breaking change, but when browsers implement this we will start having problems, and that too only with specific devices.
>
> Our current spec makes the `getContext()` API block, which is really bad and we should discuss ways to avoid that. None of the choices are particularly good

* [webxr#1041 Reporting pose data depends on the state of the document?](https://github.com/immersive-web/webxr/issues/1041) [requested by Manishearth](https://github.com/immersive-web/webxr/issues/1041#issuecomment-629449069)
> cc @avadacatavra
>
> for discussions of security implications

* [webxr#1058 Various changes around null and emulated poses](https://github.com/immersive-web/webxr/pull/1058) [requested by Manishearth](https://github.com/immersive-web/webxr/pull/1058#issuecomment-632927233)
> to discuss the changes being made here

### Immersive Web Working Group Teleconference - 2020-05-26

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, May 26, 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, May 26, 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, May 26, 8:00 PM GMT+1
<tr><td> Paris (France) <td> Tuesday, May 26, 9:00 PM GMT+2
<tr><td> Tokyo (Japan) <td> Wednesday, May 27, 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, May 26, 7:00 PM UTC
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

- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr#363 Clarification of mouse behavior when in an exclusive view](https://github.com/immersive-web/webxr/issues/363) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#603 What happens if a canvas with an xrCompatible context is attached to the DOM?](https://github.com/immersive-web/webxr/issues/603) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69) [<small>[Future]</small>](https://api.github.com/repos/immersive-web/webxr-input-profiles/milestones/4)
- [webxr-gamepads-module#16 Add link to the registry](https://github.com/immersive-web/webxr-gamepads-module/issues/16) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr-gamepads-module/milestones/1)
- [webxr#913 Context loss handling in makeXRCompatible does not make sense](https://github.com/immersive-web/webxr/issues/913) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/3)
- [webxr#1045 Discuss video capture "third eye" views and quad displays](https://github.com/immersive-web/webxr/issues/1045)


              
