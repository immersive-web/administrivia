### Call Agenda

This is obviously a lot I don't expect to g et through it all, let's just do what we can.

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2022-11-22-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [proposals#30 Virtual Keyboard API](https://github.com/immersive-web/proposals/issues/30) [requested by cabanier](https://github.com/immersive-web/proposals/issues/30#issuecomment-1304324677)
> We are making progress on enabling the native keyboard during an immersive session. As  mentioned before, it will be triggered by focusing an element just like on a 2D page.
>I'm wondering if we need a flag to indicate that the UA supports this. Most implementations won't have this feature and there would be no way for an author to know if a keyboard was shown. (Listening to blur events could work but feels hacky)
>
> should WebXR have a flag and normative text for keyboard input?

* [real-world-geometry#36 Add support for semantic labels](https://github.com/immersive-web/real-world-geometry/pull/36) [requested by cabanier](https://github.com/immersive-web/real-world-geometry/pull/36#issuecomment-1312775872)
> @bialpio I reworked the PR a bit and put in a list of predefined labels.
>This is the list of labels as per OpenXR. 
>
> discuss semantic labels

* [proposals#78 Allow the sites to request AR sessions using front-facing camera](https://github.com/immersive-web/proposals/issues/78) [requested by Yonet](https://github.com/immersive-web/proposals/issues/78#issuecomment-1299103859)
> vote for repo owner for the repo: https://github.com/immersive-web/front-facing-camera

* [anchors#79 Allow a limit of the number of active and persistent anchors](https://github.com/immersive-web/anchors/issues/79) - cabanier
> Currently the spec does not mention any limit to the number of anchors a site can create.
 >On Quest, there is a significant additional load if a lot of anchors are active so we like to limit how many can be in a scene at a time.

### Immersive Web Working Group Teleconference - 2022-11-22

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, November 22 at 11:00 AM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, November 22 at 2:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday 22 November at 19:00 GMT
<tr><td> Paris (France) <td> Tuesday 22 November at 20:00 CET
<tr><td> Tokyo (Japan) <td> Wednesday 23 November at 04:00 GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday 22 November at 19:00 UTC
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


              
