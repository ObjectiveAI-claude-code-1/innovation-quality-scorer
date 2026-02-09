# Innovation Quality Scorer

A scalar function that evaluates the creative and innovative merit of a single startup idea.

## Input Schema

The input is an object with an `idea` field. The `idea` field uses anyOf to accept:
- A string (text pitch or description)
- An image (type: image)
- An audio (type: audio)
- A video (type: video)
- An array of strings and/or multimodal elements (composite pitch)

Example input schema structure:
```json
{
  "type": "object",
  "properties": {
    "idea": {
      "anyOf": [
        {"type": "string"},
        {"type": "image"},
        {"type": "audio"},
        {"type": "video"},
        {"type": "array", "items": {"anyOf": [{"type": "string"}, {"type": "image"}, {"type": "audio"}, {"type": "video"}]}}
      ]
    }
  },
  "required": ["idea"]
}
```

## Output

A scalar score in [0, 1] representing innovation quality.

## Evaluation Criteria

1. **Conceptual Novelty**: Is this genuinely new or derivative?
2. **Technical/Business Model Innovation**: Is there new technology or novel business model?
3. **Insight Depth**: Does it stem from deep domain expertise?
4. **Cliché Avoidance**: Does it avoid Uber for X patterns?
5. **First-Principles Thinking**: Does it reason from first principles?