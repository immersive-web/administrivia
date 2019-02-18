### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2019-02-19-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [Changed XRHandedness enum to use 'none' instead of ''](https://github.com/immersive-web/webxr/pull/526) - Fixed #515.
* [State of immersive mode navigation for the WebXR Draft](https://github.com/immersive-web/webxr/issues/517) - With the [Navigation Design Doc](https://github.com/immersive-web/webxr/blob/master/designdocs/navigation.md) in mind, what is happening with regards to immersive-to-immersive navigation? 
* [Gamepad-based button/axis state](https://github.com/immersive-web/webxr/pull/499) - This is a proposal for how we might use the existing Gamepad API to expose controller button and axis state.
* [Add renderId to XRInputSource](https://github.com/immersive-web/webxr/pull/479) - toji - Splitting this component out from #462, since that one is generating a lot of conversation and it'll be good to separate out the concerns. (#462 still needs to be rebased properly and have this section removed.)
* [Custom interface for controller button/axis state (Variant A)](https://github.com/immersive-web/webxr/pull/462) - toji - This is a proposal to fix the long-running #392, as well as address #336. (And honestly those two could be separated if one part or the other of this proves controversial, but for now I think it's useful to see them together.)
* [Remove ProjectionMatrix in favor of FOV values?](https://github.com/immersive-web/webxr/issues/461) - This issue was raised in the discussion of #447.  The projection matrices were originally added instead of view-specific FOVs due to the behavior of certain hardware.  Now that this is no longer a requirement for those devices, it's been brought up that it might be better to return to representing the data as FOV values.  I'm not taking a stand one way or the other, but I didn't want this potential change to fall through the cracks.
* [Should we just remove `viewMatrix` and rename `transform` to `viewTransform`?](https://github.com/immersive-web/webxr/issues/447) - toji - In looking through #440, I wonder if any non-trivial engine with an actual scene graph will ever make use of `viewMatrix`, or if `transform` is _actually_ all they will evaluate each frame for all purposes, including positioning the camera in the scene relative to the app's chosen reference space origin.
* [Added session feature handling to the explainer.](https://github.com/immersive-web/webxr/pull/433) - Addresses #423 and #424.

### Immersive Web Working Group Teleconference - 2019-02-19

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, 19 February, 10:00 GMT-8
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, 19 February, 13:00 GMT-5
<tr><td> London (United Kingdom - England) <td> Tuesday, 19 February, 18:00 GMT
<tr><td> Paris (France) <td> Tuesday, 19 February, 19:00 CET
<tr><td> Tokyo (Japan) <td> Wednesday, 20 February, 03:00 GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, 19 February, 18:00 UTC
</table>

### Logistics

Chair: Ada Rose Cannon

Scribe:

IRC: [irc.w3.org](http://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/master/IRC.md)

Call Details can be found here: https://lists.w3.org/Archives/Member/internal-immersive-web/2019Feb/0002.html

If you are unable to login to view the call details they will be in the IRC topic.

To join the audio conference only: 

To receive a call back, provide your phone number when you join the meeting, or call the number below and enter the access code.
US Toll Number: +1-617-324-0000  
Access code:648 697 067  
Mobile Auto Dial:+1-617-324-0000,,,648697067#

For assistance go to https://mit.webex.com/mit/mc  and on the left navigation bar, click "Support".
          
