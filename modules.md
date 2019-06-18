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
    *   **Base layer:** Sessions, spaces, transforms, poses, views, the environmentBlendMode attribute, etc.
    *   **“Immersive-vr” mode:** the VR scenarios
    *   **Input:** XRInputSource, XRInputSourceArray and selection events
*   **Gamepad Input:** the definition of how advanced input controllers are exposed through Gamepad (i.e. the **<code><em>xr-standard</em></code>** mapping, registry, gamepad identifiers, etc.)
*   **AR:** The core features needed to support ar/environment-blending scenarios (The "immersive-ar" session mode definition, some ability to access the camera aligned with the XR frame (in order to support polyfilling features), anchors and some type of Real-World-Understanding/hit testing API).  XRRay will be placed in this module unless we discover other features that need it outside of AR and need to move it or make it its own module.  It is expected this module will trail the previous two in schedule.

We also envision the possibility of the following future modules.  These will not necessarily be defined immediately, and in fact being listed here is no guarantee these modules will even ever eventually exist: they are listed here more as an illustration of the modularisation principles.



*   **Layers core** (layer-source: compositor-backed textures + support for a single layer + layers array; the base layer is zeroth element).  This lays the groundwork for a multilayer architecture, contains the base for multisource, and defines the convenience mechanism for the current XRWebGLLayer. WebGL2 image source is part of Layers core.
*   **HUD DOM layer:** A single Layer available to define HUD easily - e.g., for smartphone AR use cases (although it can apply outside that scenario).
*   **Advanced layers:** World-space quad layers, cylindrical layers, … multiview layers, etc.
*   **Hand input:** Support (beyond how hand input might map into XRInputSource) for exposing hand input.
*   **Lighting estimation**: Exposure of estimation of ambient lighting.
*   **Gaze tracking**: Exposing eye tracking as input.
*   **Virtual keyboard API:** Exposes the convenience of a virtual keyboard for text input.
