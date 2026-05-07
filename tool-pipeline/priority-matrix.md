# Priority Matrix — Tool Scoring System

Score every proposed tool on five criteria (each 0-10). Total = priority rank. Higher score = build sooner.

---

## Scoring Criteria

### 1. Search Volume (SV) — ×1 weight
How many people search for this tool's primary keyword monthly?

| Score | US Monthly Searches | Description |
|-------|-------------------|-------------|
| 0 | 0 | No search volume |
| 1-2 | 10–100 | Very low |
| 3-4 | 100–1K | Low but present |
| 5-6 | 1K–5K | Decent traffic potential |
| 7-8 | 5K–20K | Strong demand |
| 9-10 | 20K+ | High-volume opportunity |

### 2. Competition — ×1 weight (inverted)
Lower competition = higher score.

| Score | Competition Level | Keyword Difficulty |
|-------|------------------|-------------------|
| 10 | Very low | 0–14 |
| 8-9 | Low | 15–29 |
| 6-7 | Moderate-low | 30–44 |
| 4-5 | Moderate | 45–59 |
| 2-3 | High | 60–79 |
| 0-1 | Very high | 80–100 |

*Source: Google Keyword Planner, Ahrefs, Semrush, or similar.*

### 3. Build Effort — ×1 weight (inverted)
Less effort = higher score. We want quick wins.

| Score | Effort (hours) | Complexity |
|-------|---------------|------------|
| 10 | < 2 | Copy-paste formula, no dependencies |
| 8-9 | 2–4 | Simple logic, 1 dependency |
| 6-7 | 4–8 | Medium complexity, data needed |
| 4-5 | 8–16 | More complex, API integration |
| 2-3 | 16–40 | Significant build, multiple APIs |
| 0-1 | 40+ | Full project, database, auth |

### 4. Monetization Potential — ×1 weight
How well can this tool be monetized with AdSense?

| Score | AdSense Fit | Est. RPM | Notes |
|-------|------------|----------|-------|
| 10 | Excellent | $15-30+ | High-intent, commercial keywords |
| 8-9 | Very good | $10-15 | Good intent, sticky users |
| 6-7 | Good | $5-10 | Decent page views per session |
| 4-5 | Fair | $2-5 | Low RPM but volume helps |
| 2-3 | Poor | $0.50-2 | Low-intent, high bounce |
| 0-1 | Very poor | < $0.50 | Ad policy risk or no placement |

### 5. SEO Fit — ×1 weight
Can we realistically rank for this tool's target keywords?

| Score | Ranking Potential | Criteria |
|-------|------------------|----------|
| 10 | Guaranteed top 3 | No strong competitors, perfect domain fit |
| 8-9 | Very likely top 5 | Weak competition, we have authority |
| 6-7 | Likely top 10 | Moderate competition, good content gap |
| 4-5 | Possible top 20 | Competitive, but long-tail angles exist |
| 2-3 | Unlikely | Strong incumbents, high DA sites |
| 0-1 | Very unlikely | Dominated by giants, no unique angle |

---

## Calculation

```
Total Score = SV(0-10) + Competition_inverted(0-10) + BuildEffort_inverted(0-10) + Monetization(0-10) + SEO_Fit(0-10)
```

**Maximum possible:** 50
**Minimum threshold for APPROVE:** ≥ 25 (unless strategic override)

---

## Priority Tiers

| Total Score | Priority | Action |
|-------------|----------|--------|
| 40–50 | 🔥 **Critical** | Build immediately. Top of backlog. |
| 30–39 | ⚡ **High** | Build this sprint (next 48h). |
| 25–29 | ✅ **Medium** | Good candidate. Queue after high-priority. |
| 20–24 | ⏳ **Low** | Hold. Re-evaluate monthly. |
| 10–19 | 📦 **Backlog** | Archive unless strategic override. |
| 0–9 | 🚫 **Skip** | Do not build. Document why. |

---

## Strategic Override

If a tool scores < 25 but has strong strategic value — fills a category gap, enables cross-linking, or is requested by Bishal — it can be overridden. Document the override reason explicitly.

```
Strategic Override: YES / NO
Reason: 
```

---

## Quick Reference

```
                    LOW ←──────────────→ HIGH
Search Volume        0  1  2  3  4  5  6  7  8  9  10
Competition (inv)   10  9  8  7  6  5  4  3  2  1  0
Build Effort (inv)  10  9  8  7  6  5  4  3  2  1  0
Monetization         0  1  2  3  4  5  6  7  8  9  10
SEO Fit              0  1  2  3  4  5  6  7  8  9  10
```

**Threshold for immediate build: ≥ 30**
**Threshold for queue: ≥ 25**
**Everything else: hold or skip**
