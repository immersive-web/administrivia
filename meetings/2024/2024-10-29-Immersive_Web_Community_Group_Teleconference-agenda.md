### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/2024/2024-10-29-Immersive_Web_Community_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [model-element#78 Progress on the spec](https://github.com/immersive-web/model-element/issues/78) [requested by zachernuk](https://github.com/immersive-web/model-element/issues/78#issuecomment-2440609945)
> I feel like we've made a lot of headway in the last 6 months - It seems like the ~45 minutes per month that we effectively end up using to talk about this feature is insufficient to resolve the details necessary to get a properly-specified feature. 
>
>I'd love to establish a more focused meeting - open to all - with a more regular cadence, so that people aren't coming back to the issues with four weeks of time to make up for between discussion. AFAIK, the initial WebXR spec was worked out with a more frequent schedule as well, so there is a precedent.

* [model-element#71 Supply an Image-based Light file](https://github.com/immersive-web/model-element/issues/71) [requested by zachernuk](https://github.com/immersive-web/model-element/issues/71#issuecomment-2440667302)
> Somehow I failed to imagine also using CSS to specify this. I quite like the idea, particularly because it means that it can be changed around with CSS classes that might indicate color themes etc, and _possibly_ to let things like `transition-duration` impact the cross-fading between different environment maps.
>
>One question would be if / how that alters an expected event model for the loadedness of the asset. Is there a right way to manage that in 2024 (and beyond?)

* [model-element#72 Specify the view on model contents](https://github.com/immersive-web/model-element/issues/72) [requested by zachernuk](https://github.com/immersive-web/model-element/issues/72#issuecomment-2440636997)
> Do we want to codify that this happens both _with_ `DOMMatrix` and _in_ CSS? It's not essential to do both, but it does mean things like `transition-duration` and CSS Animations have a way to being used.

* [model-element#75 `ready` and `complete` events/Promises for responding to source file availability etc](https://github.com/immersive-web/model-element/issues/75) [requested by zachernuk](https://github.com/immersive-web/model-element/issues/75#issuecomment-2400765096)
> Now that we've got multiple folks planning an implementation, we should check back in on this! 
>Tentatively, I think we need some signaling from the element about four major moments:
>
>* Model is parsed and renderable,
>* Model has hit some failure preventing it from becoming renderable,
>* Environmentmap is parsed and renderable,
>* Environmentmap has failed to become renderable.
>
>These could be promises with an await/catch, or events (or both). 
>
>If we wanted to pursue a CSS-based mechanism for specifying an environment map, would that change the recommended presentation of the environment map states?

* [model-element#99 Presentation as a first-class DOM element](https://github.com/immersive-web/model-element/issues/99) - zachernuk
> While most of the issues about `HTMLModelElement` relate _what_ it's displaying (i.e. 3D rendered content, animated and then lit by some lighting environment), it's also important to consider how it's presented in the page, alongside other DOM elements. What are requirements that need to apply?

### Immersive Web Community Group Teleconference - 2024-10-29

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, October 29 at 12:00 PM PDT
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, October 29 at 3:00 PM EDT
<tr><td> London (United Kingdom - England) <td> Tuesday 29 October at 19:00 GMT
<tr><td> Paris (France) <td> Tuesday 29 October at 20:00 CET
<tr><td> Tokyo (Japan) <td> Wednesday 30 October at 04:00 GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday 29 October at 19:00 UTC
</table>

### Logistics

Chair: Ada Rose Cannon

Scribe:

IRC: [irc.w3.org](https://irc.w3.org/):6667 #immersive-web [Instructions](https://github.com/immersive-web/administrivia/blob/main/IRC.md)

Call Details can be found in the Immersive Web Event Calendars: [WG](https://www.w3.org/groups/wg/immersive-web/calendar/)/[CG](https://www.w3.org/groups/cg/immersive-web/calendar/)

You subscribe to these calendars with your calendar application of choice for more convenient access to the call details. See details at Export options section in [WG](https://www.w3.org/groups/wg/immersive-web/calendar/#export)/[CG](https://www.w3.org/groups/cg/immersive-web/calendar/#export).

If you are unable to login to view the call details please ask on the IRC before the call.

### Help Wanted

Here are some issues which are good issues to get involved in, if you have taken responsibility for one leave a comment in the issue:

- [webvr-polyfill-dpdb#34 Create a helper script/web page for generating values for a new device](https://github.com/immersive-web/webvr-polyfill-dpdb/issues/34)
- [webxr-input-profiles#69 Resizing the window changes the model viewer's aspect ratio](https://github.com/immersive-web/webxr-input-profiles/issues/69) [<small>[Future]</small>](https://api.github.com/repos/immersive-web/webxr-input-profiles/milestones/4)
- [webxr#953 Typescript definitions](https://github.com/immersive-web/webxr/issues/953) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [webxr#1115 Explicitly spec when inline animation frame loops are suspended](https://github.com/immersive-web/webxr/issues/1115) [<small>[Pre-REC]</small>](https://api.github.com/repos/immersive-web/webxr/milestones/16)
- [proposals#82 Some sort of local shared space](https://github.com/immersive-web/proposals/issues/82)


              
