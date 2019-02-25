# January 2019 F2F Follow Up

The aims of this are to summarise some of the resolutions from the face to face in January in California. Firstly I would like to thank Samsung Research America for hosting the event. 

This was large put together from the minutes: 
[https://www.w3.org/2019/01/29-immersive-web-minutes.html](https://www.w3.org/2019/01/29-immersive-web-minutes.html)

[https://www.w3.org/2019/01/30-immersive-web-minutes.html](https://www.w3.org/2019/01/30-immersive-web-minutes.html)

## Input and Controllers [#336](https://github.com/immersive-web/webxr/issues/336), [#392](https://github.com/immersive-web/webxr/isues/392) & Pull [#462](https://github.com/immersive-web/webxr/pull/462)

There was a discussion about building a custom interfaces for accessing the XR controller. A gamepad-based solution (as described in #499) was also proposed and was overwhelmingly preferred.

Nell is putting together a [repository](https://github.com/immersive-web/xr-gamepad-mappings) of Schemas which can be maintained as an open source repo for mapping from the gamepad API to controllers.

## originOffset behaviour [#477](https://github.com/immersive-web/webxr/issues/477)

This issue highlights the fact that there's actually two valid ways to think about this, and we need to:

1. Make sure everyone agrees on which interpretation is desired.
2. State which way the spec intends much more clearly.

And in order sort that out I'm going to subject you all to my scribbles. 😁

![Diagram of scene with zero offset](https://user-images.githubusercontent.com/805273/51562472-bed5d080-1e3e-11e9-8d19-93816a397c99.png)

This is, I hope we can all agree, the default state of things. No `originOffset` has been applied, so the virtual scene's origin is aligned with the tracking system's origin, which in this case considers the center of the room at the floor to be `(0,0,0)`. Very typical `bounded` scenario.

My assumption when writing the `originOffset` text, and subsequently the `identity` reference space text, was that if you set it's `position` to, say, `(1, 0, -3)` you'd get an effect like this, which we'll call **Interpretation A**:

![Offset caused user to appear moved forward and right](https://user-images.githubusercontent.com/805273/51565661-6c4ce200-1e47-11e9-859e-3bad28df1ca9.png)

Specifically, in this case the `originOffset` is interpreted to be a value that is added to the native tracking space values, such that setting the `originOffset` effectively makes that point in the virtual scene align with the tracking origin of your physical space. This seemed intuitive to me, since developers using it as a teleport mechanism would say, for instance "I want the player to be warped to (x, y, z) in the virtual scene" and so `(x, y, z)` is what you would set the `originOffset.position` to.

Alex's interpretation (or at least my interpretation of his interpretation) is the inverse, which is also a valid reading of it. In this world view the same `position` of `(1, 0, -3)` would yield something like this, which we'll call **Interpretation B**:

![Offset caused user to appear moved  backward and left](https://user-images.githubusercontent.com/805273/51562988-04df6400-1e40-11e9-92e2-4017cfb5e1d7.png)

In this scenario the origin of the virtual space is offset from the origin of the tracking space by the `originOffset`, which has the practical effect of "moving" the user through the scene by the inverse amount. This felt backwards to me because of it, but when looking at it from a perspective that views the user's environment as immutable (because, as far as our software is concerned, it is) this approach makes a lot of sense.

The TL;DR of the above is:

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

Nell: 

The traditional ways people use 2d APIs don't work if there's no way to draw them to the screen.
The idea that you can create 2d uis in world space in html/css is one of the things that we hear frequently -- back at tpac we spent a bunch of time talking about the problem space.

Recapping: One of the big things that we were asking was: what does it mean to meet both of our requirements the first most obvious thing we'd need to support is interactive content e.g. having a button -- what that means in the context of XR with aiming, etc is somethinng we need to answer a related question: what do we do about cross-origin content? there's a big security rabbit hole here this is why we don't have APIs like dom-to-texture. So aside from the issues with respect to input there are security concerns about letting someone know about what's in the DOM.

Interestingly this is solvable in the context of XR since the actual composition is done by the UA and not the user, this is the concept of a quad layer, the ability to have a "quad" in space which you can back with something from the dom, which can be then rendered and composited by the UA. The webpage never sees this this also opens the door for refresh rate stuff we can play around with because they're independent from each other there are things we need to discuss what that structure looks like -- is it just a subelement of the dom?

It's a bit trickier with multidisplay situations too we were also playing with having a different document root instead it's something like a different DOM layer, or an iframe or something key thing: when you talk about hosting cross-origin content in a quadlayer in XR, you get gnarly stuff about *input* in that origin to render things you need pose data which the parent document can control so for cross-origin content by its very nature we can't let input events reach it, even when it's in the same origin with embedded cross-origin info there's no secure way to do this without letting the parent document eavesdrop on what's going on.

The plumbing code for input in terms of UAs is something we need to look into that's roughly high level, we also explored one big problem: how can we create a pit of success for people who create experiences thinking about handheld which we want to work on headworn devices.

If we put a quadlayer in xr that's a world space thing and that can work in handheld AR but it can break down too what would be an easy way to help folks who wish to optimize for handheld we need to take this first round of work and turn it into a more concrete proposal

The main benefit of quadlayer is that text on a texture looks really blurry but a seperate layer can be able to do reprojection for the final pose without any per-pixel warping.

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
