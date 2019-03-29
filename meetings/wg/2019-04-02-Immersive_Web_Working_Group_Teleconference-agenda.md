### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2019-04-02-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [Update spec and explainer to clarify pose and transform semantics](https://github.com/immersive-web/webxr/pull/569) - This is intended to address issues #477, #565, and #567 which all involve areas where the spec isn't entirely clear about intended behavior.
* [Remove XRSessionCreationOptions](https://github.com/immersive-web/webxr/pull/566) - As described in #542, this switches `requestSession` to a "primary type
* [Tracking loss and tracking recovery](https://github.com/immersive-web/webxr/pull/559) - This addresses the Jan 2019 F2F discussion we had regarding https://github.com/immersive-web/webxr/issues/243#issuecomment-454282109.
* [Format of Gamepad identifiers](https://github.com/immersive-web/webxr/issues/550) - toji - I wanted to separate this discussion out from the rest of the gamepad-as-the-input-solution work, because it's a reasonably complex topic on it's own.
* [Consider primary type plus options bag pattern in request methods](https://github.com/immersive-web/webxr/issues/542) -  `XR.requestSession()` and `XRSession.requestReferenceSpace()` both take a single options parameter. In many/most cases, only a single primary value from the options needs to be specified. It may be better to instead specify that primary value separately followed by an optional options parameter. This may both simplify the current API and allow for more flexibility for future extension.
* [Add verticalFieldOfView to XRRenderState](https://github.com/immersive-web/webxr/pull/519) - Fixes #272.
* [Combine XRStationaryReferenceSpaceSubtype into XRReferenceSpaceType](https://github.com/immersive-web/webxr/issues/514) - https://github.com/immersive-web/webxr/pull/502 merged `subtype` into XRReferenceSpaceOptions, and have `type` and (optional) `subtype` are now in the same dictionary.
* [Remove unnecessary interface members that only reflect what was requested](https://github.com/immersive-web/webxr/issues/513) - There are currently some member attributes in the spec that only reflect what the application requested. I believe this is generally discouraged as doing so increases the API surface without providing capabilities not otherwise available to the application. (It's also easier to add values in the future if necessary than it is to remove them.) The exception is where there is a fixup step or the correct value may not otherwise be obvious to the application.
* [Consider removing utility functions / properties from the spec](https://github.com/immersive-web/webxr/issues/507) - Currently, the spec contains few properties that could be considered "utility / helper" - they don't make the specification more capable, but only reduce the amount of code that app developer needs to write. Depending on our philosophy of what the spec should contain (ex. expose smallest API surface that is needed to enable content creators), we might want to remove such methods and pay attention to not add more of them.

### Immersive Web Working Group Teleconference - 2019-04-02

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, 2 April, 10:00 GMT-7
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, 2 April, 13:00 GMT-4
<tr><td> London (United Kingdom - England) <td> Tuesday, 2 April, 18:00 BST
<tr><td> Paris (France) <td> Tuesday, 2 April, 19:00 CEST
<tr><td> Tokyo (Japan) <td> Wednesday, 3 April, 02:00 GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, 2 April, 17:00 UTC
</table>

### Logistics

Chair: Chris Wilson

Scribe:

IRC: [irc.w3.org](http://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/master/IRC.md)

Call Details can be found on the [Internal Mailing List](https://lists.w3.org/Archives/Member/internal-immersive-web/2019Feb/0002.html)

If you are unable to login to view the call details they will be in the IRC topic.

To join the audio conference only: 

To receive a call back, provide your phone number when you join the meeting, or call the number below and enter the access code.
US Toll Number: +1-617-324-0000  
Access code:648 697 067  
Mobile Auto Dial:+1-617-324-0000,,,648697067#

For assistance go to https://mit.webex.com/mit/mc  and on the left navigation bar, click "Support".
          
