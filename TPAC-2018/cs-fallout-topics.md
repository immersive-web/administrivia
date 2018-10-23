# Coordinate Systems Fallout Topics

This session is to review the issues that were filed/revived after [immersive-web/webxr#409](https://github.com/immersive-web/webxr/pull/409) was merged.  Several of these topics are fairly scoped and we may be able to decide on a course of action.  Others will require deeper investigation before an conclusion can be resolved, so our purpose in discussing will mostly be to familarize the group with the problem and identify individuals who are interested in driving to those conclusions.

## Rectangular, axis-aligned bounds
Issue [immersive-web/webxr#228](https://github.com/immersive-web/webxr/issues/228) is an oldie but goodie.  The original design provides arbitrary polygonal bounds, but developer feedback has been asking for an axis-aligned XZ rectangle.  I'm proposing we leave the existing bounds and also add a new attribute to `XRBoundedFrameOfReference`.  If there are no objections to this, I'll put together a pull request asap.

## Body-locked content
This topic is described in [immersive-web/webxr#416](https://github.com/immersive-web/webxr/issues/416).  The goal of our discussion at TPAC is to (hopefully) settle on which of the proposed designs we'd like to put forward a pull-request for.

## Requiring multiple frames of reference
This topic is described in [immersive-web/webxr#417](https://github.com/immersive-web/webxr/issues/417).  The goal of our discussion at TPAC is to resolve whether this should a "none" or "any" restriction.

## Tracking data in inline sessions
There are security issues associated with exposing 3DOF data automatically in an inline session.  There is also interest in enabling inline sessions to request to access to 6DOF data.  John Pallett will provide an overview of these issues and potential mitigations in a different session at TPAC. (it's just listed here for completeness)

## Diorama content
This topic is described in [immersive-web/proposals#31](https://github.com/immersive-web/proposals/issues/31) filed in the proposals repo, because it's still in the early stages.  It has dependencies on the resolution of the previous issue, so the intention isn't to dig into design work here at TPAC.  The goal is instead to find interested parties to dig into this work or identify further areas for investigation.

## Handling Tracking Loss
Issue [immersive-web/webxr#243](https://github.com/immersive-web/webxr/issues/243) was also originally filed quite some time ago (against WebVR even), and we never reached conclusion.  It's not super clear what guidance we would give WebXR developers about what they should be doing under tracking loss, which makes it challenging to determine how to report it.  A big reason for that is a lack of a unified understanding of the tracking-loss behavior in all the underlying XR platforms. The goal for discussing this issue at TPAC is to gather that information all in one place.  Then, post-TPAC, we can dig into the tradoffs of various design options to work across the ecosystem.

## BIKESHEDDING
Issue [immersive-web/webxr#418](https://github.com/immersive-web/webxr/issues/418) is a placeholder to bikeshed all the types covered in the new explainer doc.  The goal at TPAC is to identify which types are contentious and which are agreeble.
