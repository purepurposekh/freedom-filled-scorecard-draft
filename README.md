# Freedom Filled® Business Scorecard · Draft v1

Working draft of the unified Scorecard described in `quiz-unified-architecture-v1`. Replaces the legacy SMS quiz at `tracyharris.co/quiz`, the v3c "A Quiet Reset" quiz, and the never-built "FRESH Quiz".

## Status

- Static HTML draft. Not vault canon. Not live anywhere customer-facing.
- Holding for Karl review and Tracy voice review.
- Email capture and AC tag wiring stubbed (commented `DRAFT NOTE` markers in code).

## Pages

- `index.html` · landing (cold-traffic CTA "Where Should You Focus Right Now?")
- `capture.html` · email + first name + business model + business season pre-qualifiers
- `quiz.html` · 20 questions, 5/5/5/5 across F.R.E.S.H. → Build → Sell → Lead, with 4 splash sections
- `results.html` · 4-route routing logic with hard pre-qualifier gates

## Routes

| Route | Criteria | Send to |
|---|---|---|
| Ready FFB | Right-fit model + overall ≥65% + every business pillar ≥45% + FRESH ≥50% | FFB application + book call |
| Workshop fit | Right-fit + overall 45–75% + FRESH ≥50% | Paid masterclass |
| FRESH-first | FRESH <45% regardless of business score | FRESH Reset |
| Free nurture | Wrong-fit OR overall <35% | Podcast playlist + nurture |

Right-fit business models: coaching, course, membership, service, creative, exploring. Ecommerce routes to free nurture (out of FFB scope).

## Outstanding wiring

1. Replace `DRAFT NOTE` stub on `capture.html` with POST to AC `create_or_update_contact` + tags `Quiz: Started`, `Quiz: Source - {utm}`.
2. Replace `DRAFT NOTE` stub on `quiz.html` with route tag fire on completion.
3. Replace `DRAFT NOTE` stub on `results.html` with route + focus-pillar tags.
4. Cloudflare Worker endpoint to broker AC API calls (browser CORS will block direct).
5. Tracy voice review on all copy across all four files.
6. Map result CTA `href` URLs to live destinations (FFB application, workshop checkout, FRESH Reset landing, podcast starter playlist).
7. Decide URL: `tracyharris.co/quiz` (replaces legacy in same swap) or `scorecard.tracyharris.co`.

## Source spec

Full architecture spec lives at `/home/claude-bot/research/quiz-unified-architecture-v1.md`.
