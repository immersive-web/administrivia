### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2020-11-17-Immersive_Web_Working_Group_Teleconference-agenda.md).
[Minutes](https://www.w3.org/2020/11/17-immersive-web-minutes.html) are available through irc scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [hit-test#96 Best practices for headset and handset AR](https://github.com/immersive-web/hit-test/issues/96) [requested by Manishearth](https://github.com/immersive-web/hit-test/issues/96#issuecomment-726945562)
> Currently the spec mandates that all transient sources have `targetRayMode = "screen"`, but not vice versa (even though that is true in practice). It's worth considering making that always true, but we can also add a `transient` bool.
>
>My understanding is that the API is intended to be used by registering against all normal input sources and also adding a transient source listener. Perhaps this can be  added to the explainer.
>
> to discuss how authors should be writing this and to see if we need spec or explainer changes to support that

* [layers#228 Should we limit the list of supported texture formats?](https://github.com/immersive-web/layers/issues/228) - cabanier
> Implementing the list of supported formats is showing a large amount of texture color and depth formats.
 >Is it really necessary to surface them all and allow them in the API?

### Immersive Web Working Group Teleconference - 2020-11-17

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, November 17, 12:00 PM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, November 17, 3:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday, November 17, 8:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, November 17, 9:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, November 18, 5:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, November 17, 8:00 PM UTC
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
- [webxr-gamepads-module#16 Add link to the registry](https://github.com/immersive-web/webxr-gamepads-module/issues/16) [<small>[Pre-CR]</small>](https://api.github.com/repos/immersive-web/webxr-gamepads-module/milestones/1)
- [webxr#953 Typescript definitions](https://github.com/immersive-web/webxr/issues/953) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#1115 Explicitly spec when inline animation frame loops are suspended](https://github.com/immersive-web/webxr/issues/1115) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr-samples#80 Example 17: "Hands Test" is missing](https://github.com/immersive-web/webxr-samples/issues/80)


              
