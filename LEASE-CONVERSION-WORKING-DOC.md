# lease.luxuryproperty-southdakota.com — Lease Conversion Working Document

Started 2026-09-12. Brian's rule for this project: **one page at a time.**
Do not edit a page until Brian names it. Do not report findings from a page
he has not asked about.

---

## What this site is

A separate lease site for 2111 Vantage Circle, Spearfish, South Dakota. It was
created 2026-09-12 as a copy of the for-sale site, with the CNAME repointed. All
content is currently sale copy and is being converted page by page.

- **Live at:** http://lease.luxuryproperty-southdakota.com (HTTP only, see Infrastructure)
- **Repo:** briandemsey/luxuryproperty-southdakota-lease
- **Local:** F:\luxuryproperty-southdakota-lease
- **Host:** GitHub Pages, branch `main`, auto-deploys on push
- **Sibling sites:** luxuryproperty-southdakota.com (sale), the-campus., design-build.

---

## Working method

1. Brian names the page.
2. Read that page's markup.
3. Make only the change he specifies.
4. Verify: `git diff`, then poll the live URL until the new text is served.
5. Commit and push only when he says push.
6. Record the result here.

Verification means measuring the live page, not assuming the deploy worked.
Pages builds take roughly 35 seconds; the CDN then needs a cache-busted fetch.

---

## Page status

Section-by-section pass **complete** 2026-09-12. All fourteen sections plus the
hero were named and resolved by Brian.

| # | Page / view | `data-view` | Status |
|---|---|---|---|
| — | Hero | `hero` | Converted, `dd22615` |
| — | Contents (TOC) | `contents` | Reviewed, not edited |
| I | The Offering | `offering` | Converted, `8565a0a` + `15e0729` |
| II | Provenance | `provenance` | Reviewed, no change |
| III | The House | `house` | Converted, `a2c64e0` |
| IV | Drawings | `drawings` | Converted, `39e22d0` |
| V | Personal Photography | `photography` | Converted, `15e0729` |
| VI | The Site | `site` | Converted, `b2f9e5a` |
| VII | The Opportunity | `opportunity` | Converted, `b2f9e5a` (lease rate set) |
| VIII | Inquire | `inquire` | Reviewed, no change |
| IX | Directions | `directions` | Reviewed, no change |
| X | Sotheby's Imagery | `representation` | Converted, `cdeb1ea` |
| XI | Professional Photography | `professional-photography` | Reviewed, no change |
| XII | Livestream | `livestream` | Reviewed, no change |
| XIII | Cinematic Reel | `cinematic-reel` | Reviewed, no change |
| XIV | Brochures | `brochures` | Converted, `cdeb1ea` |
| — | `<head>` metadata | — | Not started, not yet named |
| — | live.html | — | Not started, not yet named |

**Not yet done:** the end-of-pass reconciliation review Brian described
("you can review at the end for inconsistencies"). Wait for him to ask for it.
Known parked items are listed below under Remaining sale language.

---

## Completed

### Hero — 2026-09-12, commit `dd22615`

`index.html:92`

```
- <div class="hero-eyebrow">A Private Offering</div>
+ <div class="hero-eyebrow">A Private Lease</div>
```

Verified live: hero eyebrow serves "A Private Lease", "A Private Offering"
count 0. Build completed clean in 35s.

Left untouched on this page per instruction: hero body copy at line 219.

### Section I overview sentence — 2026-09-12, commit `8565a0a`

`index.html:219`

```
- It is offered furnished, in full, to a single qualified buyer.
+ It is offered furnished, in full, to a single qualified lessee.
```

Brian chose "qualified lessee" from four options offered (tenant, lessee,
single qualified party, resident). Verified live: sentence serves with lessee,
"qualified buyer." count 0. Build completed clean in 36s.

Left untouched per instruction: line 222 "qualified buyers on request", and the
verb "offered" in the same sentence.

### Section III conveys block — 2026-09-12, commit `a2c64e0`

`index.html:271`, `:273`, `:283`. Text supplied verbatim by Brian.

```
- What conveys with the sale
+ What conveys with the lease

- The property is offered furnished, in full. Among the works and appointments that convey:
+ The property is furnished, in full. Among the works and appointments are:

- will be made available to qualified buyers on request.
+ will be made available to qualified lessees on request.
```

The six itemised works were already identical to Brian's text and were not
touched. Verified live: all three strings serve, "conveys with the sale" count 0.

Note: bullet three still reads "conveying as art" for the live-edge slab.
Brian's supplied text kept it, so it stands as given. Flagged, not changed.

