# Modularising the WebXR Device API

As discussed at the June face-to-face meeting, we are investigating how we could refactor the WebXR Device API into modules, in order to make progress independently in each module.


# Why should we modularise?

The point of modularising our work is to structure our work to make more consistent progress, and enable multiple features to make progress independently.  Note that this segmentation is NOT a replacement for incubation of features - all these features will still go through the process of incubation prior to entering “WG deliverable” status.  This proposal is specifically detailing how to structure all the work across the CG and the WG, not how to progress that work through the process (that will come in a later proposal).

First, we should define our logic for when to have module boundaries.  This is a gray area; none of the statements below are intended to be absolutes.  There are three main motivations for splitting an area of functionality into a separate module:



*   **Standalone feature:** The functionality is architecturally a standalone feature that may be designed largely separately, and might even be reused in different contexts (e.g. a Lighting Estimation API).
*   **Architectural layering:** The functionality is architecturally a low-level layer that multiple other functional areas will build on
*   **Velocity:**  One area of functionality will take longer or is a much more advanced set than another related feature, or it involves a different community of feature designers.  (e.g. a HUD DOM layer for smartphone AR cases might be much quicker to define than a complete multiview layer feature.)

We should be clear that we do not want to modularise simply for the sake of modularising; there is a cost to each finer granularity.  We would like to start with a relatively minimal set of modules, as we believe it will be easier to break modules apart in the future than to recombine them.


# The Current Proposal

We should define the following modules from the WebXR Device API as it stands today:



*   **WebXR Core:** the base layer functionality shared across VR and AR, and VR features
    *   **Base layer:** Sessions, spaces, transforms, poses, views, etc.
        *   **_Contentious:_** There’s some contention over XRRay.  Our general feeling is that it belongs here in WebXR Core, as it’s likely to be generally used across multiple modules, and it will be needed in the AR module very quickly.
    *   **“Immersive-vr” mode:** the VR scenarios
    *   **Input:** XRInputSource, XRInputSourceArray and selection events
    *   **_Contentious:_** There’s also some contention over envBlendMode and ”immersive-ar”.  Our general belief is that these should be defined in this spec, but other features necessary for AR (e.g. any kind of hit-testing) should not be here; this provides the mode switches, but not the ability to use them.  This is to be discussed.
*   **Gamepad Input:** the definition of how advanced input controllers are exposed through Gamepad (i.e. the **<code><em>xr-standard</em></code>** mapping, registry, gamepad identifiers, etc.)
*   **AR:** The core features needed to support ar/environment-blending scenarios (camera alignment, anchors and Real-World-Understanding/hit testing)

We also envision the possibility of the following future modules.  These will not necessarily be defined immediately, and in fact being listed here is no guarantee these modules will even ever eventually exist: they are listed here more as an illustration of the modularisation principles.



*   **Layers core** (layer-source: compositor-backed textures + support for a single layer + layers array; the base layer is zeroth element).  This lays the groundwork for a multilayer architecture, contains the base for multisource, and defines the convenience mechanism for the current XRWebGLLayer. WebGL2 image source is part of Layers core.
*   **HUD DOM layer:** A single Layer available to define HUD easily - e.g., for smartphone AR use cases (although it can apply outside that scenario).
*   **Advanced layers:** World-space quad layers, cylindrical layers, … multiview layers, etc.
*   **Hand input:** Support (beyond how hand input might map into XRInputSource) for exposing hand input.
*   **Lighting estimation**: Exposure of estimation of ambient lighting.
*   **Gaze tracking**: Exposing eye tracking as input.
*   **Virtual keyboard API:** Exposes the convenience of a virtual keyboard for text input.
