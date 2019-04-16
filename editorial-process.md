Immersive Web Editorial Process
===============================

This document is for:

-   Finding out what the editors have been working on.
-   Finding out what is prioritised for working on in the near future.
-   Finding out the timelines of certain features.

This process is new and it is open to feedback if you have urgent concerns please raise them so that the editors can change their process.

We will have a review in a Working Group call July 2019 to reevaluate whether this process is working and how it should be changed.

How the Immersive Web timelines are documented
----------------------------------------------

We document the timelines for what is being worked on by using Github's [Milestones](https://github.com/immersive-web/webxr/milestones?direction=asc&sort=due_date&state=open) features. Each issue in the repo once brought to the attention of the editors gets assigned a milestone.

These come in 3 flavours:

-   Future, issues which aren't due for immediate attention.
-   CR for 1.0, this contains issues which need to be resolved in order for the standard to be put forward for candidate recommendation the deadline for this may get pushed back in the case of delays.
-   [Month name] Working Draft, these issues are being worked on so that they can be released in monthly Working Drafts. They are sealed before the named month so that they can be released in that Month. I.e. May '19 Working draft will not receive any more work in May, opened issues will get transferred to the milestone June '19 Working Draft.

NB: When browsing [WebXR Milestones](https://github.com/immersive-web/webxr/milestones?direction=asc&sort=due_date&state=open) via github by default the sort order is not correct so make sure it is sorted by 'closest due date'.

There will always be at least two open Month Milestones, one for the current work and one for issues to be targeted in the following month. Their deadlines will never change to keep to the schedule of monthly Working Draft updates.

Before the start of a month the milestone is closed and a snapshot of the WebXR Device API standards will be taken and prepared to be released as a working draft.

Uncompleted issues are moved to the next month.

Should there now only be a single month milestone left open a new milestone will be created for the subsequent month.

A review of issues in CR for 1.0 will be used to add issues into the newly created milestone. In addition some higher priority issues may be moved into the current month being worked on.

E.g.

1.  On April 30th the last issues are finished for the May Milestone
2.  Unfinished Issues move into June
3.  A new July milestone is created
4.  Issues from the 'CR for 1.0' get moved into the new 'July' Milestone and maybe also in to the pre-existing June milestone.

[Samples](https://github.com/immersive-web/webxr-samples) & [Polyfill](https://github.com/immersive-web/webxr-polyfill)
-----------------------------------------------------------------------------------------------------------------------

Ideally every time a new working draft is published the [polyfill](https://github.com/immersive-web/webxr-polyfill) gets a new release to align with that working draft.  Currently these repos are not in a state where that can happen.

To verify the polyfill each resolved issue should be tested against the samples. They will also need to be updated. Currently they are also not in a state to do this.

The immediate priority is to bring them into alignment with the spec, we would love to receive contributions to the polyfill and samples to get to this state:

-   Editors will start doing triage.
-   Receiving PRs for the issues raised would be very welcome.

A longer term goal is having tests in the 'Web Platform Tests' which can be run against the polyfill.

[Documentation](https://github.com/immersive-web/webxr-reference)
-----------------------------------------------------------------

This is a repo of what we would like to be published to MDN as a developer friendly source of documentation. Like the samples and the polyfill making a release each time there is a new working draft would be ideal.

[Labels](https://github.com/immersive-web/webxr/labels)
-------------------------------------------------------

We use labels in the WebXR repos to assist with automation or bring issues for attention.

-   The Agenda label is for issues which should be discussed in the next Working Group Call.
-   Labels which being 'ed:' are for automated generation of the newsletter.
-   You may add the 'editor triage' label to bring it to the focus of editors please add a note to state why this is important to you. You can add this label by adding a comment containing ‘/triage’.
