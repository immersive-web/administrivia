### Call Agenda

This agenda can be viewed and updated on [Github](https://github.com/immersive-web/administrivia/blob/main/meetings/wg/2024-03-05-Immersive_Web_Working_Group_Teleconference-agenda.md).

If you would like to add an item to the agenda or volunteer to scribe please open a pull request against this agenda.

* [webxr-hand-input#123 Reapply "Allow generic-hand"](https://github.com/immersive-web/webxr-hand-input/pull/123) [requested by AdaRoseCannon](https://github.com/immersive-web/webxr-hand-input/pull/123#issuecomment-1936728918)
> FYI

* [administrivia#205 Tag F2F issues](https://github.com/immersive-web/administrivia/issues/205) - Yonet
> Please tag the issues you would like to discuss on F2F meeting.
 >Feel free to create new issues and don't forget to rsvp. 

* [webxr#988 Are 8-bit outputs sRGB encoded?](https://github.com/immersive-web/webxr/issues/988) [requested by cabanier](https://github.com/immersive-web/webxr/issues/988#issuecomment-1933017426)
> > > The browser creates linear output values. The compositor is supposed to treat it like sRGB and not do any conversion.
>> 
>> That sounds wrong, and I don't know if it's just a terminology mismatch.
>
>That may be "wrong" but that is how browsers work.
>
>> I think we're in agreement that the web app writes its output into the opaque framebuffer using sRGB encoding, same as if it was targeting a 2D display. The browser needs to send this data to the system compositor, and basically has two choices:
>
>No, we are not in agreement. The framebuffer is in linear RGB same as WebGL. The swapchain is in sRGB.
>
>> When you say "the browser creates linear output values", do you mean it produces numbers that the compositor can use as-is? That's correct assuming that the compositor is expecting sRGB.
>
>No, the browser creates linear values. Technically this is *wrong* but that is how they're exposed to the page.
>Browsers are not alone in making this error; there were enough games that made the same assumption that Oculus' [old API](https://github.com/MortimerGoro/ovr-mobile-sys/blob/master/VrApi/Include/VrApi_Types.h#L543) had a flag to work around this.
>
>> > No, that would be incorrect. The default of the layers API should match the default WebGL canvas behavior which is rgb; regular WebXR has the same default.
>> 
>> I don't get this part. Regular WebGL canvas is interpreted as sRGB, that's why for example the recommended Three.JS rendering setup puts a `gl_FragColor = linearToSRGB(gl_FragColor)` equivalent at the end of shaders. 
>
>It only does that conditionally and looking at the code, only for sRGB render targets.
>
>> I think it would be wrong if a Layers extension XRProjectionLayer with colorFormat=RGBA would treat the data as sRGB and for example pass it on to the compositor without conversion to a GL_SRGB8_ALPHA8 OpenXR swapchain buffer. While that would match the default WebXR rendering, I think it doesn't make sense - what would colorFormat=SRGB8 do differently then? To the best of my knowledge, the default WebXR (and 2D canvas) rendering is equivalent to SRGB8 and would match being used with an OpenXR SRGB8 swapchain.
>
>No, changing the default to sRGB would break each WebXR experience because now drawing with RGB will get gamma correction applied.
>I'm happy to discuss this further during a call.
>
> discuss linear vs sRGB

* [webxr#1358 Detecting if an `XRInputSource` is an auxiliary or a primary input source](https://github.com/immersive-web/webxr/issues/1358) [requested by cabanier](https://github.com/immersive-web/webxr/issues/1358#issuecomment-1938928307)
> I worry that adding inputsources is confusing for authors and might break certain experiences.
>
>Since every site needs to be updated anyway, maybe we can introduce a new attribute (`secondaryInputSources`?) that contains all the input sources that don't generate input events.
>
> should we move secondary input sources to their own attribute?

* [webxr#1360 Indicate "preferred" immersive mode](https://github.com/immersive-web/webxr/issues/1360) - cabanier
> On most HMDs, the user can choose either a VR environment or passthrough.
 >OpenXR offers an API to convey a preferred immersive mode; basically it returns if the user is in AR or VR. An application could use this to continue in this mode.

### Immersive Web Working Group Teleconference - 2024-03-05

<table>
<tr><td> San Francisco (U.S.A. - California) <td> Tuesday, March 5 at 11:00 AM PST
<tr><td> Boston (U.S.A. - Massachusetts) <td> Tuesday, March 5 at 2:00 PM EST
<tr><td> London (United Kingdom - England) <td> Tuesday, March 5 at 7:00 PM GMT
<tr><td> Paris (France) <td> Tuesday, March 5 at 8:00 PM GMT+1
<tr><td> Tokyo (Japan) <td> Wednesday, March 6 at 4:00 AM GMT+9
<tr><td> Corresponding UTC (GMT) <td> Tuesday, March 5 at 7:00 PM UTC
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


              
