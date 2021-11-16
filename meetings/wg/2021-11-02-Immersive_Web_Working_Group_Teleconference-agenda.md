### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2021-11-02-Immersive_Web_Working_Group_Teleconference-agenda.md). [Minutes](https://www.w3.org/2021/11/02-immersive-web-minutes.html) are available through scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [layers#135 Depth testing across layers](https://github.com/immersive-web/layers/issues/135) [requested by cabanier](https://github.com/immersive-web/layers/issues/135#issuecomment-950503788)
> While designing this API, I came up with 2 choices:
>1.  an option that is passed at session creation time. The session will then always honor depth and the experience is required to pass depth
>1.  an option that is passed at layer creation time. This would need a new attribute on the binding to indicate that depth sorting is supported
>
>Option 1 seems the move obvious but 2 is more flexible although it could be confusing since you could mix layers that sort depth with non-sorting ones.
>
> how to expose depth sorting


* [layers#265 A feature that toggle stereo on runtime.](https://github.com/immersive-web/layers/issues/265) [requested by cabanier](https://github.com/immersive-web/layers/issues/265#issuecomment-933597965)
> ok. That is indeed a problem that we could fix in the layers spec.
>I'll put this on the agenda and we can discuss it in the next WebXR meeting.
>
> Can we put stereo media layers into mono?

* [webxr#1203 Provide statistics to help guide performance](https://github.com/immersive-web/webxr/issues/1203) - cabanier
> One of the hardest parts of WebXR is how to tune for good performance.
 >It is hard for authors to gauge how much processing power is available to them so they end up optimizing their code for the device they have on hand.

* [administrivia#171 TPAC 2021 action items summary](https://github.com/immersive-web/administrivia/issues/171) - Yonet
> [description]

### Immersive Web Working Group Teleconference - 2021-11-02

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, November 2, 11:00 AM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, November 2, 2:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, November 2, 6:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, November 2, 7:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, November 3, 3:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, November 2, 6:00 PM UTC
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
- [administrivia#147 Platform/Framework Feedback](https://github.com/immersive-web/administrivia/issues/147)
- [webxr#1219 Finalise accessibility-considerations-explainer.md](https://github.com/immersive-web/webxr/issues/1219) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)


              
