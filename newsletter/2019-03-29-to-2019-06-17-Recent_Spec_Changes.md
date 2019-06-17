## Recent Spec Changes - from 2019-03-29 to 2019-06-17

Edit on [Github](https://github.com/immersive-web/administrivia/blob/master/newsletter/2019-03-29-to-2019-06-17-Recent_Spec_Changes.md).
### [Remove attribs that only reflect requested values](https://github.com/immersive-web/webxr/pull/574)

Merged Fri Apr 19 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7) ![potential breaking change](https://iw-newsletter-generator.glitch.me/svg/?text=potential%20breaking%20change&bgcolor=d32a6b)

Remove attribs that only reflect requested values (#574)

Remove attribs that only echo creation parameters:

 - XRSession.mode;
 - XRWebGLLayer.depth;
 - XRWebGLLayer.stencil;
 - XRWebGLLayer.alpha;
 - XRStationaryReferenceSpace.subtype;



### [Rename reference space types](https://github.com/immersive-web/webxr/pull/640)

Merged Tue May 14 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7) ![potential breaking change](https://iw-newsletter-generator.glitch.me/svg/?text=potential%20breaking%20change&bgcolor=d32a6b)

Rename reference space types (#640)

Renames several reference space types for clarity, as recommended in
issue #633. Intent is to better communicate which reference spaces are
floor-aligned and avoid potential developer confusion that may arise
from use of the term "stationary".

Renamed reference spaces:
 - `eye-level` -> `local`
 - `floor-level` -> `local-floor`
 - `bounded` -> `bounded-floor`



### [Rename supportsSessionMode to supportsSession](https://github.com/immersive-web/webxr/pull/595)

Merged Mon Apr 22 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7) ![potential breaking change](https://iw-newsletter-generator.glitch.me/svg/?text=potential%20breaking%20change&bgcolor=d32a6b)

Rename supportsSessionMode to supportsSession (#595)

Fixes #592. Brings the method name inline with requestSession, which now takes the
same arguments.



### [Change inputSources getter from method to attrib.](https://github.com/immersive-web/webxr/pull/624)

Merged Tue May 14 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Change inputSources getter from method to attrib. (#624)

Changes the `getInputSources()` method on `XRSesssion` to a readonly
attribute `inputSources`. This better reflects the expected behavior
of the returned array being a live object that is updated in-place as
input sources are added and removed.

In order to facilitate that change the `XRInputSourceArray` interface was
also added, since `FrozenArray` doesn't support the live changes that are
required for this attribute.



### [Explicitly spec out native origins](https://github.com/immersive-web/webxr/pull/621)

Merged Tue May 07 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Explicitly spec out native origins (#621)

Adds native origins for input spaces, viewerSpace, identity, and position-disabled spaces. Specifies that the native origin of identity spaces is constant when there is no tracking data.



### [Single-canvas inline, drop XRPresentationContext](https://github.com/immersive-web/webxr/pull/656)

Merged Thu Jun 13 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Single-canvas inline, drop XRPresentationContext (#656)

This change adds a path for using a single WebGL canvas to drive inline
sessions, rather than needing both a WebGL context and an
XRPresentationContext before the inline session can function. With this
change `XRWebGLLayer`s will automatically stop allocating a framebuffer
with inline sessions, which causes WebGL commands to naturally "fall through"
to the underlying default framebuffer.

In addition to the above, this change removes the XRPresentationContext
entirely, and along with it the ability to do desktop mirroring (and
more advanced inline scenarios.) This is to simplify the core API, and
equivalent functionality will be reconsidered in the future because the
functionality that they represent is valuable.



### [Overhaul XRSpace, get(Viewer)Pose definitions](https://github.com/immersive-web/webxr/pull/609)

Merged Sat Apr 27 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Overhaul XRSpace, get(Viewer)Pose definitions (#609)

Formalizes the definitions of origins, transforms, and some of the math
involved. This will hopefully give us a better foundation on top of which
we can better talk about spacial concepts.

**Huge** thank you to @klausw, @Manishearth, and @NellWaliczek
for helping to iterate through this fairly tricky language and land on
something that much more rigorous.



### [Fix multiplication order for transforms](https://github.com/immersive-web/webxr/pull/649)

Merged Thu May 16 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Fix multiplication order for transforms

The multiplication order in the spec needs to match the matrix
semantics we've agreed on, and the usage appeared to be backwards.

Specific justifications following.

getViewerPose: if |offset| is the view offset of an eye view, the expected
semantics would be that it's a pose-like transform where the transform's
position is the eye view's coordinates in XRViewerPose space. The
corresponding matrix is viewerFromEye. XRViewerPose contains the viewer
pose in the base reference space, so its transform's position is the viewer
position in base space coordinates, and the transform is baseFromViewer.

Chaining these transforms works as follows:

```js
offset.matrix = viewerFromEye;
viewerPose.transform.matrix = baseFromViewer;

view.transform.matrix = baseFromEye
                      = baseFromViewer * viewerFromEye
                      = viewerPose.transform.matrix * offset.matrix
```

For originOffset, the logic is similar:

```js
let offsetASpace = baseSpace.getOffsetReferenceSpace(offsetAInBase);
// offsetAInBase.matrix = baseFromA
let offsetBSpace = offsetASpace.getOffsetReferenceSpace(offsetBInA);
// offsetBInA.matrix = AFromB

// equivalent to:
let offsetBSpace = baseSpace.getOffsetReferenceSpace(offsetBInBase);
// offsetBInBase.matrix = baseFromA * AFromB = offsetAInBase.matrix * offsetBInA.matrix
```

Lastly, for XRRay, the convention is to transform points or vectors by
premultiplying the transform matrix from the left, I've rephrased those usages
to make that explicit. The current text was basically saying "multiply
vector by matrix" which would be backwards.



### [Some matrix clarifications](https://github.com/immersive-web/webxr/pull/654)

Merged Fri May 17 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Some matrix clarifications (#654)

Add note clarifying what the matrix describes and a different way to multiply matrices. Also clarifies which direction XRView.transform works in.



### [Consolidate reference space types and interfaces](https://github.com/immersive-web/webxr/pull/587)

Merged Wed May 01 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Consolidate reference space types and interfaces (#587)

Consolidate the various interfaces that extended XRReferenceSpace, with the exception of XRBoundedReferenceSpace which was still necessary to communicate the boundsGeometry. This PR also eliminates the 'stationary' XRReferenceSpaceType in favor of making all of it's subtypes top level types. Which, in turn, eliminates the need for the options dictionary when creating a reference space, so this PR also changes that call to only take the type enum (an options dictionary can be added as a second argument in the future if needed, as described by #542.



### [Describe how the input source list is maintained](https://github.com/immersive-web/webxr/pull/628)

Merged Tue May 14 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Describe how the input source list is maintained (#628)

Defines what should happen as input sources for a session are added,
removed, and changed. Also clarifies the definitions for some of the
related concepts.



### [Explicitly spec out when requestReferenceSpace() can reject queries](https://github.com/immersive-web/webxr/pull/651)

Merged Fri May 17 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Explicitly spec out when requestReferenceSpace() can reject queries (#651)

Provides a more explicit algorithm for determining if a given `XRReferenceSpaceType` is supported for a given `XRSession`. It's anticipated that this criteria will be expanded in the future as we finalize privacy considerations, but for now it's focused on the device capabilities.



### [Simplify available spaces](https://github.com/immersive-web/webxr/pull/626)

Merged Thu May 09 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Simplify available spaces (#626)

Removes the position-disabled reference space from the spec and
explainers. Developers that wish to display the types of content this
reference space supported (primarily 360 media) should instead manually
zero-out the position of the XRView transforms when rendering.

Also consolidates the viewerSpace attribute and the identity reference
space into a single new reference space called viewer. This new
space is functionally equivalent to the previous viewerSpace but
fetched via requestReferenceSpace() with the same guarantee of
availability as identity had previously. All other spaces relate to it
like any other space.



### [Change blur/focus to visibilitychange](https://github.com/immersive-web/webxr/pull/687)

Merged Fri Jun 14 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Change blur/focus to visibilitychange (#687)

Fixes #488
Fixes #468

Changes the `blur` and `focus` events to `visibilitychange`, along with
a `visibilityState` attribute on the `XRSession`. The `visibilityState`
may be `visible`, `visible-blurred`, or `hidden`. This is pretty close to the
`document.visibilityState` attribute and associated event, with the
exception of the `visible-blurred` state.



### [Make origin offset immutable](https://github.com/immersive-web/webxr/pull/612)

Merged Wed May 01 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Make origin offset immutable (#612)

Fixes #580. Changes originOffset to be immutable and establish that the
way that the originOffset changes is by constructing a new reference
space with the base space and an additional offset to apply on top of
it. This should hopefully solve several timing issues related to
changing the originOffset mid-frame.



### [Make boundsGeometry work relative to the effective origin](https://github.com/immersive-web/webxr/pull/613)

Merged Wed May 01 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Make boundsGeometry work relative to the effective origin (#613)



### [Define event order of input sources](https://github.com/immersive-web/webxr/pull/629)

Merged Tue May 14 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Define event order of input sources (#629)

Makes the order of `select`, `selectstart`, and `selectend` events generated by the API explicit, as well as their timing relative to certain non-XR input events in the case of transient input types (mouse, touch, etc.)



### [Clarify when the reset event gets fired](https://github.com/immersive-web/webxr/pull/637)

Merged Tue May 14 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Clarify when the reset event gets fired (#637)

Clarify when the reset event gets fired



### [Updated the explainer with new origin offset mechanics.](https://github.com/immersive-web/webxr/pull/642)

Merged Sat May 25 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Updated the explainer with new origin offset mechanics. (#642)



### [requestSession(): Group steps to run when promise is rejected](https://github.com/immersive-web/webxr/pull/646)

Merged Wed May 15 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

requestSession(): Group steps to run when promise is rejected (#646)

This makes the algorithm a little easier to read.



### [Clarify assumptions for local and local-floor tracking](https://github.com/immersive-web/webxr/pull/648)

Merged Wed May 15 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7)

Clarify assumptions for local and local-floor tracking (#648)



### [Reject outstanding promises on session shut down](https://github.com/immersive-web/webxr/pull/585)

Merged Mon Apr 15 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Reject outstanding promises on session shut down

Fixes #556. Adds a catch-all statement that promises shouldn't outlive
the session they were returned from and indicates what error they should
reject with when the session shuts down.



### [Explicitly specify how the views array is populated](https://github.com/immersive-web/webxr/pull/614)

Merged Wed May 01 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Explicitly specify how the views array is populated (#614)

Explicitly specify how the views array is populated when calling `getViewerPose()`.



### [Remove gravity mention](https://github.com/immersive-web/webxr/pull/616)

Merged Wed May 01 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Remove gravity mention



### [Remove redundant "abort these steps" in requestSession() algorithm](https://github.com/immersive-web/webxr/pull/645)

Merged Wed May 15 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Remove redundant "abort these steps"

"and abort these steps" is unnecessary as the steps are aborted two steps later. This would also prevent "pending immersive session" from being cleared.



### [Make XRRay.matrix unique, add steps for obtaining it](https://github.com/immersive-web/webxr/pull/655)

Merged Tue May 28 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Make XRRay.matrix unique, add steps for obtaining it (#655)

Adds an algorithm for how `XRRay.matrix` must be calculated to ensure compatibility between UAs.



### [Specify that projection matrices may include shear](https://github.com/immersive-web/webxr/pull/575)

Merged Mon Apr 01 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Specify that projection matrices may include shear

Fixes #461.

At the January F2F we agreed that the `projectionMatrix` attribute
should remain a matrix to allow for more complex projections that
include, for example, shearing. In order to dissuade applications from
attempting to decompose the matrix into a view frustum, which wouldn't
properly account for that, this PR adds text to the spec that explicitly
states that decomposition is a bad idea and gives reasoning as to why.



### [`inverse` attribute always returns the same object](https://github.com/immersive-web/webxr/pull/586)

Merged Mon Apr 15 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

`inverse` attribute always returns the same object (#586)

Fixes #576. Specifies that the object returned by `XRRigidTransform`'s
`inverse` attribute must always be the same JS object and, furthermore,
the `inverse` of a transform returned by `inverse` must be the
originating transform.



### [Identify cases where the Gamepad id should be unknown](https://github.com/immersive-web/webxr/pull/615)

Merged Wed May 01 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Identify cases where the Gamepad id should be unknown



### [Remove XRWebGLLayer.requestViewportScaling()](https://github.com/immersive-web/webxr/pull/631)

Merged Thu May 09 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Remove XRWebGLLayer.requestViewportScaling()

This method has been identified as a target for deferring until a future
version of the API, due to it's difficulty to use effectively and
overlap with framebuffer scaling for quality control.



### [Add none variant to XREye](https://github.com/immersive-web/webxr/pull/641)

Merged Tue May 14 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:feature](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Afeature&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Add none variant to XREye (#641)

Fixes #620



### [Added non-normative note about gamepad liveness.](https://github.com/immersive-web/webxr/pull/650)

Merged Wed May 15 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Added non-normative note about gamepad liveness.



### [Remove XRLayer base type.](https://github.com/immersive-web/webxr/pull/688)

Merged Mon Jun 10 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Remove XRLayer base type. (#688)

Also changed `baseLayer` to only accept an `XRWebGLLayer`. This can be
extended in the future in a few ways:

 - Re-introduce XRLayer and change `baseLayer` to take one.
 - Update `baseLayer` to accept a union of layer types.
 - Leave `baseLayer` as WebGL-only and enforce that new layer types must
   use whatever layer array mechanism is introduced.


