## Recent Spec Changes - from 2019-02-22 to 2019-03-29

Edit on [Github](https://github.com/immersive-web/administrivia/blob/master/newsletter/2019-02-22-to-2019-03-29-Recent_Spec_Changes.md).
### [Gamepad-based button/axis state](undefined)

Merged Fri Mar 01 2019 - <i>ed:explainer</i>, <i>ed:feature</i> - Closed T18:10:01Z

Gamepad-based button/axis state (#499)

This commit describes how to access to controller button and axis state for `XRInputSource`s via a `gamepad` attribute, which is an instance of the `Gamepad` interface described in the Gamepad API. It details the additional restrictions that apply to gamepads that are exposed in this way, as well as how they interact with the existing `select/selectstart/selectend` events.



### [Spec text for the identity reference space](undefined)

Merged Tue Mar 05 2019 - <i>ed:spec</i> - Closed T19:07:18Z

Spec text for the identity reference space (#520)

Adds text and algortihms detailing the creation of the `identity` reference space to the spec.



### [Indicate the preferred ergonomics of a tracked-pointer ray](undefined)

Merged Mon Feb 25 2019 - <i>ed:spec</i> - Closed T23:07:48Z

Indicate the preferred ergonomics of a tracked-pointer ray (#524)



### [Remove viewMatrix and add XRTransform.inverse()](undefined)

Merged Fri Mar 08 2019 - <i>ed:explainer</i>, <i>ed:spec</i> - Closed T00:07:55Z

Remove viewMatrix and add XRRigidTransform.inverse() (#531)

Long-requested API cleanup to get rid of the explicit `viewMatrix` attribute, paired with a method for getting the inverse of an `XRRigidTransform`. The `inverse()` method can both be used to get the value that was previously returned by the `viewMatrix` (`transform.inverse().matrix`) and also makes application of the `XRReferenceSpace.originOffset` attribute easier if your use case happens to feel "backwards" from the default behavior.



### [Specify that getViewerPose throws an error for non-rAF XRFrames](undefined)

Merged Fri Feb 22 2019 - <i>ed:explainer</i>, <i>ed:spec</i> - Closed T23:42:36Z

Specify that getViewerPose throws an error unless the frame come from a rAF call.



### [Spec: Move outputContext to XRRenderState](undefined)

Merged Tue Mar 19 2019 - <i>ed:spec</i> - Closed T20:27:45Z

Spec: Move outputContext to XRRenderState (#536)

This change makes the outputContext part of the Session's render state, as is outlined in the explainer, so that it can be managed by the same timing as the rest of the state. This change requires slightly more logic than other render state values since it may need to remove the outputContext from a session that it was previously assigned to.



### [Spec: Stationary subtype support is all-or-nothing](undefined)

Merged Mon Feb 25 2019 - <i>ed:spec</i> - Closed T21:13:04Z

Spec: Stationary subtype support is all-or-nothing (#537)



### [added a few AR device examples](undefined)

Merged Mon Feb 25 2019 - <i>ed:explainer</i> - Closed T18:10:23Z

added a few AR device examples



### [Add ignoreDepthValues attribute to the XRWebGLLayer](undefined)

Merged Thu Mar 07 2019 - <i>ed:explainer</i>, <i>ed:feature</i>, <i>ed:spec</i> - Closed T23:44:37Z

Add ignoreDepthValues attribute to the XRWebGLLayer (#548)

This value instructs the UA to prevent the values left in the depth
buffer after a frame is rendered for compositing. If left false (the
default) the UA is allowed to use the depth buffer for things like
improved reprojection.

Also includes some language specifying how the depth buffer is
interpreted and indicating that reverse-Z projection is acceptable.



### [Explainer: requestReferenceSpace no longer takes an array](undefined)

Merged Thu Mar 07 2019 - <i>ed:spec</i> - Closed T23:06:54Z

requestReferenceSpace no longer takes an array

This change brings the explainer's IDL signature back inline with the
version that's in the spec until we determine once and for all if we
should allow this function to accept an array or not.Tellingly, despite
multiple code examples using requestReferenceSpace only one, the one
explicitly showing the fallback behavior, was actually using the
"correct" form of the call prior to this PR.



### [Validate position DOMPointInit](undefined)

Merged Mon Mar 25 2019 - <i>ed:spec</i> - Closed T18:29:38Z

Validate position DOMPointInit



### [Allow flexible depth for screen-based ray input](undefined)

Merged Tue Mar 26 2019 - <i>ed:explainer</i> - Closed T22:26:45Z

Allow flexible depth for screen-based ray input

For screen-based input, it seems overly specific to require that the ray origin must be at the near plane. If the system knows the actual position of the screen in 3D space, i.e. for a zSpace-style display or for smartphone AR, it would be preferable to use the actual mapping of the touch point into virtual world space for this. For example, if you use touch controls to add bubbles or other particle effects to the scene, it would look most natural to have those actually originate at the touched point.

As an additional complication, https://github.com/immersive-web/webxr/pull/548 changed the core spec to explicitly allow reversed-Z where `depthFar` is less than `depthNear`. If the actual screen plane isn't available, it would be more consistent to use the closer of the two instead of always using `depthNear`.

As far as I can tell the spec itself doesn't currently require any particular depth for `XRTargetRayMode` `screen`.

See also https://github.com/immersive-web/webxr/issues/489#issuecomment-455291966 - I think it's problematic to assume that the screen plane corresponds to the near plane.


