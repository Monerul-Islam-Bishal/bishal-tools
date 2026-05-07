# COO Review Pipeline — Tool Ideas

## Overview

End-to-end workflow for taking tool ideas from research to production. Every tool passes through six stages with clear gates, owners, and handoff criteria.

---

## Pipeline Stages

### Stage 1: Idea Generation
**Owner:** Research Agent
**Input:** Market trends, keyword gaps, competitor analysis
**Output:** Completed `tool-proposal-template.md` with SEO data

**Checklist:**
- [ ] Search volume data (US monthly)
- [ ] Competition level (low/medium/high)
- [ ] Existing similar tools ranked
- [ ] Keyword difficulty score
- [ ] Related long-tail keyword opportunities
- [ ] Build effort estimate (hours)

**Gate:** Proposal must have all SEO fields filled before passing to COO.

---

### Stage 2: COO Review
**Owner:** COO Agent (me)
**Input:** Tool proposal from Stage 1
**Output:** Proposal with COO recommendation + priority score

**Review Criteria:**
1. **Market demand** — Does search volume justify the effort?
2. **Build complexity** — Can we ship this fast? (under 8h ideal)
3. **Monetization fit** — Will AdSense placement make sense?
4. **SEO potential** — Can we realistically rank on page 1?
5. **Strategic fit** — Does this grow our tool ecosystem?

**Checklist:**
- [ ] Priority score calculated (see priority-matrix.md)
- [ ] Business value assessed
- [ ] Risks documented
- [ ] COO recommendation set: APPROVE / HOLD / SKIP

**Gate:** Only APPROVED proposals proceed. HOLD proposals get re-reviewed weekly. SKIP proposals archived with reason.

---

### Stage 3: Bishal Approval
**Owner:** Bishal
**Input:** COO-reviewed proposal with recommendation
**Output:** Decision (Yes / No / Revise)

**Presentation format:**
- One-pager summary per proposal
- Benefits vs. risks clearly stated
- Effort estimate and revenue projection
- Linked priority-matrix score for context

**Gate:** Bishal's approval is final. Revise requests go back to Stage 2.

---

### Stage 4: Development
**Owner:** Developer Agent
**Input:** Approved tool proposal
**Output:** Working tool page with tests passing

**Deliverables:**
- [ ] Tool page built (Next.js or HTML/JS)
- [ ] Schema.org markup added
- [ ] Basic SEO meta tags set
- [ ] AdSense slots placed
- [ ] Mobile responsive
- [ ] Core Web Vitals pass (lighthouse)
- [ ] README updated

**Gate:** Developer opens a PR/pushes to staging. All items above must be checked.

---

### Stage 5: QA
**Owner:** QA Agent
**Input:** Staging URL + completed proposal
**Output:** QA sign-off or bug report

**QA Checklist:**
- [ ] Tool works correctly (happy path + edge cases)
- [ ] Mobile layout looks good (all breakpoints)
- [ ] AdSense ads render (test mode)
- [ ] Meta tags render correctly
- [ ] No broken links / console errors
- [ ] Lighthouse scores ≥ 80 all categories
- [ ] Schema markup valid (Google Rich Results test)

**Gate:** Pass or fail. Failed items go back to Stage 4 with specific bugs.

---

### Stage 6: Deploy
**Owner:** Deploy Agent / Sitemap Agent
**Input:** QA-signed-off tool
**Output:** Live tool page + updated sitemap

**Checklist:**
- [ ] Deploy to production
- [ ] Sitemap.xml regenerated with new tool URL
- [ ] Sitemap submitted to Google Search Console
- [ ] Internal tool directory updated (if applicable)
- [ ] Tool added to analytics tracking
- [ ] Post-deployment smoke test

**Final:** Tool is live. Move proposal to `archive/` with deployment date.

---

## Pipeline Flow Diagram

```
Idea Gen → COO Review → Bishal Approves → Development → QA → Deploy
   │            │              │               │        │        │
   └──→ data ───┘              │               │        │        │
                   ←── revise ─┘               │        │        │
                                     ←── bugs ──┘        │
                                                         └── sitemap ──→ Live
```

## Escalation

- **Blocked at any stage** → Notify COO (me) within 24h
- **Proposal rejected at Stage 3** → Archive with reason, move on
- **QA fails twice** → COO review to decide: fix or kill
- **AdSense issues** → Pause deployment, flag to Bishal

## Success Metrics

- **Cycle time:** < 48h from proposal → deploy for simple tools
- **Approval rate:** ≥ 50% of proposed tools get built
- **Quality:** 0 critical bugs reaching production
- **SEO wins:** ≥ 3 tools in top 10 search results within 90 days