Build-API note: `/pages/builds` did not list `a2c64e0` even after the deploy
succeeded. Trust the served page over the builds list; verify by fetching the
live URL, not by waiting for a build record.

### Section IV drawings lead — 2026-09-12, commit `39e22d0`

`index.html:300`

```
- The full drawing set will be made available to qualified buyers on request.
+ The full drawing set will be made available to qualified lessees on request.
```

Only occurrence in the section. Heading, h2, and drawings grid are neutral and
were not touched. Verified live; hero and Section III confirmed unregressed.

---

### Section V photography lead — 2026-09-12, commit `15e0729`

`index.html:324`

```
- Additional photography will be provided to qualified buyers on request.
+ Additional photography will be provided to qualified lessees on request.
```

Only occurrence in the section. Gallery markup and all alt text are neutral.

### Section I closing sentence — 2026-09-12, commit `15e0729`

`index.html:222`. Brian returned to this line after Section V.

```
- along with additional photography and documentation - will be provided to qualified buyers on request.
+ along with additional photography and documentation - will be provided to qualified lessees on request.
```

Pushed together with Section V. Verified live: both strings serve,
**"qualified buyers" is now 0 on the page**, "qualified lessees" is 4.
Regression check passed on hero, Sec I sentence, Sec III heading and lead,
Sec IV drawings.

### Section VI Monument Health paragraph — 2026-09-12, commit `b2f9e5a`

`index.html:388`. Brian reviewed the section and named this one word.

```
- For a residence purchased with a long horizon in mind,
+ For a residence held with a long horizon in mind,
```

Rest of the section (town, university, airport, recreation, closing
paragraph) is neutral and was not touched.

### Section VII price block — 2026-09-12, commit `b2f9e5a`

`index.html:421-422`. **The lease rate, supplied by Brian.**

```
- <div class="price-eyebrow">Offered at</div>
- <div class="price">$1,850,000</div>
+ <div class="price-eyebrow">Leased at</div>
+ <div class="price">$10,000 per month</div>
```

Two-line structure preserved; `price-note` ("Fully furnished. Move-in ready.")
left as is. Verified live.

### Sections VIII and IX — 2026-09-12, reviewed, no change

Brian reviewed both and named no changes.

### sitemap.xml and robots.txt — 2026-09-12, commit `bc9c5fa`

Both still advertised the sale domain, which worked against the canonical fix
in `be416dd`. The two belong together: a canonical pointing at the lease domain
is useless while the sitemap submits the sale domain.

```
robots.txt
- Sitemap: https://luxuryproperty-southdakota.com/sitemap.xml
+ Sitemap: https://lease.luxuryproperty-southdakota.com/sitemap.xml

sitemap.xml
- <loc>https://luxuryproperty-southdakota.com/</loc>  <lastmod>2026-07-06</lastmod>
+ <loc>https://lease.luxuryproperty-southdakota.com/</loc>  <lastmod>2026-09-12</lastmod>
+ second entry added: /live.html, priority 0.5, changefreq daily
```

Two judgment calls, flagged to Brian at the time and not vetoed: adding the
`live.html` entry (a real page, previously missing from the sitemap), and
setting `lastmod` to today (the old date predated this repo by two months).

Verified live: robots serves the lease sitemap URL; sitemap parses with two
lease-domain entries and zero sale-domain entries.

### Section footers — 2026-09-12, commit `632a3db`

One string in fifteen places, done as a single `replace_all` after the
section-by-section pass rather than fifteen times during it.

```
- Offered by the owner &mdash; Brian Demsey
+ Leased by the owner &mdash; Brian Demsey
```

Lines 213, 236, 257, 295, 320, 380, 407, 435, 489, 657, 682, 805, 824, 842,
894. Two markup variants both caught: the fourteen `class="section-footer"`
divs and the TOC's plain `<div>` at 213. Verified live: 15 present, 0
remaining. Regression check passed on hero, lease rate, canonical.

### Section VII buyer references — 2026-09-12, commit `46e3c8f`

`index.html:420`, `:423`. Three instances across two lines.

```
- would place the buyer inside that jurisdiction as of closing.
+ would place the lessee inside that jurisdiction as of closing.

- engaged by the buyer. A qualified buyer should retain trust, tax,
+ engaged by the lessee. A qualified lessee should retain trust, tax,
```

Verified live: both lines serve, "the buyer" and "qualified buyer" both 0 on
the served page. Regression clean on hero, lease rate, 15 footers, TOC hint.

**Left alone, flagged to Brian, not vetoed and not named:** "as of closing"
remains in line 420, inside the sentence just edited. A lease has a
commencement, not a closing. This is now the last sale-shaped phrasing in the
section.

