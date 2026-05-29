# Pattern Severity

Use this file to calibrate how hard to push back during audit or rewrite.

Not every AI signal deserves the same response. A text should not be over-corrected into sterile prose just because it contains one imperfect phrase.

## Low severity

Address in the final pass, or skip if correction would make the text worse.

- one filler phrase in an otherwise clean text
- a single em dash where a comma would also work
- one rhetorical question that genuinely moves the reader forward
- one earned contrast frame such as `не X, а Y`
- one abstract noun near a concrete claim, example, number, or mechanism
- minor hedging that reflects real uncertainty
- one short punchline-style sentence that lands naturally

Low-severity issues are not worth interrupting the flow for while bigger problems remain.

## Medium severity

Flag and rewrite in Step 3 or Step 4. These issues noticeably weaken the text.

- 2-3 repeated formatting tricks: colons, em dashes, fragment pairs, question-led blocks
- several abstract nouns stacked without concrete anchors
- safe, commitment-free tone across most of the text
- rhythm that stays metronomic for 4+ sentences
- intro or conclusion that exists only because the template expects one
- one neural turn such as `проблема в другом` or `вот в чём подвох` used as the main insight move
- repeated paragraph endings that sound polished but interchangeable

Medium-severity issues usually need rewriting, not cosmetic synonym swaps.

## High severity

Restructure before touching wording. These issues make the text read as AI output regardless of individual phrases.

- `не X, а Y` or similar contrast frames used 3+ times
- fake-depth turn used as the core thesis or conclusion
- every paragraph structured like a LinkedIn post: claim -> colon -> elaboration -> one-liner
- no concrete example, number, scene, operational detail, or mechanism anywhere
- text sounds polished and says almost nothing
- repeated paragraph endings that feel like quote cards
- the whole text could be reused for another topic in the same category with minimal changes
- the main argument is built from wrappers, transitions, and abstractions instead of claims

## Editing priority

1. High severity -> fix structure first.
2. Medium severity -> fix after structure is clean.
3. Low severity -> fix in final pass or skip.

Do not spend time on low-severity points while high-severity ones remain.

## Scoring link

If a high-severity issue remains, the related scoring dimension cannot score above 6.

Examples:
- no concrete detail anywhere -> Specificity max 5
- polished but empty text -> Density max 4
- metronomic sentence flow -> Rhythm max 5
- safe neutral tone with no position -> Voice max 6
- wrapper-heavy argument -> Directness max 6
