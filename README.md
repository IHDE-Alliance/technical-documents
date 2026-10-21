# IHDEA Technical Documents

This repository holds the formal technical documents of the
[International Heliophysics Data Environment Alliance (IHDEA)](https://ihdea.net):
Notes, Recommendations, and Standards covering data formats, metadata models,
semantic artifacts, service interfaces, software practices, and resource sharing
across heliophysics data providers.

Accepted Recommendations and Standards are also published, with DOIs, to the
[IHDEA Technical Documents community on Zenodo](https://zenodo.org/communities/idhea-tech-docs/),
and all accepted documents are listed on the documents page of
[ihdea.net](https://ihdea.net).

The rules summarized here are defined in full in the **IHDEA Standards Process**
document (`STD-Standards-Process`). If this README and that document disagree,
the Standards Process document governs.

## Document levels

Every document in this repository has one of three maturity levels. Each level
says how much authority an implementer can attach to it.

| Level | Type code | Required implementers | What it means |
| :---- | :-------- | :-------------------- | :------------ |
| **Note** | `NOTE` | None | A dated, public record of an idea, proposal, practice, or background material. No consensus, endorsement, or technical review is implied. Not normative. |
| **Recommendation** | `REC` | 2 IHDEA member organizations | A specification or guideline that its authors and an IHDEA working group consider technically sound and ready for broader use. |
| **Standard** | `STD` | ≥ 50% of IHDEA member organizations | The final, stable form of a document, approved by the IHDEA Executive Committee. The only level that may be cited as a normative IHDEA reference. |

An IHDEA member organization is any organization with representation on the
IHDEA Executive Committee (see [ihdea.net](https://ihdea.net) for the list).

Documents advance one level at a time: Note → Recommendation → Standard. Not
every document is expected to advance. A Recommendation or Standard may be
demoted by one level if it no longer meets its implementation threshold; Notes
are never demoted.

## File naming and versioning

Each document name has four hyphen-separated parts:

```
<TYPE>-<ConciseName>-<I.J>-<YYYYMMDD>
```

- **TYPE**: `NOTE`, `REC`, or `STD`
- **ConciseName**: a short condensation of the title, no spaces (hyphens or CamelCase)
- **I.J**: version number
  - `I` (major) is `0` during internal development, becomes `1` at first
    publication as a Recommendation, and increments for any change that breaks
    backward compatibility or requires substantial rework by implementers.
  - `J` (minor) increments for substantive, backward-compatible changes. It
    normally stays fixed when a Recommendation is promoted to a Standard.
- **YYYYMMDD**: the date that version was produced. Errata change only the date.

Example progression:

```
NOTE-ExampleTopic-1.0-20260115.pdf    initial idea
REC-ExampleSpec-0.1-20260201.pdf      early internal draft
REC-ExampleSpec-1.0-20260301.pdf      published for review
REC-ExampleSpec-1.1-20260401.pdf      non-breaking revision
REC-ExampleSpec-2.0-20260501.pdf      breaking revision
STD-ExampleSpec-1.0-...pdf            approved as Standard
```

The Document Coordinator may adjust names for consistency with this convention.

## File formats

Every document must be submitted in **both** of these forms:

1. **PDF**: the published document of record.
2. **An editable source** (Markdown, HTML5, or a Word-type document) kept
   alongside the PDF so future editors can revise it. Plain text is not
   acceptable.

Use the IHDEA technical document template where possible. Every document must
include the required template elements: title page with document type, DOI,
title, authors (with ORCiDs), contact email, abstract, status history, and
(for Recommendations and Standards) the relevant IHDEA working group and the
member organizations that implement it. See Appendix A of the Standards Process
document for the full outline.

## License

All documents in this repository are published under the
[Creative Commons Attribution 4.0 International license (CC BY 4.0)](LICENSE.txt).
By submitting a document you grant IHDEA and the public a perpetual, worldwide,
royalty-free license to reproduce, distribute, and adapt it with attribution.
Authors keep their copyright and confirm they have the right to contribute the
work, including any permission needed from their home organization.

Reference implementations, example code, and schemas offered as evidence of
implementation should, where possible, be published under an OSI-approved open
source license (e.g. Apache-2.0, BSD-3-Clause, MIT) in a public repository, with
a persistent identifier cited in the document. Authors must disclose any known
patent claims or other IP encumbrances when they submit.

## How to contribute

> **Only approved documents go in this repository.** Draft and edit your
> document elsewhere (e.g. Google Docs or your own GitHub repository) and open a
> pull request here only when the step below calls for it.

All submissions get a non-technical review by the Document Coordinator
(relevance to IHDEA, grammar and style, working links, contact details, and
template compliance), with a target turnaround of 10 business days.

### Submitting a Note

1. The primary author must belong to an IHDEA member organization.
2. Open a pull request adding the PDF and its editable source.
3. The Document Coordinator reviews it with you and merges it.

Revisions to Notes follow the same steps.

### Promoting a Note to a Recommendation

1. **Find a working group.** Get concurrence from one or more IHDEA working
   group (WG) leads that the document is relevant to their WG. If none fits, a
   new WG may be formed under the IHDEA bylaws.
2. **Draft with the WG.** Join the WG, revise the document with its members,
   and document at least **two** IHDEA member organizations with working
   implementations. Obtain WG approval (by the members, not only the leads) and
   record it in the document.
3. **Open review.** Open an [issue](../../issues) with a short description and a
   link to a commentable copy of the document. The review lasts at least one
   month; if no one outside the authors and the WG comments, extend it by a
   month. Authors and WG leads advertise the issue to all IHDEA WG leads. Note
   the end of the review at the top of the issue.
4. **Submit.** Increment the minor version and close commenting. Once the WG
   approves the final text, a WG lead opens a pull request that links the
   review issue and tags the author(s). After the non-technical review it is
   merged and a DOI is assigned.

### Promoting a Recommendation to a Standard

The Recommendation process applies, plus:

1. The document must list the member organizations implementing it
   (at least 50% of IHDEA member organizations).
2. A WG lead opens a pull request beginning with the line
   **"Vote needed by the IHDEA Executive Committee"**, followed by the title,
   abstract, and a link to the most recent open-review issue.
3. The Executive Committee confirms the 50% threshold (commented on the pull
   request), may request a presentation, and votes at its next meeting (target:
   within 60 calendar days of submission).
4. The vote result (percentage of each vote type, key comments, and
   passed/not passed) is posted on the pull request and added to the document.
5. If the vote passes, the pull request goes through the non-technical review
   and is merged. If it fails, the pull request is closed; authors may revise
   the Recommendation and resubmit.

A Standard cannot go to a vote while a disclosed IP encumbrance is unresolved.

### Revising a Recommendation or Standard

Present the change to the relevant WG, which decides with the authors whether it
is minor or major.

- **Minor** (backward compatible): WG approval after internal review, then a pull request.
- **Major** (breaking): start over through the full process, beginning as a Note.

### Errata

Typos, broken links, formatting, cross-references, grammar, and contact updates
that do not change technical content can be fixed without a vote:

1. Any IHDEA member opens a pull request labeled as an erratum, explaining why
   it does not change technical content, and tags the author(s) and WG lead(s).
2. The Document Coordinator confirms the change is non-substantive.
3. The document date is updated (version numbers unchanged), a one-line entry is
   added to its revision history, and the pull request is merged.

If the Document Coordinator judges the change substantive, it must go through
the revision process instead.

## Periodic review and demotion

- Each WG reviews its Recommendations and Standards every 2–5 years for needed
  revisions.
- The Executive Committee reviews selected Recommendations and Standards every
  2–5 years against their implementation thresholds. Documents that no longer
  qualify are demoted one level, and the Document Coordinator and WG leads move
  them and announce the change.

## Roles

| Role | Responsibilities |
| :--- | :--------------- |
| **Document Coordinator** | Appointed by the Executive Committee. Maintains this repository, performs non-technical review, confirms both PDF and editable source are present, and merges pull requests. |
| **WG Lead** | Confirms a document's relevance to the WG, schedules WG votes, checks acceptance criteria, and submits pull requests for Recommendations and Standards. |
| **WG Members** | Discuss technical details and vote on draft Recommendations. |
| **Executive Committee** | Votes on Standards, appoints the Document Coordinator, and periodically reviews documents. |
| **Executive Committee Chair** | Schedules Standard votes, reports results to the Document Coordinator, and notifies the newsletter maintainers of new or changed documents. |

## Questions

Open an [issue](../../issues) in this repository, or contact the IHDEA working
group leads listed on [ihdea.net](https://ihdea.net).