### TOC hints — 2026-09-12, commit `1fb3b18`

Three hints still described a sale and disagreed with the headings they point
at. `index.html:128`, `:156`, `:205`.

```
III - Description and what conveys  -> Description and what is included
VII - Domicile and price            -> Domicile and rate
XIV - Printable listing documents   -> Printable descriptive documents
```

Two judgment calls, flagged to Brian and not vetoed: item III avoids "conveys"
entirely rather than mirroring the heading as "what conveys with the lease"
(too long for a hint, and "conveys" is the conveyance term being removed
elsewhere); item VII uses "rate" to match the "Leased at / $10,000 per month"
block.

**Not changed:** item I's title "The Offering". It mirrors the Section I
heading, which Brian reviewed and kept. Changing the TOC alone would create the
mismatch this task was fixing. Still open if he wants both changed together.

Verified live over HTTPS: all three new hints serve, all three old strings at 0,
regression clean on hero / lease rate / 15 footers.

### `<head>` metadata — 2026-09-12, commit `be416dd`

Seven edits, 22 insertions / 17 deletions. Done after the end-of-pass review
identified this as the only item with consequences beyond wording.

- `description`, `og:description`, `twitter:description`: sale price becomes
  "Leased fully furnished at $10,000 per month"; twitter opens "Private lease."
- `keywords`: "private sale" out; "private lease", "luxury rental South
  Dakota", "furnished lease" in
- **`canonical`**: was `https://luxuryproperty-southdakota.com/`, now the lease
  subdomain. This was the one actively harmful item: it told search engines the
  page was a duplicate of the sale site, so the lease site could not rank on
  its own.
- `og:url`, `og:image`, `twitter:image`, JSON-LD `url` and all four `image`
  entries: sale domain to lease domain
- JSON-LD `description`: "Offered furnished, in full" to "Leased furnished, in
  full"
- JSON-LD `offers`: flat `"price": "1850000"` replaced with a
  `UnitPriceSpecification` at 10000 USD, `unitCode: MON`, `unitText: per
  month`; offer `url` on the lease domain

Verified against the **served** page: JSON-LD parses, zero occurrences of the
sale price, zero sale-domain URLs.

