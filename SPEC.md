# Innovation Quality Scorer

A scalar function that evaluates the creative and innovative merit of a single startup idea.

## Input Schema

The input is an object with a single required field called `idea`.

The `idea` field can be:
- A string (plain text pitch)
- An image (schema type: image)
- An audio clip (schema type: audio)
- A video (schema type: video)
- A composite array containing any mix of the above

Use this exact input schema:
```json
{
  "type": "object",
  "properties": {
    "idea": {
      "anyOf": [
        {"type": "string", "description": "A text pitch."},
        {"type": "image", "description": "An image pitch."},
        {"type": "audio", "description": "An audio pitch."},
        {"type": "video", "description": "A video pitch."},
        {
          "type": "array",
          "description": "A composite pitch with multiple parts.",
          "items": {
            "anyOf": [
              {"type": "string"},
              {"type": "image"},
              {"type": "audio"},
              {"type": "video"}
            ]
          }
        }
      ]
    }
  },
  "required": ["idea"]
}
```

## Output

A scalar score in [0, 1] representing innovation quality.

## Evaluation Criteria

1. **Conceptual Novelty**: Genuinely new or derivative?
2. **Technical/Business Model Innovation**: New tech or model?
3. **Insight Depth**: Deep domain expertise?
4. **Cliché Avoidance**: Avoids Uber for X?
5. **First-Principles Thinking**: Reasons from first principles?