### Recent Spec Changes - 2019-01-01

Edit on [Github](https://github.com/immersive-web/administrivia/blob/master/newsletter/2019-01-01-Recent_Spec_Changes-agenda.md).

14 Matching Merged PRs

* [Add XRRenderState to the spec](https://github.com/immersive-web/webxr/pull/458) - spec
> Also fixed a minor inconsistency in the explainer regarding the name of the associated dictionary.
* [ Describe the identity reference space](https://github.com/immersive-web/webxr/pull/459) - explainer
> This adds a new reference space type that takes the place of passing `null` as the mechanism to return identity poses. Move to handle it with a new space like this was due the desire to allow the `originOffset` to still be used even in situations with no tracking.
> 
> Nell and I had a question about whether or not the included code sample is something that belongs in the spec and/or explainer, since it's a pretty specific case and the purpose of this doc is not to teach anyone quaternion math. Still, it seems like a good demonstration of why this new type matters. Thoughts?
* [Handle pose queries in a more generalized fashion](https://github.com/immersive-web/webxr/pull/460) - spec,explainer
> This PR is intended to pave the way for making it easier to introduce new types of pose tracking functionality in the future by making how we query poses for almost everything more generalized. (The viewer pose is still special because it's the only thing that needs the `views` array, but even there this change makes it less of an outlier.) Ideally this change will make it much easier to reason about adding things like anchors in the future, and also serves to set the stage for #384 as well as fixing the frame-bound concern brought up in that issue.
* [Make outputContext part of the XRRenderState](https://github.com/immersive-web/webxr/pull/504) - explainer
> This was discussed at the Jan 2019 F2F as part of a broader topic of refactoring output contexts. Making output contexts mutable as described in the PR was seen as non-controversial while other aspects of the discussion did not reach an agreement.
> 
> Change moves setting the `outputContext` from a session-creation time event that was then immutable to part of the `XRRenderState`, which allows it to be changed at any point. `outputContext`'s can still only be associated with a single session at a time, so it will be removed from any previous session when reassigned. 
* [Spec XRPresentationContext creation](https://github.com/immersive-web/webxr/pull/501) - spec
> fixes XRPresentationContext should be a dictionary (https://github.com/immersive-web/webxr/issues/449)
* [Update explainer.md](https://github.com/immersive-web/webxr/pull/508) - explainer,copy-change
> taken the liberty of updating a bunch of relatively minor grammatical changes and minor working updates, such as splitting up very long sentences ...only 1 or 2 actual edits of any semantics ..really nice explainer! just requesting pull for these edits 
* [Added XRPose and related refactors to the spec](https://github.com/immersive-web/webxr/pull/496) - spec
> Refactoring
* [Introduce spec internal concept and start to use Infra spec definitions](https://github.com/immersive-web/webxr/pull/518) - spec
> This change defines a spec internal concept, XR device, distinguished from the
> XR object's XR device internal slot. The XR device concept is not exposed to the
> script surface but just used by spec internal algorithms. The XR device concept
> represents an XR device and the XR object's XR device internal slot can hold an
> XR device.
> 
> This change moves the definition of the list of supported modes from XR object's
> XR device internal slot to XR device concept. This makes us be able to define XR
> device's states under the concept rather than the platform object's internal
> slot and write algorithm steps that reference those states more easly.
> 
> This change specifies navigator.xr attribute's getter and the creation of XR
> object associated with a Navigator object.
> 
> This change introduces the Infra spec defintions to define XR object's
> properties and algorithm steps: select an XR device, supportsSeesionMode()
> method, requestSession() method for this particular PR. (More to come.)
* [Add XRSession.viewerSpace and tidy XRSpace explanations](https://github.com/immersive-web/webxr/pull/491) - explainer
> This PR addresses a few related things I noticed now that the getPose() changes have landed
> 1. We were missing a section that focused on the descriptions of XRSpace and XRPose themselves. I added this to spatial-tracking-explainer.md and moved the XRRigidTransform and XRRay types to be together in that document's idl section
> 2. Having an XRSpace representing the viewer would be really handy for a few reasons. First, it would allow pose data to be queried relative to the viewer, such as "where are the hands relative to the headset?", without having to do extra matrix math. Second, it's easier to describe the consistent targetRaySpace for 'gaze' based input sources. Third, it becomes one of the XRSpaces from which hit testing can be done (See PR #493).
> 3. With both of the above changes in the spatial-tracking-explainer.md, it made sense to move some of the smaller subsections around so content was grouped in a more sensible manner.
> 4. Added a check on the results of `getPose()` in the explainer sample code
> 5. While I was at it, this fixes #478 in the explainer, though the actual spec will still need updating.
> 6. Fixed a few typos, too.
> 
* [Adding an explainer for real-world hit testing](https://github.com/immersive-web/webxr/pull/493) - explainer
> This PR contains an explainer with a proposal for adding real-world hit testing to WebXR.  It builds strongly on the great work done by @lincolnfrog, @judax, @blairmacinyre, and others to clearly define the problem space. While it is expected that hit-testing will often be used to create anchors, this PR does not include a proposal for an anchors API; that will come in a subsequent PR but still needs a bit more design work.
> 
> Rather than a long-winded PR description, I'm hoping that the explainer stands on its own.  Please don't hesitate to call out areas that are unclear.
> 
> For clarity's sake, the base for this PR is the input-explainer-cleanup branch in PR #492
* [Restructures input-explainer.md to improve clarity and prep for hit-testing proposal](https://github.com/immersive-web/webxr/pull/492) - explainer
> While working on the proposal for adding hit testing to WebXR, it became clear that to easily explain the new hit testing concepts, the input explainer needed a bit of house keeping. I ended up moving a large portion of the document content around, so it may be easier to just view the new version of the document rather than the diff.
> 
> The intent with this PR is to clarify the descriptions of existing functionality, not to introduce changes in that functionality. That said, I expect we may uncover shared misunderstandings through the cleaner text, so please do call out things that don't match your expectations. I also removed the grab-and-drag sample code for the moment; it makes a reappearance in the hit-testing-explainer in PR #493
> 
> For ease of diffing, the base for this PR is adding-viewerSpace branch behind PR #491
* [Narrow application of the 'unstable' markup in the spec](https://github.com/immersive-web/webxr/pull/510) - spec,copy-change
> Previously the entire spec was contained in one big "unstable" section. This update changes that to only apply to sections of the spec that the editors (conservatively) feel may still see breaking changes. 
> 
> Sections not marked "unstable" are **not** considered "done". They are expected to still see updates to prose, algorithm improvements, and new additive functionality, but are not likely to have backwards-compatibility-breaking changes made to them going forward.
* [Describe exceptions that updateRenderState may throw.](https://github.com/immersive-web/webxr/pull/511) - spec
> Based on some observations made while attempting to implement `updateRenderState` in Chrome.
* [Specify that frame callbacks are not called without a base layer](https://github.com/immersive-web/webxr/pull/512) - spec
> Pretty self-explanatory. We shouldn't execute callbacks if there's no render target, especially since that facilitates tracking the user movements without an associated visual changes.

