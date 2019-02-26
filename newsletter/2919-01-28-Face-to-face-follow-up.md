# January 2019 F2F Follow Up

The aims of this are to summarise some of the resolutions from the face to face in January in California. Firstly I would like to thank Samsung Research America for hosting the event. 

This was large put together from the minutes: 
[https://www.w3.org/2019/01/29-immersive-web-minutes.html](https://www.w3.org/2019/01/29-immersive-web-minutes.html)

[https://www.w3.org/2019/01/30-immersive-web-minutes.html](https://www.w3.org/2019/01/30-immersive-web-minutes.html)

## Input and Controllers [#336](https://github.com/immersive-web/webxr/issues/336), [#392](https://github.com/immersive-web/webxr/isues/392) & Pull [#462](https://github.com/immersive-web/webxr/pull/462)

There was a discussion about building a custom interfaces for accessing the XR controller. A gamepad-based solution (as described in #499) was also proposed and was overwhelmingly preferred.

Nell is putting together a [repository](https://github.com/immersive-web/xr-gamepad-mappings) of Schemas which can be maintained as an open source repo for mapping from the gamepad API to controllers.

## originOffset behaviour [#477](https://github.com/immersive-web/webxr/issues/477)

[View the issue](https://github.com/immersive-web/webxr/issues/477#issuecomment-456565794) for more detail and wonderful handdrawn diagrams!

**Interpretation A** thinks of the `originOffset` as applying to the *tracking* origin.
**Interpretation B** thinks of the `originOffset` as applying to the *virtual scene's* origin.

Either can be wholly mathematically consistent, and either can be made clear by the spec text, I'm just curious which approach the WG as a whole finds to be the most intuitive.

After a vote at the face to face **Interpretation B** seemed to be more the popular and we will work with in the future.

## Hit Testing and Anchors ([#491](https://github.com/immersive-web/webxr/pull/491), [#492](https://github.com/immersive-web/webxr/pull/492), [#493](https://github.com/immersive-web/webxr/pull/493))

The proposed changes are the introduction of the first real AR parts of the WebXR spec. They were met with overwhelming approval after the explanations. I have included the introduction from the [hit testing explainer](https://github.com/immersive-web/webxr/blob/master/hit-testing-explainer.md) which I recommend reading: 

"Hit testing" (aka "raycasting") is the process of finding intersections between 3D geometry and a ray, comprised of an origin and direction. Conceptually, hit testing can be done against virtual 3D geometry or real-world 3D geometry. As WebXR does not have any knowledge of the developer's 3D scene graph, it does not provide APIs for virtual hit testing. It does, however, have information about the real-world and provides a method for developers to hit test against it. Most commonly in WebXR, developers will hit test using XRInputSources or the XRSession.viewerSpace to track where a cursor should be drawn on hand-held devices, or even to bounce a virtual object off real-world geometry. In WebXR, 'inline' and 'immersive-vr' sessions are limited to performing virtual hit tests, while 'immersive-ar' sessions can perform both virtual and real-world hit tests.

[Continue reading the hit testing explainer](https://github.com/immersive-web/webxr/blob/master/hit-testing-explainer.md)

## FoV / ViewMatrix ([#461](https://github.com/immersive-web/webxr/issues/461)/[#447](https://github.com/immersive-web/webxr/issues/447)) Expose combined frustrum ([#203](https://github.com/immersive-web/webxr/issues/203)) Default FoV for Magic Window ([#272](https://github.com/immersive-web/webxr/issues/272))

The next section tackled issues relating to the field of view.

## Intersection of Request Animation Frame and Request Idle Callback

- Should we provide projection matrices or break them down for the user?

No clear conclusion. Further discussion required.

- What should the default field of view for magic window mode be?

There isn't really a too bad answer settled on 90degrees vertical (PR [#519](https://github.com/immersive-web/webxr/pull/519))

## Handling Tracking Loss ([#243](https://github.com/immersive-web/webxr/issues/243))

This began with a summary of Alex Turner's research into how different platforms handle losing position tracking: 

[Handling tracking loss · Issue #243 · immersive-web/webxr](https://github.com/immersive-web/webxr/issues/243#issuecomment-454282109)

There was discussion around sensible defaults a PR will be put together soon to put these into the spec.

## Handling Request Animation Frames for content of different framerates being displayed on displays of different framerates

It's really worth [reading the minutes](https://www.w3.org/2019/01/30-immersive-web-minutes.html#item04) for this topic. Essentially some video content will be slower than the headset framerate:

- Video 24/50/60Hz
- DOM content 60 Hz

Which could be displayed on multiple devices at the same time:

- Headsets 90+ Hz
- Monitors/TV 60Hz

Previously browsers largely ignored this and set the assumed it was always 60hz on browsers which could support it even on screens which run at higher frame rates.

No resolutions were proposed during the session but it's an interesting issue to think about.

## Quadlayer - DOM content in XR

Nell gives a great summary of this issue which you can [read in the minutes](https://www.w3.org/2019/01/30-immersive-web-minutes.html#item05)

The idea that you can create 2d uis in world space in html/css is one of the things that we hear frequently -- back at tpac we spent a bunch of time talking about the problem space. The traditional ways people use 2d APIs don't work if there's no way to draw them to the screen.

This is solvable in the context of XR if the actual composition is done by the UA and not the user, this is the concept of a quad layer.

The main benefit of quadlayer is that putting text content on a texture looks really blurry but a seperate layer can be able to do reprojection for the final pose without any per-pixel warping.

## Long lived XR Apps (proposals/[#43](https://github.com/immersive-web/proposals/issues/43))

This was a discussion about the possibilities of running simultaneous XR apps which can hang around for a long time even in other experiences outside of the browser. For example a semi-permanent information widget positioned in a fixed place in your house in AR.

Initial discussion here for a solution based on WebExtensions: [https://github.com/immersive-web/proposals/issues/43](https://github.com/immersive-web/proposals/issues/43)

Analysis on some of the threat vectors of XR: 

[immersive-web/privacy-and-security](https://github.com/immersive-web/privacy-and-security/blob/master/EXPLAINER.md)

## Mirror views - Display WebXR on other sources

Discussion on how important it is to get a video output suitable for flat displays from a WebXR scene?
Many uses were raised:

- Debugging
- Streaming
- Local Audience
- Asymmetrical Experiences

## Expose a hidden area mesh or a hidden area depth write function ([#463](https://github.com/immersive-web/webxr/issues/463))

A simple optimization that VR native applications are already taking advantage of is to inhibit fragment shading of regions of the display panels that, after warping and optics, are not visible to the user.

OpenVR exposes such information as a mesh:

[https://github.com/ValveSoftware/openvr/wiki/IVRSystem::GetHiddenAreaMesh](https://github.com/ValveSoftware/openvr/wiki/IVRSystem::GetHiddenAreaMesh)

Essentially, such a mesh is rendered before the rest of the scene geometry using either depth buffer or stencil buffer writes to inhibit fragment processing of those pixels in subsequent render passes.

This can provide significant performance improvements without relying on any special rendering API functions. This is also much easier to integrate into rendering engines relative to other optimizations (eg, multiview).

Should probably just be fetched every frame
