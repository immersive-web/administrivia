<h1>Immersive Web Working Group teleconf</h1>
  <h2>13 Nov 2018</h2>
  <p><a href=
  'https://github.com/immersive-web/administrivia/blob/master/meetings/wg/2018-11-14-Immersive_Web_Working_Group_Teleconference-agenda.md'>
  Agenda</a></p>
  <h2><a name="attendees" id="attendees">Attendees</a></h2>
  <div class="intro">
    <dl>
      <dt>Present</dt>
      <dd>dom, ada, present, LocMDao, Tony_Brainwaive,
      NellWaliczek, brandonjones, AlexT, Leonard</dd>
      <dt>Regrets</dt>
      <dd>ChrisW</dd>
      <dt>Chair</dt>
      <dd>Ada</dd>
      <dt>Scribe</dt>
      <dd>cabanier, dom</dd>
    </dl>
  </div>
  <h2>Contents</h2>
  <ul>
    <li>
      <a href="#agenda">Topics</a>
      <ol>
        <li>
          <a href="#item01">Towards FPWD</a>
        </li>
        <li>
          <a href="#item02">Define how to request features which
          require user consent</a>
        </li>
        <li>
          <a href="#item03">The Great Bikeshedding II:
          XRFrameOfReference and XRCoordinateSystem</a>
        </li>
        <li>
          <a href="#item04">AOB</a>
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
  <hr />
  <div class="meeting">
    <p class='irc'>&lt;<cite>ada</cite>&gt; zakim choose victim</p>
    <p class='irc'>&lt;<cite>ada</cite>&gt; zakim choose a
    victim</p>
    <p class='irc'>&lt;<cite>cabanier</cite>&gt; scribenick
    cabanier</p>
    <p class='irc'>&lt;<cite>dom</cite>&gt; scribenick:
    cabanier</p>
    <h3 id="item01">Towards FPWD</h3>
    <p class='phone'><cite>dom:</cite> as you know,we are now a
    working group and our goal is to bring XR document to final
    status<br />
    ... this is called the recommendation track<br />
    ... I have a few slides</p>
    <p class='irc'>&lt;<cite>dom</cite>&gt; <a href=
    "https://www.w3.org/2018/Talks/dhm-rec-track-101/?full#2">https://www.w3.org/2018/Talks/dhm-rec-track-101/?full#2</a></p>
    <p class='phone'><cite>dom:</cite> on slide 2, it describes
    what the rec process looks like<br />
    ... from first pw, to rec</p>
    <p class='phone'>our charter says for pwd in november but it
    will likely be december</p>
    <p class='phone'><cite>scribe:</cite> then we can publish as
    many wd as we want<br />
    ... ultimately we want to stabilize and make sure we get
    reviews<br />
    ... we want to get an accessible technology and standardization
    ready<br />
    ... the next big stage is CR<br />
    ... the charter says that is in June which is very
    aggressive<br />
    ... the rest of the process which is REC is mostly updating the
    spec and going through small check with W3C members<br />
    ... this is a very broad overview<br />
    ... slide 3 is more detailed on the first step<br />
    ... I want to introduce jargon so you know what it means<br />
    ... fpwd = first public working draft. We need a group
    decision. The chairs will make sure that the WG is ok with the
    draft and the slide describes what that means<br />
    ... then the director will make sure that this is in scope and
    then the publication will happen in the TR (technical report)
    space of the W3C website<br />
    ... FPWD is mostly a set of signals. First signal is that we're
    serious<br />
    ... Second signal is that we say what we're working on.<br />
    ... also a signal to other groups to show what we're
    working<br />
    ... these are horizontal reviews. Accessibility, privacy,
    security, etc<br />
    ... it's also an important steps for your lawyers. The charter
    sets a scope for the commitments</p>
    <p class='irc'>&lt;<cite>bajones</cite>&gt; +present</p>
    <p class='phone'><cite>scribe:</cite> this will give a
    opportunity for the IPR exclusion<br />
    ... the FPWD is the start of the exclusion process but we want
    to avoid any exclusions<br />
    ... FPWD doesn't mean that the spec is complete. It's the start
    game<br />
    ... you should aim the show the scope of the final spec<br />
    ... it doesn't mean that everybody is happy with the
    content<br />
    ... likely no everyone will be completely happy with the final
    spec<br />
    ... fpwd is a good signal what we mean with WebXR<br />
    ... slide 9 talks about editor's draft from the editors<br />
    ... Nell and Brandon are on top of this. We should have
    something at the end of the month<br />
    ... then we should have a call for consensus<br />
    ... aka a CFC<br />
    ... likely a github issue from the authors asking for
    objections/support<br />
    ... this will get us to FPWD<br />
    ... slide 10 will show what comes after that<br />
    ... part of it is getting in shape for review from other
    groups<br />
    ... webaudio, webrtc, sensor/device, etc<br />
    ... we want to get feedback from implementors. This will likely
    happen naturally<br />
    ... since most are in this group.<br />
    ... we also want to focus on testing once things
    stabilize<br />
    ... we want to check if the spec is implementable and is
    implemented<br />
    ... this is an overview of the short term and the next 12
    months<br />
    ... let me know of any questions now or over email</p>
    <p class='irc'>&lt;<cite>dom</cite>&gt; ScribeNick: dom</p>
    <p class='irc'>&lt;<cite>cabanier</cite>&gt; ada: thanks you so
    much</p>
    <p class='irc'>&lt;<cite>cabanier</cite>&gt; bajones: there's
    not a whole lot to report</p>
    <p class='phone'><cite>Brandon:</cite> reporting on editors
    draft next step<br />
    ... Brandon and I are working on it<br />
    ... Nell has limited availabilities due to upcoming re.Invent
    but helping reviewing my edits<br />
    ... we want to get the spec sync'd with the explainers<br />
    ... and fill gaps that haven't been fleshed out in the
    past<br />
    ... the FPWD is not going to cover everything we want to see in
    the API<br />
    ... we want to make sure the bones of session creation are
    present<br />
    ... this includes removal of WebXRDevice</p>
    <p class='irc'>&lt;<cite>scribe</cite>&gt; ... new session
    modes</p>
    <p class='phone'><cite>UNKNOWN_SPEAKER:</cite> and feature
    request<br />
    ... and making sure we describe the basics of the frame
    loop<br />
    ... some of the stuff around input and coordinates will not be
    finalized though<br />
    ... probably won't happen before December</p>
    <p class='phone'><cite>Nell:</cite> Brandon has been doing the
    gap analysis between spec &amp; explainer<br />
    ... some of the things will come after FPWD - e.g. hit
    testing<br />
    ... I'll be tackling the analysis around anchors, hit testing
    and migrate the results to the WebXR spec<br />
    ... I have tried to assign issues in the webxr repo to
    appropriate milestones<br />
    ... incl one milestone for our F2F in Jan<br />
    ... good place to look at our plans</p>
    <p class='phone'><cite>Brandon:</cite> beyond updating the spec
    prose<br />
    ... there are been discussions around teleportation
    mechanics<br />
    ... it has become apparent that there are certain bits of maths
    we can make easier for everybody<br />
    ... I've also been looking at the input story a little
    more<br />
    ... and features / permissions</p>
    <p class='phone'><a href=
    "https://github.com/immersive-web/webxr/milestone/6">Issues
    tagged for FPWD milestone</a></p>
    <p class='phone'><cite>Ada:</cite> re January F2F - I'll get
    details for that out soon<br />
    ... trying to get logistical informations from host</p>
    <h3 id="item02">Define how to request features which require
    user consent</h3>
    <p class='phone'><a href=
    "https://github.com/immersive-web/webxr/issues/424">Define how
    to request features which require user consent #424</a></p>
    <p class='phone'><cite>Brandon:</cite> will bundle with #423 as
    well</p>
    <p class='phone'><a href=
    "https://github.com/immersive-web/webxr/issues/423">Allow
    session creation to be blocked on required features
    #423</a></p>
    <p class='irc'>&lt;<cite>ada</cite>&gt; Open PR: <a href=
    "https://github.com/immersive-web/webxr/issues/433">https://github.com/immersive-web/webxr/issues/433</a></p>
    <p class='phone'><a href=
    "https://github.com/immersive-web/webxr/pull/433">Added session
    feature handling to the explainer. #433</a></p>
    <p class='phone'><cite>Brandon:</cite> I've been trying to
    distinguish features I want vs features I need (ones where the
    only fallback is session failure)<br />
    ... we want to avoid dictionary keys for required features -
    most browsers don't have mechanics to iterate through
    dictionary keys and reject on unrecognized ones<br />
    ... it's feature for "ignore-unknown" extensibility<br />
    ... but as a result, to list required features in that way, you
    first have to check with the browsers which of the required
    features it knows about<br />
    ... getUserMedia does it this way<br />
    ... what we have landed on is list of string enums for
    "desired" and "required" features<br />
    ... any symbol that is not recognized in "required" will cause
    failure<br />
    ... whereas for "desired" features, the experience can fallback
    on progressive enhancement<br />
    ... We would have to use strings rather than an enum to avoid
    the fallback case on "desired", per WebIDL<br />
    ... the exact prompt of bundled permissions is left to
    implementors<br />
    ... also room for requesting additional "desired" features once
    the session has been created<br />
    ... where we're at is pretty simple, but took a lot of
    reasoning based on how specs are expected to work, what is
    WebIDL-compatible, etc<br />
    ... it's been tricky to navigate<br />
    ... not set in stone yet<br />
    ... feeling pretty good about the proposal and would like to
    include in FPWD</p>
    <p class='phone'><cite>Ada:</cite> wondering what happens in
    the event of the developer is asking for "whatever you can
    get"<br />
    ... to give the user an option to pick among the different
    modes a device support</p>
    <p class='phone'><cite>Brandon:</cite> the distinction between
    VR &amp; AR is not covered in this proposal<br />
    ... it would be handled at the session creation via session
    modes<br />
    ... if you want to offer the AR vs VR choices, you would query
    the supported modes and present that in a user selector<br />
    ... If you request an AR session with environment mapping, all
    the bells and whistles, etc<br />
    ... there won't be a mode to ask for everything<br />
    ... for the following reasons:<br />
    ... * if you don't know about a feature, you can't possible use
    it<br />
    ... we want to make sure the devs asks as little as they
    need<br />
    ... * there will new features coming in over time<br />
    ... * some features may be mutually exclusive</p>
    <h3 id="item03">The Great Bikeshedding II: XRFrameOfReference
    and XRCoordinateSystem</h3>
    <p class='phone'><a href=
    "https://github.com/immersive-web/webxr/issues/418">The Great
    Bikeshedding II: XRFrameOfReference and XRCoordinateSystem
    #418</a></p>
    <p class='phone'><cite>Nell:</cite> no one has chimed in - if
    nobody does, I'll just do something on my own<br />
    ... is anyone from Mozilla around today?</p>
    <p class='phone'>[crickets]</p>
    <p class='phone'><cite>Nell:</cite> this conversation can
    either become unending, or nobody speaks up and I just make it
    up on my own<br />
    ... I'm interested to hear better name suggestions, possible
    risks for confusions<br />
    ... e.g. mismatches or conflicts with native APIs<br />
    ... I suggested XRFrameOfReference -&gt; XRStage and
    XRCoordinateSystem -&gt; XRSpatialRoot<br />
    ... any reaction?</p>
    <p class='phone'><cite>Brandon:</cite> I've typed
    XRFrameOfReference and XRCoordinateSystem a lot - they're long,
    ungainly, hard to type</p>
    <p class='irc'>&lt;<cite>alexturn</cite>&gt; +present</p>
    <p class='phone'><cite>Brandon:</cite> we need better, shorter
    names<br />
    ... I have opinions which I've shared with Nell, but would like
    to hear from other vendors</p>
    <p class='phone'><cite>AlexT:</cite> my primary concern for
    SpatialRoot vs CoordinateSystem<br />
    ... having Root used on something that would not be the base
    would be awkward</p>
    <p class='phone'><cite>Nell:</cite> I documented the intent
    behind that choice<br />
    ... DOM is a tree with one root, with children<br />
    ... in a scene, each frame of reference creates a tree of
    objects independent from the others<br />
    ... thus these frames of references are roots of these
    independent trees<br />
    ... curious about reactions to that intent</p>
    <p class='irc'>&lt;<cite>Leonard</cite>&gt; : I guess the main
    point is "root" is root-local to the user, not to the world or
    anyone else.</p>
    <p class='phone'><cite>Alex:</cite> still needs to build my
    mental model around it; I get where you're coming from<br />
    ... a question of "is" vs "has"</p>
    <p class='phone'><cite>Brandon:</cite> going back to what Nell
    said earlier, relating to the fundamental model of the Web in
    the DOM tree<br />
    ... there will be a tendency to compare what we have with
    it<br />
    ... we have these frame of references and coordinate
    systems<br />
    ... frame of reference is or has a coordinate system<br />
    ... one is like an element, the other is like document<br />
    ... anchors and other items looks more like leaves of the DOM
    tree<br />
    ... I think a lot of developers will see the frame of reference
    as a root</p>
    <p class='phone'><cite>Nell:</cite> that's fair - my worry is
    people assuming a static relation between frame of reference
    and coordinate system<br />
    ... maybe SpatialNode instead of CoordinateSystem<br />
    ... I'm hesitant to use Root for the Stage<br />
    ... ultimately it doesn't matter - coordinate systems are not
    children<br />
    ... they can be related to different frame of references<br />
    ... I don't want to imply a hierarchy that doesn't exist</p>
    <p class='phone'><cite>Brandon:</cite> it's a matter at
    comparing how these works in the back-end and how people will
    end up using them<br />
    ... even in the DOM, you can move elements from one tree to
    another (e.g. to an iframe)<br />
    ... this is one space where we might benefit from OpenXR
    experience<br />
    ... not sure how much of it is public atm</p>
    <p class='irc'>&lt;<cite>Zakim</cite>&gt; Leonard, you wanted
    to say I guess the main point is "root" is root-local to the
    user, not to the world or anyone else.</p>
    <p class='phone'><cite>Leonard:</cite> the coordinate system is
    local to the user - calling it root in the context of the user
    is not going to be an issue</p>
    <p class='phone'><cite>nell:</cite> not sure I follow</p>
    <p class='phone'><cite>Leonard:</cite> I'm agreeing with
    you</p>
    <p class='phone'><cite>Nell:</cite> we've talked about
    coordinatesystem, not much about frameofreference which is the
    more appalling term</p>
    <p class='phone'><cite>alexT:</cite> I'm thinking of them
    together<br />
    ... OpenXR has hand coordinate system and head coordinate
    system<br />
    ... you could still call them root, but they're not locked in
    space<br />
    ... this goes back to the is-a vs has-a - this impacts which of
    the names ring right</p>
    <p class='phone'><cite>nell:</cite> we need proposals</p>
    <p class='phone'><cite>alexT:</cite> agree - but it needs to be
    considered holistically on the set of related names</p>
    <p class='phone'><cite>Brandon:</cite> I think we would be open
    to move from "is-a" to "has-a" if we find a good set of
    names</p>
    <p class='phone'><cite>Nell:</cite> I want 3 name proposal from
    you alexT, posted on the issue</p>
    <p class='phone'><cite>AlexT:</cite> [Challenge Accepted]<br />
    ... will post a really bad one to trigger reactions</p>
    <p class='phone'><cite>Ada:</cite> there are no bad ideas</p>
    <h3 id="item04">AOB</h3>
    <p class='phone'><cite>Ada:</cite> we'll get mail out soon on
    the F2F</p>
    <p class='irc'>&lt;<cite>LocMDao</cite>&gt; Thank you for
    having us</p>
    <p class='phone'><cite>Ada:</cite> looking forward to the next
    call</p>
  </div>
  <h2><a name="ActionSummary" id="ActionSummary">Summary of Action
  Items</a></h2><!-- Action Items -->
  <h2><a name="ResolutionSummary" id="ResolutionSummary">Summary of
  Resolutions</a></h2><!-- Resolutions -->
  [End of minutes]<br />
  <hr />
  <address>
    Minutes manually created (not a transcript), formatted by David
    Booth's <a href=
    "http://dev.w3.org/cvsweb/~checkout~/2002/scribe/scribedoc.htm">
    scribe.perl</a> version 1.154 (<a href=
    "http://dev.w3.org/cvsweb/2002/scribe/">CVS log</a>)<br />
    $Date: 2018/11/13 19:03:18 $
  </address>
