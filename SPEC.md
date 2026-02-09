# Innovation Quality Scorer

A scalar function that evaluates the creative and innovative merit of a single startup idea.

## Input Schema

The input is an object with an `idea` field that contains a single startup idea. The idea can be:
- A string (text pitch or description)
- An image (pitch deck slide, mockup)
- An audio (audio pitch)
- A video (video pitch or demo)
- An array of the above (composite pitch with multiple parts)

```json
{
  "idea": "An AI-powered personal stylist that uses your existing wardrobe photos to suggest daily outfits and shopping recommendations."
}
```

## Output

A scalar score in [0, 1] representing the idea's innovation quality, where 1.0 indicates breakthrough innovation and 0.0 indicates purely derivative thinking.

## Evaluation Criteria

Evaluate based on five dimensions:

1. **Conceptual Novelty**: Is this genuinely new or a marginal improvement? Does it combine elements unexpectedly? Would it surprise domain experts?

2. **Technical/Business Model Innovation**: Is there new technology, algorithm, or process? Does the business model create value in a novel way?

3. **Insight Depth**: Does the idea stem from deep domain expertise or genuine customer understanding? Is there a non-obvious insight?

4. **Cliché Avoidance**: Does it avoid startup clichés ("Uber for X")? Does it transcend buzzword territory with substance?

5. **First-Principles Thinking**: Does it reason from first principles rather than analogy? Does it question assumptions others take for granted?