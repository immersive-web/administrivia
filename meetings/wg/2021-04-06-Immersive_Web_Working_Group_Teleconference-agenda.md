### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2021-04-06-Immersive_Web_Working_Group_Teleconference-agenda.md).
[Minutes](https://www.w3.org/2021/04/06-immersive-web-minutes.html) are available through scribe.

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [administrivia#154 Home for Raw Camera Access proposal / repository](https://github.com/immersive-web/administrivia/issues/154) [requested by bialpio](https://github.com/immersive-web/administrivia/issues/154#issuecomment-806276186)
> This makes sense - we have been receiving requests for raw camera access API and were postponing working on it mostly due to privacy concerns, but the other side of the argument is that raw camera access allows for more rapid prototyping of solutions while UA vendors work on standardizing privacy-preserving APIs. This was also something that was mentioned during yesterday's call in the context of marker tracking API - I believe 8th Wall would be interested in experimenting with JS-powered marker tracking from within WebXR. There are also use cases that are only possible with raw camera access (and there may be more use cases that we don't even know we should be solving). I think Computer Vision is where those discussions & API incubations were supposed to happen so it'd seem to me that there was already a need for such features - creating a new repository would only help with the organizational aspect of the work.
>
>For now I should be able to proceed in my private repository, but I'm mostly worried that folks will be hesitant to participate due to IP concerns. @-ing people who may have some opinion on this as well: @klausw, @nbutko, @thetuvix.
>
> In case we still do not have a clear way forward by the time of the next meeting.

* [webxr#1178 Use session's requested features instead of session device's enabled features to check if a reference space is supported ](https://github.com/immersive-web/webxr/issues/1178) [requested by Manishearth](https://github.com/immersive-web/webxr/issues/1178#issuecomment-805161134)
> So basically the existing design falls out of the following constraints:
>
> - We want people to be able to request permissions _before_ a session starts to time prompts
> - We want people to be able to request permissions _during_ a session so they need not overwhelm the user with prompts for features that may not be needed unless the user performs certain actions (like clicking an in-ui "enable experimental hand tracking" button)
> - We wanted to use existing APIs as much as possible instead of inventing our own permissions system
>
>The second one is what's biting us in particular here, we want the following to work:
>
>```js
>let sess = await navigator.xr.requestSession("immersive-ar", { requiredFeatures: ["local-floor"]});
>// ...
>
>navigator.permissions.query({name: "xr", mode: "immersive-ar", requiredFeatures: ["hand-tracking"]});
>
>sess.inputSources[0].hand.doSomething();
>```
>
>
>There are basically a couple paths forward for us here:
>
>## Keep it as is
>
>The status quo is _fine_, but it does have the weird pitfall that consecutive sessions (or cached permissions) may lead to code working in some cases but not in others. It's a good way to induce "works on my machine" if the permission caching for your setup leads to code just working, but other people have sessions get rejected.
>
>There can also be perf implications on implementations that do not spin up system resources when the relevant features are not yet enabled; e.g. ideally sessions without hand-tracking do not need to set up hand tracking until needed.
>
>## Add a mid-session feature request API
>
>We can add a `requestAdditionalFeatures({required:, optional:})` API. This is unfortunate, we built the permissions API stuff to avoid doing this. But it's probably a minor API, and the permissions API is still useful for controlling when permissions are _prompted_ vs when they are used.
>
>## Add an optional `session` parameter to `XRPermissionDescriptor`
>
>We can continue to use the permissions API, but add a way to "tag" permissions onto existing sessions by giving it a nullable `session` parameter. This makes it possible for the permissions API to still be used pre-session to control prompt times, but will still be useful during the session to enable new features.
>
>## Add an `optionalFeaturesIMayAskForLaterButDontPromptForThemYet` parameter to `requestSession()`
>
>Lets a session declare all features it _may_ rely on. Imperfect, but works. Likely to be confusing even if we can come up with a better name for it.
>
> to discuss this next meeting

### Immersive Web Working Group Teleconference - 2021-04-06

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, April 6, 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, April 6, 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday, April 6, 8:00 PM GMT+1
<tr><td> Paris (France) <td> Tuesday, April 6, 9:00 PM GMT+2
<tr><td> Tokyo (Japan) <td> Wednesday, April 7, 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, April 6, 7:00 PM UTC
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
- [administrivia#147 Platform/Framework Feedback](https://github.com/immersive-web/administrivia/issues/147)


              
