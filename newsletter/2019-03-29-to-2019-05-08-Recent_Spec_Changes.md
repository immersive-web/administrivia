## Recent Spec Changes - from 2019-03-29 to 2019-05-08

Edit on [Github](https://github.com/immersive-web/administrivia/blob/master/newsletter/2019-03-29-to-2019-05-08-Recent_Spec_Changes.md).
### [Remove attribs that only reflect requested values](https://github.com/immersive-web/webxr/pull/574)

Merged Fri Apr 19 2019 - ![ed:explainer](/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7) ![potential breaking change](/svg/?text=potential%20breaking%20change&bgcolor=d32a6b)

Remove attribs that only reflect requested values (#574)

Remove attribs that only echo creation parameters:

 - XRSession.mode;
 - XRWebGLLayer.depth;
 - XRWebGLLayer.stencil;
 - XRWebGLLayer.alpha;
 - XRStationaryReferenceSpace.subtype;



### [Rename supportsSessionMode to supportsSession](https://github.com/immersive-web/webxr/pull/595)

Merged Mon Apr 22 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7) ![potential breaking change](/svg/?text=potential%20breaking%20change&bgcolor=d32a6b)

Rename supportsSessionMode to supportsSession (#595)

Fixes #592. Brings the method name inline with requestSession, which now takes the
same arguments.



### [Explicitly spec out native origins](https://github.com/immersive-web/webxr/pull/621)

Merged Tue May 07 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Explicitly spec out native origins (#621)

Adds native origins for input spaces, viewerSpace, identity, and position-disabled spaces. Specifies that the native origin of identity spaces is constant when there is no tracking data.



### [Overhaul XRSpace, get(Viewer)Pose definitions](https://github.com/immersive-web/webxr/pull/609)

Merged Sat Apr 27 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Overhaul XRSpace, get(Viewer)Pose definitions (#609)

Formalizes the definitions of origins, transforms, and some of the math
involved. This will hopefully give us a better foundation on top of which
we can better talk about spacial concepts.

**Huge** thank you to @klausw, @Manishearth, and @NellWaliczek
for helping to iterate through this fairly tricky language and land on
something that much more rigorous.



### [Consolidate reference space types and interfaces](https://github.com/immersive-web/webxr/pull/587)

Merged Wed May 01 2019 - ![ed:explainer](/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Consolidate reference space types and interfaces (#587)

Consolidate the various interfaces that extended XRReferenceSpace, with the exception of XRBoundedReferenceSpace which was still necessary to communicate the boundsGeometry. This PR also eliminates the 'stationary' XRReferenceSpaceType in favor of making all of it's subtypes top level types. Which, in turn, eliminates the need for the options dictionary when creating a reference space, so this PR also changes that call to only take the type enum (an options dictionary can be added as a second argument in the future if needed, as described by #542.



### [Make origin offset immutable](https://github.com/immersive-web/webxr/pull/612)

Merged Wed May 01 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Make origin offset immutable (#612)

Fixes #580. Changes originOffset to be immutable and establish that the
way that the originOffset changes is by constructing a new reference
space with the base space and an additional offset to apply on top of
it. This should hopefully solve several timing issues related to
changing the originOffset mid-frame.



### [Make boundsGeometry work relative to the effective origin](https://github.com/immersive-web/webxr/pull/613)

Merged Wed May 01 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Make boundsGeometry work relative to the effective origin (#613)



### [Reject outstanding promises on session shut down](https://github.com/immersive-web/webxr/pull/585)

Merged Mon Apr 15 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Reject outstanding promises on session shut down

Fixes #556. Adds a catch-all statement that promises shouldn't outlive
the session they were returned from and indicates what error they should
reject with when the session shuts down.



### [Explicitly specify how the views array is populated](https://github.com/immersive-web/webxr/pull/614)

Merged Wed May 01 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Explicitly specify how the views array is populated (#614)

Explicitly specify how the views array is populated when calling `getViewerPose()`.



### [Remove gravity mention](https://github.com/immersive-web/webxr/pull/616)

Merged Wed May 01 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Remove gravity mention



### [Specify that projection matrices may include shear](https://github.com/immersive-web/webxr/pull/575)

Merged Mon Apr 01 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Specify that projection matrices may include shear

Fixes #461.

At the January F2F we agreed that the `projectionMatrix` attribute
should remain a matrix to allow for more complex projections that
include, for example, shearing. In order to dissuade applications from
attempting to decompose the matrix into a view frustum, which wouldn't
properly account for that, this PR adds text to the spec that explicitly
states that decomposition is a bad idea and gives reasoning as to why.



### [`inverse` attribute always returns the same object](https://github.com/immersive-web/webxr/pull/586)

Merged Mon Apr 15 2019 - ![ed:explainer](/svg/?text=ed%3Aexplainer&bgcolor=875fb7) ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

`inverse` attribute always returns the same object (#586)

Fixes #576. Specifies that the object returned by `XRRigidTransform`'s
`inverse` attribute must always be the same JS object and, furthermore,
the `inverse` of a transform returned by `inverse` must be the
originating transform.



### [Identify cases where the Gamepad id should be unknown](https://github.com/immersive-web/webxr/pull/615)

Merged Wed May 01 2019 - ![ed:spec](/svg/?text=ed%3Aspec&bgcolor=875fb7)

Identify cases where the Gamepad id should be unknown


