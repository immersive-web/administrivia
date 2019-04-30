## Overall Timeline for WebXR Device API Spec

TAG Review Working Draft: May 1, 2019

VR-Complete Working Draft:  July 1, 2019

Pre-TPAC Working Draft: Sept 1, 2019

CR Draft: December 1, 2019

## The Project At a Glance

The best top-down view of progress in the WebXR Device API specification is to look at the [issues sorted by milestone](https://github.com/immersive-web/webxr/milestones?direction=asc&sort=due_date&state=open).  This view lets you see the milestones, and progress in the milestones.  Additionally, you can get a [more precise view](https://github.com/immersive-web/webxr/issues?utf8=%E2%9C%93&q=is%3Aissue+is%3Aopen+milestone%3A%22May+2019+Working+Draft%22+-label%3A%22fixed+by+pending+PR%22) of what remains to be worked on in the current milestone by masking out the issues that are fixed by pending PRs.

## Milestones

We will organize the work into monthly sprints, each of which is a Milestone in Github.  Work is to be triaged into the milestone (month) they are targeted to be addressed.   Each milestone is due at the **end** of the named month.  Some of the monthly milestones, some of them have particular completeness goals, and will trigger an official Working Draft.  Each milestone is effectively a sprint, and issues may be moved from one milestone to a later one if they are not completed; we will prioritize breaking changes and the completeness of goals in order.

1. **April 2019** - After this milestone, will issue a **TAG Review Request Working Draft**.
2. **May 2019**
3. **June 2019** - End of this milestone is the **“VR-complete” Working Draft**. All breaking changes affecting “the replacement of WebVR” should be resolved.   There may be additional detail or spec text necessary within this scope, but implementers are encouraged to implement that scope, and issues that might destabilize that part of the spec will be prioritized after this point.
4. **July 2019**
5. **August 2019** - End of this milestone is the last **Working Draft **before TPAC, where we will assess and ensure we’re on track to land.
6. **September 2019**
7. **October 2019** - **Final Working Draft**
8. **November 2019/Candidate Recommendation** - At the end of this milestone, we plan to issue a call for consensus on a **Candidate Recommendation**.
9. **REC** - Any followup needed for our final Recommendation.  Note that issues are NOT to be pushed into this milestone prior to issuing our CR.
10. **Future** - this is the generic bucket for “this won’t make v1”. 


## How do WG members ask to (de-)prioritize an issue?

Anyone can enter an issue comment with “/triage” as the start of the comment, and this will trigger a bot to add the editor-triage tag.  Please put detail into the comment to clearly state what you think should change and why.  Editors and chairs will triage issues at a minimum weekly (generally on Monday).

## How do WG members ask to put an issue on the telecon agenda?

If you enter an issue comment with “/agenda” as the start of the comment, this will trigger a bot to add the agenda tag.  Please put detail into the comment to clearly state what you hope to accomplish with the discussion.  Chairs will triage issues weekly on Thursday to prepare agenda for following week on Friday.

## How Labels are used on Issues

We use labels on Github issues to help with triage, and to provide better insight into the issues.  Issues have been triaged if the milestone has been set.  The [defined labels we use](https://github.com/immersive-web/webxr/labels) are:

*   **agenda:** This issue is on [the agenda](https://github.com/immersive-web/webxr/labels/agenda) for discussion in the next WG telecon/FTF.  
*   **ed:explainer:** Include in newsletter, explainer change
*   **ed:feature:** Include in newsletter, adds a feature
*   **ed:spec:** Include in newsletter, spec change
*   **editor triage:** This issue needs triage attention.  You can trigger this label being added with a comment containing “/triage”, and the chairs/editors will triage weekly.  (Once it has been re-triaged, comments will be put in the issue, and the label will be removed.)
*   **fixed by pending PR:** A PR that is in review will resolve this issue.  This will help understand what work is currently in flight vs. unaddressed.
*   **feature request:** This is a request for a new feature.
*   **good starter bug:** This label is used to mark issues that are relatively minor and well-contained, and are available for others to pick up and contribute fixes.  If you want to contribute to the spec directly, these are good bugs to start with.  If you have some time to work on it, and think you can complete it within a week or two, select one of these issues, assign it to yourself and assign the milestone to when you can have it completed. 
*   **potential breaking change:** Issues that may affect the core design structure and affect backward compatibility.  These issues are naturally more important for us to resolve sooner rather than later.
*   **ready for editing:** Design is decided, and this issue ready for Editor to fix.  (aka this is waiting for the Editors to have time, not for a decision to be made.)
*   **spec bug:** Inconsistencies in spec
