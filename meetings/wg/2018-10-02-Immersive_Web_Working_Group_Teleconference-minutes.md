  <h2><a name="attendees" id="attendees">Attendees</a></h2>
  <div class="intro">
    <dl>
      <dt>Present</dt>
      <dd>cwilso, Dominique_Hazael-Massieux, Alex_Turner,
      Max_Rebuschatis, Rik_Cabanier, Ada_Rose_Cannon, Trevor_Smith,
      Brandon_Jones, David_Dorwin, Ron_Padzensky, Phu_Le,
      Nell_Waliczek, Artem, Bolgar, David, Dorwin</dd>
      <dt>Regrets</dt>
      <dd></dd>
      <dt>Chair</dt>
      <dd>adarose</dd>
      <dt>Scribe</dt>
      <dd>cwilso</dd>
    </dl>
  </div>
  <h2>Contents</h2>
  <ul>
    <li>
      <a href="#agenda">Topics</a>
      <ol>
        <li>
          <a href="#item01">Nell to give short update on Privacy
          workshop</a>
        </li>
        <li>
          <a href="#item02">Address confusion regarding
          XRFrameOfReference types - NellWaliczek</a>
        </li>
        <li>
          <a href="#item03">Is XRDevice still necessary? - toji</a>
        </li>
      </ol>
    </li>
    <li>
      <a href="#ActionSummary">Summary of Action Items</a>
    </li>
    <li>
      <a href="#ResolutionSummary">Summary of Resolutions</a>
    </li>
  </ul>
  <hr>
  <div class="meeting">
    <p class="irc">&lt;<cite>scribe</cite>&gt; scribe: cwilso</p>
    <p class="phone"><cite>Ada:</cite> we sent out notes on IRC,
    etc, last week, and we're going to trial that system today and
    at TPAC.<br>
    ... zakim, who is here?</p>
    <h3 id="item01">Nell to give short update on Privacy
    workshop</h3>
    <p class="irc">&lt;<cite>dom</cite>&gt; <a href="https://www.w3.org/Privacy/permissions-ws-2018/">W3C Workshop
    on Permissions and User Consent</a></p>
    <p class="phone"><cite>NW:</cite> there was a 2-day W3C
    Workshop, covering wide range of topics from value of
    permission prompts and how users understand them, to
    DoNotTrack<br>
    ... I presented the thinking we've had, from John's doc (and a
    "what is webxr")</p>
    <p class="irc">&lt;<cite>dom</cite>&gt; <a href="https://www.w3.org/Privacy/permissions-ws-2018/WebXR.pdf">THE
    IMMERSIVE WEB, Nell Waliczek (slides at workshop)</a></p>
    <p class="phone"><cite>NW:</cite> covered different threats we
    see, and asked for feedback.</p>
    <p class="irc">&lt;<cite>dom</cite>&gt; <a href="https://www.w3.org/2018/09/26-permissions-minutes.html#item04">
    Minutes of session on permissions in New Contexts</a></p>
    <p class="phone"><cite>NW:</cite> in the context of feedback,
    asked for prior art. two things that came up were Devices and
    S3nsors and Fullscreen (so, already the things we were looking
    at)?</p>
    <p class="irc">&lt;<cite>dom</cite>&gt; <a href="https://www.w3.org/2018/09/27-permissions2-minutes.html#item01">
    Minutes of second session on XR in workshop</a></p>
    <p class="phone"><cite>NW:</cite> followup: I presume we are
    going to talk about this at TPAC, and/or I can set up another
    telecon about this topic. I don't think anything directly
    actionable came out of the workshop<br>
    ... one thing that did come out was "what would it look like
    for the W3C to do user research to drive questions like 'do
    users understand the privacy decisions they're making'?"<br>
    ... there were a couple instances of people not making progress
    due to lack of usable user data on what users actually
    understand, and being opinion-based instead.<br>
    ... &lt;/end summary&gt;</p>
    <p class="phone"><cite>Ada:</cite> we [IW chairs+editors] have
    been discussing the next FTF, post-TPAC</p>
    <p class="phone">We've settled on Tuesday January 29th -
    Wednesday January 30th, at Samsung Research America in the bay
    area</p>
    <p class="phone"><cite>NW:</cite> You may be surprised, as we
    don't even have the agenda for TPAC out yet, but given our
    tight timeframes, we wanted to get it on the calendar.</p>
    <h3 id="item02">Address confusion regarding XRFrameOfReference
    types - NellWaliczek</h3>
    <p class="phone"><a href="https://github.com/immersive-web/webxr/issues/396">https://github.com/immersive-web/webxr/issues/396</a></p>
    <p class="phone">and <a href="https://github.com/immersive-web/webxr/issues/389">https://github.com/immersive-web/webxr/issues/389</a>
    on local frame of reference</p>
    <p class="phone"><cite>NW:</cite> sorry to not get the summary
    out ahead of time.<br>
    ... at FTF, we spent 2-2.5 hrs talking about general confusion
    on frames of reference, how it relates to anchors, etc<br>
    ... how are we going to shape this information so it's sensible
    to developers (without that 3 hours of explanation).<br>
    ... so I've been putting together a proposal that covers
    everything I heard at the FTF - PR pending, should show up
    tomorrow.<br>
    ... creating a mental model from what the developer is trying
    to do, rather than from what the tracking system exposes.<br>
    ... my intent is to chat about it next Tuesday in the offweek
    call,<br>
    ... and merge it (or can it) within the next two weeks.<br>
    ... the design covers 3 things: 1) frame of reference types, 2)
    local frame of reference, and 3) poseless sessions</p>
    <p class="irc">&lt;<cite>lincolnfrog</cite>&gt; what about the
    dynamic coordinate systems part of that?</p>
    <p class="irc">&lt;<cite>lincolnfrog</cite>&gt; sounds good,
    thanks!</p>
    <p class="phone"><cite>NW:</cite> for the first round, there
    are 5-6 smaller scope issues I didn't include yet. the intent
    is to list the "further issues to address" in the PR, and I'll
    file those issues when merging.</p>
    <p class="phone"><cite>BJ:</cite> I've been working with Nell
    closely on this proposal, and I'm on board. we're discovering
    just how tightly intertwined the entire API is, but we're
    trying to keep these large-scale changes as modular as
    possible.</p>
    <p class="phone"><cite>NW:</cite> as I was pulling coordinate
    systems/frame of reference stuff together, I realized we should
    do the same for the input stuff.<br>
    ... should we defer discussing URP/Poseless until my update is
    out?</p>
    <p class="phone"><cite>BJ:</cite> David outlined some of the
    pros and cons - I think the "next steps" bit had an interesting
    question, "should WebXR always be able to create a session,
    even if it doesn't track a device?:"<br>
    ... I'd like to get a feel for how people feel about this
    concept?</p>
    <p class="irc">&lt;<cite>BrandonJones_Google</cite>&gt; +1</p>
    <p class="irc">&lt;<cite>adarose</cite>&gt; +1</p>
    <p class="irc">&lt;<cite>NellWaliczek</cite>&gt; +1</p>
    <p class="phone"><cite>AT:</cite> poseless in general seems
    find; wonder how much we need to provide model transforms. [?
    sorry, my attention wandered]</p>
    <p class="phone"><cite>NW:</cite> but from Microsoft's
    perspective, you'd be okay creating a session even with no
    tracking device available?</p>
    <p class="phone"><cite>AT:</cite> yes, I think so, would want
    to see full design</p>
    <p class="phone"><cite>TS:</cite> My problem with this has
    always been not technical, but a general concern - I get that
    uniform RAF would be good, but this seems like it's turning
    into a general rendering use case, that might be NOT XR.</p>
    <p class="phone"><cite>BJ:</cite> Nell and I had discussed
    "mutable sessions" at one point - sessiosn that could go from
    inline to immersive and back<br>
    ... that might alleviate that concern a bit? But of course we
    might not go with that API shape.</p>
    <p class="phone"><cite>NW:</cite> Also, don't read too much
    into "we've contemplated this". It was just a thought
    experiment, not a PR.</p>
    <p class="phone"><cite>TS:</cite> I get this. But if someone
    made a session that works in flat mode, why isn't think just
    called a "rendering session" rather than an XR session?<br>
    ... it';s not a killer to the idea, but just a concern in
    positioning.</p>
    <h3 id="item03">Is XRDevice still necessary? - toji</h3>
    <p class="phone"><cite>BJ:</cite> As of 15 minutes ago, I have
    a PR up. WHY HAVEN'T YOU ALL READ IT YET?!?<br>
    ... but to explain ... one of the things I personally heard
    from developers attemping to use the XR API is that it's very
    complex.<br>
    ... there are areas that I think we can simplify, and at the
    prompting of Apple and others, the XRDevice became a lot less
    interesting.<br>
    ... this PR moves session creation up to ???, and gets rid of
    XRDevice altogether. Please take a look.</p>
    <p class="irc">&lt;<cite>adarose</cite>&gt; <a href="https://github.com/immersive-web/webxr/pull/405/files">https://github.com/immersive-web/webxr/pull/405/files</a></p>
    <p class="phone"><cite>AT:</cite> at a high level, it makes
    sense to me. The only time I'd expect to see this would be
    multiple headsets on a desktop, or choosing between AR or VR on
    a mobile device that supports both. But the latter seems
    fixable with XRModes.<br>
    ... we can always add a device abstraction later if necessary
    for the former case,</p>
    <p class="phone"><cite>NW:</cite> AT, can you ask Rafael to
    take a look at this, to sanity-check device
    connect/disconnect?</p>
    <p class="irc">&lt;<cite>NellWaliczek</cite>&gt; Specifically
    regarding adaptor selection</p>
    <p class="phone"><cite>AT:</cite> sure. even if there's a gap,
    it's quite possible we could fill it without re-introducing the
    whole device layer.</p>
    <p class="phone"><cite>ada:</cite> I hope you all found IRC
    minuting okay. Any last points/</p>
    <p class="phone"><cite>NW:</cite> we do want to get into a
    better position on scribing. We'll need to rotate scribes.</p>
    <p class="phone"><cite>Dom:</cite> for anyone who has
    hesitations on this, we'll be there FTF at TPAC.</p>
    <p class="irc">&lt;<cite>dom</cite>&gt; <a href="https://github.com/immersive-web/administrivia/tree/master/meetings/wg">
    WG Meetings repo</a></p>
    <p class="irc">&lt;<cite>adarose</cite>&gt; +1</p>
  </div>
  <h2><a name="ActionSummary" id="ActionSummary">Summary of Action
  Items</a></h2><!-- Action Items -->
  <h2><a name="ResolutionSummary" id="ResolutionSummary">Summary of
  Resolutions</a></h2><!-- Resolutions -->
  [End of minutes]<br>
  <hr>
  <address>
    Minutes manually created (not a transcript), formatted by David
    Booth's <a href="http://dev.w3.org/cvsweb/~checkout~/2002/scribe/scribedoc.htm">
    scribe.perl</a> version 1.154 (<a href="http://dev.w3.org/cvsweb/2002/scribe/">CVS log</a>)<br>
    $Date: 2018/10/02 18:17:07 $
  </address>
  </div>
