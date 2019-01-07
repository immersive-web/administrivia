# Transition process from proposals to spec for the Immersive Web

The Immersive Web Working Group and Community Group work together to develop the specifications for building Augmented Reality and Virtual Reality applications on the web. New proposals will be developed in the community group and transition to the working group when they are ready. This document aims to outline the process for taking an idea all the way from inception through to publishing in the Immersive Web groups.

## 1. Proposing an Idea

Ideas should first be proposed as [issues in the proposals repo](https://github.com/immersive-web/proposals/issues). Here they can be raised to the attention of the group, and be discussed and rationalised in the context of the Immersive Web work.  Proposals may also be raised to discuss in the community group teleconferences.

The intent at this stage is to raise awareness, gauge interest and get feedback on the idea or potential approaches to solutions. 

## 2. Creating a Repo

Once there is clear interest from multiple parties in exploring an issue, the Community Group chair can create a repository to discuss (or move one into the Immersive-Web organisation, if the proposer had one already).  

The repository for a proposal enables issue tracking, and branching.  In particular, any issues raised in the initial discussion in the "proposals" repository should be filed in the new repository.

The best place to start with any new proposal is **[an explainer](https://w3ctag.github.io/explainers)** to provide a quick introduction to why the feature is needed and what it does. It should be written for a non-technical audience to provide a fast introduction for non-experts to understand.

At this stage it's still okay for there just to be a single contributor managing and controlling the contents of the proposal. It is also okay to push changes straight to master without needing peer review.

## 3. Incubate the idea in the Community Group

The goal here is to develop the idea further to ensure it is viable and to work through issues with the idea. Putting together tests, polyfills, demos or implementations is incredibly valuable to this effort because they can be used to prove that the change is wanted.

Gaining feedback from the community and developers to inform the development is very valuable here because the API surface can be radically changed with little impact on the rest of the standard and without needing buy in from the rest of the group or the editors.

## 4. Move to the Working Group

Now the issue is in a good format it needs to move somewhere that can actually create standards - most commonly, the Immersive Web Working Group.  (Not all features will move to the IWWG - some may move to HTML or other WGs, or to other standards-developing organizations altogether.) 

There should be significant agreement from implementers that the
proposal is baked enough to move to the Working Group to lock down and ship. Having at least two implementers who have built prototypes is a significant signal. Tests should be developed at this stage.

For features that should move to the Immersive Web Working Group, the IWWG will need to vote to adopt this.  The Community Group chair can help connect with the WG chairs, and the WG will need to vote to adopt the work.

If the proposed change is within the scope of the working group charter then it shouldn't be a problem; but if the proposed feature is outside the scope of the charter, the working group may need to be re-chartered to adopt a broader scope. 
Work performed in the Working Group will have to include clear consensus and appropriate peer review.  Once the core design has been settled, if the work is not being adopted as a separate specification deliverable from the WG, the text can move into the core WebXR Device API specification and the feature design docs from the repo should be marked as of historical interest only.