Left alone deliberately: `availability: InStock` (ecommerce vocabulary, but
schema.org has no better fit for an available lease) and
`datePosted: 2026-08-21` (the sale site's date; cosmetic).

Lesson: validate JSON-LD by parsing it. A syntax error there kills all
structured data silently rather than erroring visibly.

### Sections XI, XII, XIII — 2026-09-12, reviewed, no change

Professional Photography, Livestream, Cinematic Reel. Brian reviewed all three
and named no changes.

### Section X representation — 2026-09-12, commit `cdeb1ea`

`index.html:659`

```
- to represent our family in the sale of our home.
+ to represent our family in the management of our home.
```

### Section XIV brochures heading — 2026-09-12, commit `cdeb1ea`

`index.html:842`

```
- <h2>Printable listing documents.</h2>
+ <h2>Printable descriptive documents.</h2>
```

Both verified live. Regression spot-check passed on hero and the Section VII
lease rate.

---

## Working method correction (2026-09-12)

Brian's instruction, in his words: **stay inside the boundaries of the section
in question. Review at the end for inconsistencies.**

I had been reporting findings from outside the named section on nearly every
turn (head metadata, other sections' buyer references, the shared footer). That
is the same overreach he corrected earlier in the session, in a different shape.
The parked lists below exist so those items are captured without being raised
mid-section.

Do not run a whole-file sweep until Brian says the section-by-section pass is
finished.

---

## Remaining sale language (located, not changed)

Found by grep 2026-09-12. Each waits until Brian names that section.

- **Line 415, 418** (Section VII, tax disclaimer): "engaged by the buyer",
  "A qualified buyer should retain trust, tax, and estate counsel of their own
  choosing." This is legal language, not marketing copy. A straight word swap
  may not be right; worth more thought than the other substitutions.
- **Line 883** (Sotheby's imagery notice): "prospective buyers"
- **Section footer, every section**: `Offered by the owner - Brian Demsey`.
  Repeated template line. Cleaner as one pass across all sections than page by
  page. Appears in Provenance and Section V among others.
- **`<head>` metadata**: see the deferred list above, including the canonical
  and og:url tags still pointing at the sale domain.

---

## Verification gotchas (learned the hard way)

**The builds API lags and misreports.** `/pages/builds` did not list `a2c64e0`
at all after a successful deploy, and `/pages/builds/latest` returned a stale
commit. The served page is the authority. Do not gate verification on a build
record.

**Poll loops need an actual delay.** A `for i in $(seq 1 60)` loop with no sleep
burns all iterations in seconds, so it reports "not deployed" while the build is
still in flight. Section IV looked like a failed push for exactly this reason,
then appeared on iteration 1 of the next poll. Either put a real wait between
attempts or confirm the build has left `building` before polling content.

**Check for regressions, not just the new string.** Each content poll should
also confirm a couple of earlier edits are still served, so a bad deploy that
reverts prior work is caught immediately.

---

## Observed, awaiting Brian

Recorded so nothing is lost between sessions. **Not a to-do list and not a
recommendation.** Each waits until Brian names that page.

### Contents (TOC) — reviewed 2026-09-12, no edits made

- Item I title: "The Offering"
- Item III hint: "Description and what conveys" (conveyance = title passing at closing)
- Item VII hint: "Domicile and price"
- Footer: "Offered by the owner — Brian Demsey"

Neutral, likely no change needed: Inquire / "A private introduction",
items II, IV, V, VI, IX through XIV.

Plumbing note: anchor hrefs and `data-nav` values (`#offering`, `#opportunity`)
are wired to the view-switching and audio JS around `index.html:909`. Renaming
them requires touching that script. Invisible to readers. Not worth the risk on
a live page unless Brian wants it.

### Hero page, deferred item

- Line 219: "offered furnished, in full, to a single qualified buyer" — sits
  directly beneath the converted eyebrow.

### Section I, deferred items

- Line 224: `offering-audio.m4a` / `.mp3` - **RESOLVED 2026-09-12, commit
  `727d9ce`.** Brian re-recorded the narration for the lease.

  New take opens "Hi, my name is Brian Demsey and I built this house and I'm
  the one **leasing** it." Transcribed and checked: no other sale vocabulary
  anywhere in the recording.

  Recorded on iPhone Voice Memos, same device and settings as the original, so
  the format matched exactly: AAC 48kHz mono, 243.6s vs the old 244.4s. The
  `.mp3` was re-encoded at 96k from the new `.m4a` rather than transcoded from
  the old lossy file. Filenames unchanged, so `index.html` needed no edit.

  Verified live by byte count, not just a 200: served m4a is 2,178,823 bytes,
  matching the new local file; the old take was 2,161,844.

  Old take backed up outside the repo at
  `<scratchpad>/OLD-offering-audio.m4a` / `.mp3`. Not in git history beyond
  the commits before `727d9ce`.

  **Two things I got wrong, recorded so they are not repeated:**
  1. I claimed the audio "has to be re-recorded, not edited" based on reading
     the v2 script PDF, then later claimed it needed "one word changed". Both
     were guesses about audio I had not listened to. **The recording never
     matched that script** - the old take had a different opening ("Hi.
     Hopefully we'll have a chance to meet in person"), said Mark Singer
     designed the house "40 years ago" (contradicting the site's own history),
     and contained none of the script's paddling opening. Transcribe before
     asserting what audio says.
  2. My regex check for a spoken phone number reported "none detected" when
     the number **is** spoken, at 228.68s. A failed pattern match is not
     evidence of absence.

  **Still live in the recording:** Brian's cell number, 949-291-1422, spoken
  aloud at 228.68s on a public page. The original script's own notes warned
  about this and recommended a dedicated forwarding line. Brian is aware; his
  call.
- Line 271: "What conveys with the sale"

### Section VII, deferred item

- Line 422: `$1,850,000` price block. No lease rate has been supplied.

### `<head>` metadata, deferred

- Line 7 description, line 8 keywords ("private sale"), line 25 twitter
  ("Private sale.")
- Lines 10, 17, 34: `canonical` and `og:url` point at
  `https://luxuryproperty-southdakota.com/`, the sale domain. This one has SEO
  consequences beyond wording: a canonical pointing elsewhere tells search
  engines this page is a duplicate and should not be indexed on its own.
- Lines 28-60: JSON-LD structured data typed `SingleFamilyResidence` with
  sale-shaped description.

---

## Infrastructure: the TLS certificate

**RESOLVED 2026-09-12.** https://lease.luxuryproperty-southdakota.com serves
200 with a valid Let's Encrypt certificate (`CN=lease.luxuryproperty-southdakota.com`,
issuer `CN=YR1`, valid 2026-09-12 to 2026-12-11, `ssl_verify=0`).

**What fixed it:** the documented remove-and-re-add of the custom domain. The
`PUT cname:` re-add is what triggers the DNS check and queues the Let's Encrypt
job. Cert issued at 14:16 UTC, within minutes of the re-add.

**Sequence as actually run:**

1. `git rm CNAME`, commit, push (`bc09bcc`) - so the file could not re-apply
   the domain while the API setting was cleared
2. `gh api -X PUT .../pages -f cname=` - cleared. Note `https_enforced` flipped
   itself to `true` here; that is GitHub's default for a bare `.github.io` host,
   not something to set deliberately. It reverted to `false` on the re-add.
3. `gh api -X PUT .../pages -f cname=lease.luxuryproperty-southdakota.com` -
   **this is the trigger**
4. GitHub's API wrote its own `Create CNAME` commit (`2bf880d`) to `main`
   automatically. A manual CNAME restore was therefore rejected as
   non-fast-forward; `git pull --rebase` reconciled it and the local commit was
   skipped as already applied.
5. Verified with a real HTTPS fetch plus `openssl s_client`, not the API's word.

**Two things went sideways mid-sequence, both self-resolving:**

- Build `bc09bcc` reported `errored` / "Page build failed." while `CNAME` was
  absent but the API claimed the domain. The next build (`2bf880d`, GitHub's own
  CNAME commit) succeeded. Expected and harmless.
- The push rejection at step 4. **Do not `--force` here** - it would fight
  GitHub's own commit. Rebase and let it stand.

HTTP served 200 throughout; there was no visitor-facing outage.

**`https_enforced` enabled 2026-09-12** on Brian's instruction, once the cert
was confirmed approved. `PUT .../pages -F https_enforced=true`.

Verified by real fetches, not the API's word:

```
http://  -> 301 -> https://lease.luxuryproperty-southdakota.com/
followed -> 200, 1 redirect, final scheme https
live.html -> 301 -> https://.../live.html   (site-wide, not just root)
https:// -> 200, ssl_verify=0
```

Page content confirmed intact over TLS: hero "A Private Lease", "Leased at /
$10,000 per month", 15 footers, 4 "qualified lessees", canonical on the lease
domain, zero sale-price and zero sale-domain remnants.

Order matters here: enforcement is downstream of the certificate. It was set
only after `https_certificate.state` read `approved`. Do not set it first as a
way to trigger issuance - that is not what it does.

---

### Original diagnosis, kept for reference

**Status at the time: unresolved. Site served over HTTP only.**

`https://lease.luxuryproperty-southdakota.com` fails to connect. The Pages IPs
present `CN=*.github.io`, which does not cover this hostname, so the handshake
fails with `SEC_E_WRONG_PRINCIPAL`. The Pages API shows `https_certificate: null`
— not pending, not errored. Issuance was never triggered.

Everything else verified clean: single CNAME to `briandemsey.github.io`, no
conflicting A/AAAA on the subdomain, no CAA record restricting Let's Encrypt,
ACME challenge path reachable over HTTP with zero redirects, hostname 36 chars
(under the 64-char limit), no cross-repo CNAME collision, repo public and
building. `/pages/health` returns `{}` on repeat calls and gave no verdict.

**Documented remedy** (docs.github.com, verified 2026-09-12, not from memory):
remove and re-add the custom domain. Setting or changing the custom domain is
what triggers the DNS check and queues the Let's Encrypt job. Enabling "Enforce
HTTPS" is **not** the trigger — it is downstream of a cert that already exists,
and the docs never present it as the retry mechanism.

**Sequence, ready to run on Brian's word:**

1. Delete `CNAME` from `main` first, so the file and the API setting do not fight.
   Leaving it risks a half-set domain with `pending_domain_unverified_at` populated,
   which is worse than the current clean null.
2. `PUT /repos/.../pages` with `cname: null` to remove the domain.
3. `PUT` again with `cname: lease.luxuryproperty-southdakota.com` to re-add.
4. Restore the `CNAME` file so repo and API agree.
5. Poll for a non-null `https_certificate`, then confirm with a real HTTPS fetch.

Cost if it goes wrong: domain briefly unset; worst case lands unverified and
needs another cycle. HTTP currently serves 200.

Doc sources:
- https://docs.github.com/en/pages/getting-started-with-github-pages/securing-your-github-pages-site-with-https
- https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site/troubleshooting-custom-domains-and-github-pages

---

## Standing rules for this project

- **One page at a time.** Brian has had to say this repeatedly. Report on the
  page he asked about and nothing else.
- No em dashes in anything written for Brian.
- No guessing. Test locally, verify before claiming success.
- Never ask Brian to check or refresh a page; measure it directly.
- Do not invent listing terms. Lease rate, availability, and terms come from
  Brian.
- Save to the project folder on F:.
