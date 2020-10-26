Title: **HYP-0001: Proposals**

Short Name: `0001-proposals`

Type: Standard

Status: Draft (as of 2020-10-26)

Github PR:

Authors: Paul Frazee

# Summary
[summary]: #summary

The Hypercore Proposal ("HYP") process is how the Hypercore community reaches consensus around technical protocol enhancements and organizational process.

# Motivation
[motivation]: #motivation

The Hypercore protocol is still a living standard. A transparent process is needed for community members to understand what changes are in the pipeline and how new ideas might come to fruition. HYPs are a processes for proposing changes and codifying implementations of the Hypercore Protocol.


# How To Submit a Proposal
[submit]: #submit

As a first step, before drafting a HYP or implementing experimental new
protocol features, it's helpful to informally pitch your idea to see if others
in the community are already thinking something similar, or have discussed the
same idea in the past. This discussion could happen over chat, Github issues,
blog posts, or other channels. If you can recruit collaborators and work out
some of the details, all the better.

Once your idea has been flushed out, the process for proposing and debating a
new HYP is:

1. Use git to fork the [hypercore-protocol/hyp](https://github.com/hypercore-protocol/hyp)
   repository
1. Copy `0000-template.md` to `proposals/0000-my-proposal.md` (don't choose the
   "next" number, use zero; `my-proposal` should be a stub identifier for the
   proposal.)
1. Fill in the HYP template. All proposals should have a Type and Status (see
   below for details). Feel free to tweak or expand the structure (headers,
   content) of the document to fit your needs, but your proposal should be
   "complete" before submission.
1. You can create an informal WIP (work in progress) PR (pull-request)
   whenever you like for early feedback and discussion, but there is no
   expectation that your proposal will be given detailed review until it is
   complete.
1. When you are ready, submit your complete proposal for review (this could be
   opening a PR or removing WIP status from an existing one), with the intent
   of being accepted with "Draft" status.
   An editor (somebody who is an owner of the HYPs repository) will look over
   your proposal for completeness; if acceptable, they will assign one or more
   reviewers.
   At this stage, two outcomes are the most likely: your proposal
   is merged with "Draft" status, or declined.  The submitter can withdraw a
   proposal at any time. If accepted, an HYp number will be assigned and the PR
   merged. If declined, reviewers may give feedback and/or invite proposers to
   "significantly revise and resubmit".
1. While in draft status, proposals can be experimented with. Small corrections
   and clarifications can be submitted by PR expect to be merged quickly if
   they are reasonable and don't change the broad behavior or semantics of the
   proposal; larger changes should be re-submitted as Superseding proposals.
1. When it seems appropriate, a PR can be submitted to upgrade the status of a
   "Draft" to "Active". At this time a final review will take place, with the
   outcome being that a proposal stays "Draft" or becomes "Active".
   Small changes to the HYP can be included, but it's expected that
   this is in broad strokes the same proposal that was reviewed earlier (if
   not, a new "Draft" should be proposed that Supersedes).
1. Small tweaks (grammar, clarifications) to a merged HYP can take place as
   regular Github PRs; revisiting or significantly revising should take place
   as a new HYP. Draft, Process, and Informational HYPs have a lower bar for
   evolution over time via direct PR.

# Details
[reference-documentation]: #reference-documentation

## Types and Statuses
[types]: #types

HYPs should have a type:

* **Standard** for technical changes to the protocol, on-disk formats, or
  public APIs. These are intended to be *prescriptive*, and to clearly
  delineate which features and behaviors are mandatory or optional.
* **Process** for formalizing community processes or other (technical or
  non-technical) decisions. For example, a security vulnerability reporting
  policy, a process for handling conflicts of interest, or procedures for
  mentoring new developers.
* **Informative** for describing conventions, design patterns, existing norms,
  special considerations, etc.

The status of a HYP can be:

* **Pre-Merge**: a well-formed HYP has been written and a PR opened. The
  "Status" line can list Draft when in this state.
* **Draft**: PR has been merged and a number assigned, but additional time is
  needed for deeper discussion or more implementation before being "normative"
  and expected for implementation. It is acceptable to have "competing"
  proposals in this state at the same time.
* **Active**: adopted or intended for implementation in mainline libraries and
  clients as appropriate. Again, HYPs should clarify which aspects of
  themselves are optional or required for well-behaved clients.
* **Closed**: either consensus was against, a decision was postponed, or the
  authors withdrew their proposal. This could apply to any of: a proposal PR
  that was never merged, a merged Draft (which was never Active), or an Active
  HYP which there is now consensus against without a specific new HYP to
  replace it.
* **Superseded**: a formerly Active HYP has been made obsolete by a new
  Active HYP; the new HYP should specify specific old HYPs that it would
  supersede.

## Content and Structure
[content]: #content

A changelog should be kept in the HYP itself giving the date of any changes of
status.

A template file is provided, but sections can be added or removed as
appropriate for a specific HYP.

The HYP text itself should be permissively licensed; the convention is to use
the Creative Commons Attribution License (CC-BY), with attribution to the major
contributing authors listed.

For appropriate HYPs (including *all* Standards HYPs), authors should
explicitly consider and note impacts on:

* Privacy and User Rights. Consider reading IETF [RFC 6973] ("Privacy
  Considerations for Internet Protocols") and [RFC 8280] ("Research into Human
  Rights Protocol Considerations".)
* Backwards compatibility of on-disk archives and older network clients. If a
  backwards-incompatible change is proposed, a migration plan should be
  sketched out in the proposal.
* Security.

[RFC-6973]: https://tools.ietf.org/html/rfc6973
[RFC-8280]: https://tools.ietf.org/html/rfc8280


## Acceptance Criteria
[criteria]: #criteria

The criteria for a proposal being accepted as a Draft are, at a minimum, that
the proposal is complete, understandable, unambiguous, and relevant. There is a
good faith assumption that the submitter believes that the proposal could
actually be adopted and put to beneficial use. An editor may screen proposals
before passing on to the group for review.

For Standards and Process HYPs, Draft proposals should be specific enough that
they can be prototyped and experimented with (e.g. in a pilot program or test
network), but it isn't expected that all details have been worked out. Working
code is helpful but not required.

For a Draft to migrate to Active, there is an expectation that the proposal has
been demonstrated (e.g. in working code, though not necessarily in "official"
libraries yet), that the proposal will be the "new normal" and expected
behavior going forward, and that the chance of unforeseen issues arising during
complete adoption is low.


## Decision Making Process
[power]: #power

There exists a Protocol Working Group (WG) which makes HYP status
decisions; see the Github repository for a list of current members and the
governance process. At time of writing, the WG has only one member, Mathias
Buus, the creator of the Hypercore Protocol. The process outlined here includes
the tools for decision-making as the WG is expanded to include more members.

By no means should working group members be the only people reviewing or giving
feedback on proposals.

When deciding on Draft status, at least one WG member must review the entire
proposal in detail, give feedback, and give informed approval. If no detailed
review takes place in the fixed time window, the default is to close (reject)
until a member is willing to commit to review. Any WG member can request
revisions or clarifications (blocking acceptance until addressed), and any
member can block. In other words, consensus requires that at least one member
actively approve, and any member can block, but it isn't required to have every
member review and actively given an opinion. This is referred to as the "loose
consensus" model.

For Active status, the expectation is that all working group members will
review the proposal and actively participate in consensus. In the event that
not all members can participate, the default is again negative. Any member can
block. This is referred to as the "complete consensus" model.

For all other status changes, at least one WG member must vouch for or approve
the change ("loose consensus"). If there is unambiguous consensus (or, eg, a
HYP is documenting already adopted practice), a HYP can move directly to Active
status (following the "complete consensus" process).

In all cases, if there is a deadlock (a block can not be overcome after
further discussion), there is an option to override the block by a vote. The
details of this process are left to description in the Working Group
repository, and are expected to be used only in exceptional cases (eg, are not
invoked by default if a member blocks).

Proposals are expected to be open for at least three days (72 hours) for
comment (and longer to accommodate special circumstances, like holidays). Vetoes
(blocks) can happen up to a week after initially being submitted for review,
which might be retroactive if the proposal was accepted (by other WG members)
very quickly.

# Background and References
[references]: #references

The following standards processes were referenced and considered while
designing the HYP process:

* **Dat Enhancement Process** as described in [DEP 1][dep-1]. The DEP process
  governed changes to the Dat protocol, which was the former name of the
  Hypercore Protocol. The HYP process is strongly informed by the DEP process
  and takes the bulk of its design from DEP-1. In practice, the DEP struggled
  with active participation from WG members over a long period, and was
  difficult for core engineers to maintain as large updates were still being
  explored and developed for the technology. The HYP process reduces the
  initial overhead of DEPs by reducing the initial WG members to one, the
  protocol lead, while still allowing for additional WG members to be added.
  The goal is to fit the current capacity of the protocol development
  participants while still providing a clear pathway for outside contribution
  and the provision for expanded governance in the future. It might be
  described as "BDFL" governance with a pathway to WG governance.
* **BitTorrent Enhancement Process** as described in [BEP 1][bep-1]. The
  Bittorrent protocol has a lot of technical similarities to Hyper, and as a
  single protocol family (not a language or full-stack system) is one of the
  most similar in scope. The de facto BEP model is that Drafts are very stable
  and widely adopted; only the most universal core components are Final. The
  HYP process bases it's type categories on the BEP process. There is a single
  editor and an explicit BDFL in the BEP process.
* The **[Rust Language RFC Process][rust-rfc]** is relatively new, but has had
  a huge volume of proposals, rivaling even the IETF. The process is relatively
  lightweight and happens entirely on Github; it is the most similar to the HYP
  process proposed here, in terms of Draft/Active distinction. Rust has strong
  organizational backing with defined leadership roles; proposals are reviewed
  by specific sub-teams.
* **[IETF RFC Process][ietf]**: perhaps the oldest and best known RFC process,
  under the motto of "rough consensus and working code". The process is very
  bespoke (involving custom file formats and software) and heavy on process
  (with working groups and in-person meetings).
* **[XMPP Standards Process][xmpp]**: has the interesting sub-pattern of
  regularly updated (annual) standards. XMPP is also a protocol, like
  Bittorrent. The protocol was designed for easy extension, and at various
  points has seen adoption, extension, and pressure from powerful entities.
* **Python Enhancement Process** documented in [PEP 1][pep-1]. PEPs are
  relatively broad in scope (they often speak to process and organizational
  dynamics), and are widely cited directly by name. Proposals are usually
  debated in great detail on mailing lists before being proposed. Python has a
  BDFL (benevolent dictator for life) who has final say over proposals, though
  he sometimes delegates to deputies.
* The **W3C** is a paid membership organization which, like the IETF, is made
  up of entities large and small, for-profit and altruistic, with decent
  regional diversity. W3C standards are often rather large and verbose
  documents, and tend to tail (rather than lead) implementation.


[dep-1]: https://github.com/datprotocol/DEPs/blob/master/proposals/0001-dep-process.md
[bep-1]: http://bittorrent.org/beps/bep_0001.html
[rust-rfc]: https://github.com/rust-lang/rfcs
[xmpp]: https://xmpp.org/about/standards-process.html
[ietf]: https://www.ietf.org/about/process-docs.html
[pep-1]: https://www.python.org/dev/peps/pep-0001/


# Unresolved questions
[unresolved]: #unresolved-questions

How mutable should "Draft" Standards HYPs be over time? What about
Informational HYPs? Should there be an additional status ("Living"?) for HYPs
that are expected to evolve, or is this against the whole philosophy of having
specific stable documents to reference? This is expected to be clarified while
this HYP itself is in Draft status.

Does "Active" status mean that implementation is *mandatory*, and that features
*must* be implemented unless they are explicitly optional? How would this
expectation be enforced for third-party software? This is expected to be
clarified when concrete examples arise.


# Changelog
[changelog]: #changelog

- 2020-10-26: First complete draft submitted provisionally
