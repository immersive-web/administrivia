### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2019-10-22-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* Check out the bottom of the agenda for issues which are looking for help.
* Discussion about XRSessionModes: https://github.com/immersive-web/webxr-ar-module/issues/28, https://github.com/immersive-web/webxr-ar-module/pull/38
> Finalize [the enum move](https://github.com/immersive-web/webxr-ar-module/pull/38), and discuss [Brandon's comment about having two immersive modes](https://github.com/immersive-web/webxr-ar-module/issues/28#issuecomment-540811746)
* [webxr-ar-module#29 Should handheld and headset AR use the same XRSessionMode?](https://github.com/immersive-web/webxr-ar-module/issues/29) + [webxr-ar-module#9 Enable developers to distinguish between screen-based and head-worn sessions](https://github.com/immersive-web/webxr-ar-module/issues/9) (Manish)
> Discuss how best to expose that the UI is screen-based vs headworn, and whether or not we should block on DOM overlay.
* [webxr-gamepads-module#18 Ensure that the returned gamepad object is live](https://github.com/immersive-web/webxr-gamepads-module/issues/18) [requested by NellWaliczek](https://github.com/immersive-web/webxr-gamepads-module/issues/18#issuecomment-540758145)
> Agenda to confirm the expected behavior from the Gamepad folks and get consensus on which approach we intend to take.
* [webxr-input-profiles#79 Do fallback profiles need to contain only subset of componenents?](https://github.com/immersive-web/webxr-input-profiles/issues/79) [requested by NellWaliczek](https://github.com/immersive-web/webxr-input-profiles/issues/79#issuecomment-540135141)
> Filed #100 to specifically address the Oculus Touch profile.
>
> To gather opinions on what the general guidelines ought to be
* [webxr-input-profiles#82 UA reserved buttons](https://github.com/immersive-web/webxr-input-profiles/issues/82) [requested by NellWaliczek](https://github.com/immersive-web/webxr-input-profiles/issues/82#issuecomment-540136280)
> I'll take a poke at the right schema changes to support tracking this in the registry.  In the meanwhile...
>
> To learn which buttons should be documented as reserved for each profile
* [webxr-input-profiles#14 Add behavior for unknown gamepads](https://github.com/immersive-web/webxr-input-profiles/issues/14) [requested by NellWaliczek](https://github.com/immersive-web/webxr-input-profiles/issues/14#issuecomment-544731669)
> When this issue was originally filed, we were still figuring out the details of the `profiles` attribute.  Now that we've gotten further along, a few other things should be considered:
>1.  In some cases the UA will be unable to identify a vendor-prefixed string.  Should `profiles = []` in that case?  What if a `generic` prefixed string can be identified?
>1. In some cases the UA will allow users to hide the actual vendor-prefixed information.  Should `profiles=[]` or should a generic be reported? If so, is it up to the UA to decide how specific that generic is (i.e. if `generic-trigger-grip` is valid, should `generic-trigger` ever be returned?)
>1. If we decide to add `squeeze` events, does the `profiles` array need to indicate that this event can be fired?
>1. If we allow `profiles` to be an empty array, do we have any concerns about developers falling into a pit of failure?
>1. Is there any situation in which `""` would be a valid profile id?
### Immersive Web Working Group Teleconference - 2019-10-22

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, October 22, 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, October 22, 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, 22 October, 20:00 BST
<tr><td> Paris (France) <td> Tuesday, 22 October, 21:00 CEST
<tr><td> Tokyo (Japan) <td> Wednesday, 23 October, 04:00 GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, 22 October, 19:00 UTC
</table>

### Logistics

Chair: Chris Wilson, Ada Rose Cannon

Scribe:

IRC: [irc.w3.org](http://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/master/IRC.md)

Call Details can be found on the [Internal Mailing List](https://lists.w3.org/Archives/Member/internal-immersive-web/2019Feb/0002.html)

If you are unable to login to view the call details please ask on the IRC before the call.

For assistance go to https://mit.webex.com/mit/mc  and on the left navigation bar, click "Support".

### Help Wanted

Here are some issues which are good issues to get involved in, if you have taken responsibility for one leave a comment in the issue:

- [webxr#225 Behavior of window.requestAnimationFrame and window.requestIdleCallback when presenting](https://github.com/immersive-web/webxr/issues/225)
- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr#603 What happens if a canvas with an xrCompatible context is attached to the DOM?](https://github.com/immersive-web/webxr/issues/603)
- [webxr#679 Consider removing XRWebGLLayer's `context` attribute](https://github.com/immersive-web/webxr/issues/679)
- [webxr#736 Should calling XRSession.requestAnimationFrame in a Window.animationFrameCallback be banned?](https://github.com/immersive-web/webxr/issues/736)
- [webxr#776 Remove unnecessary or redundant information from "Security, Privacy, and Comfort Considerations" ](https://github.com/immersive-web/webxr/issues/776)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69)
- [webxr-gamepads-module#16 Add link to the registry](https://github.com/immersive-web/webxr-gamepads-module/issues/16)
- [webxr#854 Result of calling checkFramebufferStatus on an opaque framebuffer](https://github.com/immersive-web/webxr/issues/854)
- [webxr#856 Do opaque framebuffers have a reference to their XR session?](https://github.com/immersive-web/webxr/issues/856)
- [webxr#860 What is a "valid feature descriptor"](https://github.com/immersive-web/webxr/issues/860)
- [webxr#877 Note somewhere that you should be always be queueing up the next rAF within rAF](https://github.com/immersive-web/webxr/issues/877)
- [webxr#880 Corrections and clarifications for description/steps for updateRenderState()](https://github.com/immersive-web/webxr/issues/880)
- [webxr#891 Clarify semantics of preserveDrawingBuffer](https://github.com/immersive-web/webxr/issues/891)


        
