## Recent Spec Changes - from 2019-05-08 to 2019-06-17

Edit on [Github](https://github.com/immersive-web/administrivia/blob/master/newsletter/2019-05-08-to-2019-06-17-Recent_Spec_Changes.md).
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



### [Rename getPose arg referenceSpace->baseSpace](https://github.com/immersive-web/webxr/pull/659)

Merged Mon May 20 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Rename getPose arg referenceSpace->baseSpace (#659)

The use of `referenceSpace` here may inadvertently suggest that it only
takes an `XRReferenceSpace` object, when in reality it can take any
`XRSpace`. Using `baseSpace` as a replacement at the suggestion of
@klausw and @thetuvix.

Plus it's fun to say: `getPose` finds the place of your space in the
baseSpace's space! ;D



### [Update Explainer Text for new requestReferenceSpace modes names](https://github.com/immersive-web/webxr/pull/662)

Merged Tue May 21 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Update Explainer Text for new requestReferenceSpace modes names



### [Handle detached arrays](https://github.com/immersive-web/webxr/pull/684)

Merged Wed Jun 05 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Handle detached arrays (#684)

Handle detached arrays in XRRigidTransform.matrix and XRRay.matrix



### [Move racy parts of requestSession() to the main thread](https://github.com/immersive-web/webxr/pull/706)

Merged Mon Jun 17 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Move racy parts of requestSession() to the main thread (#706)

Move racy parts of requestSession() to the main thread.



### [Remove redundant "abort these steps" in requestSession() algorithm](https://github.com/immersive-web/webxr/pull/645)

Merged Wed May 15 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Remove redundant "abort these steps"

"and abort these steps" is unnecessary as the steps are aborted two steps later. This would also prevent "pending immersive session" from being cleared.



### [Make XRRay.matrix unique, add steps for obtaining it](https://github.com/immersive-web/webxr/pull/655)

Merged Tue May 28 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Make XRRay.matrix unique, add steps for obtaining it (#655)

Adds an algorithm for how `XRRay.matrix` must be calculated to ensure compatibility between UAs.



### [Properly format conditionals](https://github.com/immersive-web/webxr/pull/657)

Merged Mon May 20 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Properly format conditionals (#657)



### [Replace 'list of pending render states' with 'pending render state'](https://github.com/immersive-web/webxr/pull/701)

Merged Fri Jun 14 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Replace 'list of pending render states' with 'pending render state' (#701)

Replace 'list of pending render states' with 'pending render state'



### [Some XRRenderState clarifications](https://github.com/immersive-web/webxr/pull/703)

Merged Fri Jun 14 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Some XRRenderState clarifications



### [Clarify that small overlay UIs are allowed in exclusive access](https://github.com/immersive-web/webxr/pull/709)

Merged Mon Jun 17 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Clarify that small overlay UIs are allowed in exclusive access (#709)

Clarify that small overlay UIs are allowed in exclusive access



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



### [Clarify what value a touchpad should report when not being touched.](https://github.com/immersive-web/webxr/pull/660)

Merged Tue May 21 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Clarify what value a touchpad should report when not being touched. (#660)

Specify that untouched touchpads report axis values of `0`.



### [Better define gamepad placeholder buttons and axes](https://github.com/immersive-web/webxr/pull/661)

Merged Tue May 21 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Better define gamepad placeholder buttons and axes (#661)

Define what values are expected for placeholder elements and when it is appropriate to omit them.



### [Remove XRLayer base type.](https://github.com/immersive-web/webxr/pull/688)

Merged Mon Jun 10 2019 - ![ed:explainer](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Remove XRLayer base type. (#688)

Also changed `baseLayer` to only accept an `XRWebGLLayer`. This can be
extended in the future in a few ways:

 - Re-introduce XRLayer and change `baseLayer` to take one.
 - Update `baseLayer` to accept a union of layer types.
 - Leave `baseLayer` as WebGL-only and enforce that new layer types must
   use whatever layer array mechanism is introduced.



### [Change required gamepad index to -1](https://github.com/immersive-web/webxr/pull/690)

Merged Tue Jun 11 2019 - ![ed:spec](https://iw-newsletter-generator.glitch.me/svg/?text=ed%3Aspec&bgcolor=875fb7)

Change required gamepad index to -1 (#690)


