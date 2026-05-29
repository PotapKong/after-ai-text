# Workflow and Audit

## Writing model

Treat AI as a draft accelerator, not the final author.

Recommended order:
1. Give the model structure and facts.
2. Read the draft aloud or simulate a read-aloud check.
3. Add real specifics, opinion, and lived texture.
4. Remove clichés and structural AI patterns.
5. Audit before publishing.

## Final audit checklist

- [ ] No obvious banned phrases remain.
- [ ] Sentence lengths vary.
- [ ] The text contains concrete details, numbers, or a real example when appropriate.
- [ ] The text has a viewpoint, not safe agreement with everything.
- [ ] There are no formal intro/conclusion blocks unless the genre needs them.
- [ ] The text reads aloud without monotony.
- [ ] Fake modal hedging has been removed.
- [ ] Personal texture is real, not invented.
- [ ] No dramatic triple-fragment rhetoric remains unless clearly intentional.
- [ ] Repeated colons are gone unless they serve a real structural purpose.
- [ ] Colon-based dramatic turns have been flattened into normal clauses where possible.
- [ ] Em dash overuse has been corrected where simpler punctuation works.
- [ ] Meta-turn phrases like `проблема в другом` or `дело в том` are gone unless clearly intentional.
- [ ] Fake-depth wrappers and symmetrical contrast frames are gone.
- [ ] Quote-based comparison tricks like `не как "X", а "Y"` are gone.
- [ ] Repeated model habits are gone or clearly intentional.
- [ ] Pull-quote paragraph endings are not stacked without purpose.

## Validation loop

1. Rewrite.
2. Run the checklist.
3. Fix only failed items.
4. Re-check.
5. Deliver only after the audit passes well enough for the genre.

## Scoring

Use scoring for medium and long rewrites, audits, articles, expert posts, or when the user asks for quality control.

Skip scoring for quick line edits, one-sentence rewrites, captions, or small phrase-level fixes.

Rate the text 1-10 on each dimension:

| Dimension | Question |
|-----------|----------|
| Directness | Текст делает утверждения или только подводит к ним? |
| Rhythm | Ритм меняется или идёт метрономом от начала до конца? |
| Specificity | Есть числа, сцены, детали, механика, реальные примеры? |
| Voice | Слышна позиция автора или текст безопасно соглашается со всем? |
| Density | Много ли смысла на абзац? Есть ли фразы, которые можно удалить без потери? |

Threshold: 35/50.

Rules:
- If the total score is below 35, return to Step 3 or Step 4.
- Do not rewrite the whole text unless the structure failed broadly.
- Fix only dimensions scored below 6.
- If any high-severity issue remains, the related dimension cannot score above 6.

Density scoring:
- 10 = almost nothing can be removed without losing meaning.
- 5 = several sentences can be removed with little loss.
- 1 = most of the text can be removed and the meaning barely changes.
