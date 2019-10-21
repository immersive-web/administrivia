### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2019-10-29-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [webxr-gamepads-module#18 Ensure that the returned gamepad object is live](https://github.com/immersive-web/webxr-gamepads-module/issues/18) [requested by NellWaliczek](https://github.com/immersive-web/webxr-gamepads-module/issues/18#issuecomment-540758145)
> Hold on... I'm a bit unsure this was the conclusion from that conversation.  In fact, from my recollection it was the opposite thing they were asking us to do.  To make sure that the Gamepad object on an XRInputSource was different every time it was requested.  The implication of which would be revisiting if the gamepad should be an attribute or have a getter function.
>
> To confirm the expected behavior from the Gamepad folks and get consensus on which approach we intend to take.

* [webxr-ar-module#29 Should handheld and headset AR use the same XRSessionMode?](https://github.com/immersive-web/webxr-ar-module/issues/29) [requested by Manishearth](https://github.com/immersive-web/webxr-ar-module/issues/29#issuecomment-540124329)
> We should discuss this alongside #9 and #28 as a general discussion about modes

* [webxr-input-profiles#79 Do fallback profiles need to contain only subset of componenents?](https://github.com/immersive-web/webxr-input-profiles/issues/79) [requested by NellWaliczek](https://github.com/immersive-web/webxr-input-profiles/issues/79#issuecomment-540135141)
> Filed #100 to specifically address the Oculus Touch profile.
>
> To gather opinions on what the general guidelines ought to be

* [webxr-input-profiles#82 UA reserved buttons](https://github.com/immersive-web/webxr-input-profiles/issues/82) [requested by NellWaliczek](https://github.com/immersive-web/webxr-input-profiles/issues/82#issuecomment-540136280)
> I'll take a poke at the right schema changes to support tracking this in the registry.  In the meanwhile...
>
> To learn which buttons should be documented as reserved for each profile

### Immersive Web Working Group Teleconference - 2019-10-29

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, October 29, 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, October 29, 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, 29 October, 19:00 GMT
<tr><td> Paris (France) <td> Tuesday, 29 October, 20:00 CET
<tr><td> Tokyo (Japan) <td> Wednesday, 30 October, 04:00 GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, 29 October, 19:00 UTC
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

- [webxr#225 Behavior of window.requestAnimationFrame and window.requestIdleCallback when presenting](https://github.com/immersive-web/webxr/issues/225)
- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr#679 Consider removing XRWebGLLayer's `context` attribute](https://github.com/immersive-web/webxr/issues/679)
- [webxr#776 Remove unnecessary or redundant information from "Security, Privacy, and Comfort Considerations" ](https://github.com/immersive-web/webxr/issues/776)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69)
- [webxr-gamepads-module#16 Add link to the registry](https://github.com/immersive-web/webxr-gamepads-module/issues/16)
- [webxr#854 Result of calling checkFramebufferStatus on an opaque framebuffer](https://github.com/immersive-web/webxr/issues/854)
- [webxr#856 Do opaque framebuffers have a reference to their XR session?](https://github.com/immersive-web/webxr/issues/856)
- [webxr#860 What is a "valid feature descriptor"](https://github.com/immersive-web/webxr/issues/860)


        
