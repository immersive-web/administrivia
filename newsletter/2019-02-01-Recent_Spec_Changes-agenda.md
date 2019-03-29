## Recent Spec Changes - from 2019-02-22 to 2019-03-29

Edit on [Github](https://github.com/immersive-web/administrivia/blob/master/newsletter/2019-02-01-Recent_Spec_Changes-agenda.md).
### [Gamepad-based button/axis state](undefined)

Merged Fri Mar 01 2019 - <i>ed:explainer</i>, <i>ed:feature</i> - Closed T18:10:01Z

Gamepad-based button/axis state (#499)

This commit describes how to access to controller button and axis state for `XRInputSource`s via a `gamepad` attribute, which is an instance of the `Gamepad` interface described in the Gamepad API. It details the additional restrictions that apply to gamepads that are exposed in this way, as well as how they interact with the existing `select/selectstart/selectend` events.

<details>
  <summary>Initial Description</summary>
  <p>This is a proposal for how we might use the existing Gamepad API to expose controller button and axis state.</p>
</details>


### [Spec text for the identity reference space](undefined)

Merged Tue Mar 05 2019 - <i>ed:spec</i> - Closed T19:07:18Z

Spec text for the identity reference space (#520)

Adds text and algortihms detailing the creation of the `identity` reference space to the spec.

<details>
  <summary>Initial Description</summary>
  <p>Fixes #482</p>
<p>Adding the <code>&quot;identity&quot;</code> reference space type. Not including <code>originOffset</code> at this point to keep PRs focused and easy to review.</p>
</details>


### [Indicate the preferred ergonomics of a tracked-pointer ray](undefined)

Merged Mon Feb 25 2019 - <i>ed:spec</i> - Closed T23:07:48Z

Indicate the preferred ergonomics of a tracked-pointer ray (#524)

<details>
  <summary>Initial Description</summary>
  <p>Fixed #516.</p>
</details>


### [Remove viewMatrix and add XRTransform.inverse()](undefined)

Merged Fri Mar 08 2019 - <i>ed:explainer</i>, <i>ed:spec</i> - Closed T00:07:55Z

Remove viewMatrix and add XRRigidTransform.inverse() (#531)

Long-requested API cleanup to get rid of the explicit `viewMatrix` attribute, paired with a method for getting the inverse of an `XRRigidTransform`. The `inverse()` method can both be used to get the value that was previously returned by the `viewMatrix` (`transform.inverse().matrix`) and also makes application of the `XRReferenceSpace.originOffset` attribute easier if your use case happens to feel "backwards" from the default behavior.

<details>
  <summary>Initial Description</summary>
  <p>Fixes #447.</p>
<p>Ooh, hey! I'm gonna try GitHub's shiny new &quot;Draft Pull Request&quot; thingy here. ('Cuz this PR is clearly not quite there yet, but I feel it's worth discussing anyway.)</p>
<p>This was discussed on the IW call today, but I'll recap here: There's been some ongoing discussion about removing <code>XRView.viewMatrix</code> because it's computable from the values given in the <code>XRView.transform</code>. I've been a bit reluctant to do that simply because if someone <em>is</em> using the matrix then this makes it significantly more involved to get the same value back.</p>
<p>Separately, we had a discussion around the <code>originOffset</code> at the January 2019 Face to Face and one of the outcomes of that was that no matter how we chose to interpret the value given there we'd end up feeling &quot;backwards&quot; about 50% of the time.</p>
<p>This CL attempts to make both of those issues easier by introducing an <code>inverse()</code> method to the <code>XRRigidTransform</code> interface, which simply returns another <code>XRRigidTransform</code> that represents the opposite transform. (&quot;inverse&quot; rather than &quot;invert&quot; because the latter sounds like it modifies the object in place to me. Happy to take opposing opinions on that one.) The math to do this isn't terrible (though as you can tell from the CL I haven't fully worked out the algorithm yet) but it will be a big developer convenience if there's a mechanism to do it in the API.</p>
<p>With this function in place it means that developers that find that their use of <code>originOffset</code> is backwards from what they were expecting can correct it with a simple</p>
<pre><code>referenceSpace.originOffset = transform.inverse();
</code></pre>
<p>Similarly, for developers that would really prefer to use a <code>viewMatrix</code> directly, the call now becomes</p>
<pre><code>// Previously view.viewMatrix
view.transform.inverse().matrix;
</code></pre>
<p>Which is admittedly more verbose but also makes use of a more broadly applicable API mechanism rather than introducing data duplication that we presume most developers won't need.</p>
</details>


### [Specify that getViewerPose throws an error for non-rAF XRFrames](undefined)

Merged Fri Feb 22 2019 - <i>ed:explainer</i>, <i>ed:spec</i> - Closed T23:42:36Z

Specify that getViewerPose throws an error unless the frame come from a rAF call.

<details>
  <summary>Initial Description</summary>
  <p>Previous explainer text indicated that this scenario should have returned <code>null</code>, but that seems inconsistent with the behavior of other similar restrictions, so I've updated it to throw an <code>InvalidStateError</code>. Thanks to Jacob DeWitt (for whom I don't yet know a GitHub handle) for helping highlight the inconsistency!</p>
</details>


### [Spec: Move outputContext to XRRenderState](undefined)

Merged Tue Mar 19 2019 - <i>ed:spec</i> - Closed T20:27:45Z

Spec: Move outputContext to XRRenderState (#536)

This change makes the outputContext part of the Session's render state, as is outlined in the explainer, so that it can be managed by the same timing as the rest of the state. This change requires slightly more logic than other render state values since it may need to remove the outputContext from a session that it was previously assigned to.

<details>
  <summary>Initial Description</summary>
  <p>Also documents the algorithm for removing the ouputContext from previously bound sessions when a new session has been associated.</p>
</details>


### [Spec: Stationary subtype support is all-or-nothing](undefined)

Merged Mon Feb 25 2019 - <i>ed:spec</i> - Closed T21:13:04Z

Spec: Stationary subtype support is all-or-nothing (#537)

<details>
  <summary>Initial Description</summary>
  <p>Fixes #532 and #533</p>
</details>


### [added a few AR device examples](undefined)

Merged Mon Feb 25 2019 - <i>ed:explainer</i> - Closed T18:10:23Z

added a few AR device examples

<details>
  <summary>Initial Description</summary>
  <p>minor suggestion.  Added a few AR device examples to the list of VR device examples.</p>
</details>


### [Add ignoreDepthValues attribute to the XRWebGLLayer](undefined)

Merged Thu Mar 07 2019 - <i>ed:explainer</i>, <i>ed:feature</i>, <i>ed:spec</i> - Closed T23:44:37Z

Add ignoreDepthValues attribute to the XRWebGLLayer (#548)

This value instructs the UA to prevent the values left in the depth
buffer after a frame is rendered for compositing. If left false (the
default) the UA is allowed to use the depth buffer for things like
improved reprojection.

Also includes some language specifying how the depth buffer is
interpreted and indicating that reverse-Z projection is acceptable.

<details>
  <summary>Initial Description</summary>
  <p>Fixes #523.</p>
<p>This value instructs the UA to prevent the values left in the depth buffer after a frame is rendered for compositing. Slightly concerned about potential for confusion regarding the <code>depth</code> and <code>ignoreDepthValues</code> attributes being on the same dictionary, so clarifying bikeshedding is welcome there if you have suggestions.</p>
<p>Given the scope of the feature it felt appropriate to handle both the spec text and explainer text in the same PR. Please take a look!</p>
</details>


### [Explainer: requestReferenceSpace no longer takes an array](undefined)

Merged Thu Mar 07 2019 - <i>ed:spec</i> - Closed T23:06:54Z

requestReferenceSpace no longer takes an array

This change brings the explainer's IDL signature back inline with the
version that's in the spec until we determine once and for all if we
should allow this function to accept an array or not.Tellingly, despite
multiple code examples using requestReferenceSpace only one, the one
explicitly showing the fallback behavior, was actually using the
"correct" form of the call prior to this PR.

<details>
  <summary>Initial Description</summary>
  <p>As requested in #549.</p>
<p>This change brings the explainer's IDL signature back inline with the
version that's in the spec until we determine once and for all if we
should allow this function to accept an array or not.Tellingly, despite
multiple code examples using requestReferenceSpace only one, the one
explicitly showing the fallback behavior, was actually using the
&quot;correct&quot; form of the call prior to this PR.</p>
</details>


### [Validate position DOMPointInit](undefined)

Merged Mon Mar 25 2019 - <i>ed:spec</i> - Closed T18:29:38Z

Validate position DOMPointInit

<details>
  <summary>Initial Description</summary>
  <p>Given that it's a float, comparison with 1 may not be the best idea, but I feel like erroring here is marginally better than ignoring invalid <code>w</code> values.</p>
</details>


### [Allow flexible depth for screen-based ray input](undefined)

Merged Tue Mar 26 2019 - <i>ed:explainer</i> - Closed T22:26:45Z

Allow flexible depth for screen-based ray input

For screen-based input, it seems overly specific to require that the ray origin must be at the near plane. If the system knows the actual position of the screen in 3D space, i.e. for a zSpace-style display or for smartphone AR, it would be preferable to use the actual mapping of the touch point into virtual world space for this. For example, if you use touch controls to add bubbles or other particle effects to the scene, it would look most natural to have those actually originate at the touched point.

As an additional complication, https://github.com/immersive-web/webxr/pull/548 changed the core spec to explicitly allow reversed-Z where `depthFar` is less than `depthNear`. If the actual screen plane isn't available, it would be more consistent to use the closer of the two instead of always using `depthNear`.

As far as I can tell the spec itself doesn't currently require any particular depth for `XRTargetRayMode` `screen`.

See also https://github.com/immersive-web/webxr/issues/489#issuecomment-455291966 - I think it's problematic to assume that the screen plane corresponds to the near plane.

<details>
  <summary>Initial Description</summary>
  <p>For screen-based input, it seems overly specific to require that the ray origin must be at the near plane. If the system knows the actual position of the screen in 3D space, i.e. for a zSpace-style display or for smartphone AR, it would be preferable to use the actual mapping of the touch point into virtual world space for this. For example, if you use touch controls to add bubbles or other particle effects to the scene, it would look most natural to have those actually originate at the touched point.</p>
<p>As an additional complication, https://github.com/immersive-web/webxr/pull/548 changed the core spec to explicitly allow reversed-Z where <code>depthFar</code> is less than <code>depthNear</code>. If the actual screen plane isn't available, it would be more consistent to use the closer of the two instead of always using <code>depthNear</code>.</p>
<p>As far as I can tell the spec itself doesn't currently require any particular depth for <code>XRTargetRayMode</code> <code>screen</code>.</p>
<p>See also https://github.com/immersive-web/webxr/issues/489#issuecomment-455291966 - I think it's problematic to assume that the screen plane corresponds to the near plane.</p>
</details>

