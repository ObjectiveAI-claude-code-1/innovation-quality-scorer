# Innovation Quality Scorer

A scalar function that evaluates the creative and innovative merit of startup ideas.

## Overview

This function analyzes startup ideas across multiple dimensions of innovation quality, returning a score from 0 (completely derivative) to 1 (genuinely groundbreaking). It's designed to assess the thinking behind an idea rather than its execution viability.

## Input

The function accepts startup ideas in multiple formats:

- **Text**: Elevator pitches, executive summaries, one-liners, or detailed descriptions
- **Image**: Pitch deck slides, napkin sketches, product mockups, or concept diagrams
- **Audio**: Recorded pitches, founder interviews, or verbal explanations
- **Video**: Demo videos, pitch recordings, or prototype demonstrations
- **Composite**: Arrays combining multiple elements (e.g., pitch deck with text, images, and embedded videos)

## Evaluation Dimensions

### Conceptual Novelty
- **Core Concept Novelty**: Is this genuinely new or derivative?
- **Problem Reframing**: Does it reveal new ways of understanding existing problems?

### Technical/Business Model Innovation
- **Technical Innovation**: Genuine breakthroughs vs. trendy tech applications
- **Business Model Innovation**: Novel value creation and capture mechanisms

### Insight Depth
- **Domain Insight Depth**: Evidence of hard-won, non-obvious domain knowledge
- **Contrarian Knowledge**: Specific, substantiated beliefs that contradict conventional wisdom

### Cliché Avoidance
- **Structural Cliché Avoidance**: Avoiding "Uber for X" or "A meets B" patterns
- **Buzzword Independence**: Technology as specific capability, not magic words
- **Market Claim Authenticity**: Specific market insight vs. lazy "$X billion market" claims

### First-Principles Thinking
- **First-Principles Evidence**: Reasoning from fundamental truths
- **Assumption Identification**: Explicitly questioning domain assumptions
- **Solution Inevitability**: Solutions derived from deep analysis, not arbitrary choices

### Holistic Assessment
- **Paradigm Shift Potential**: Potential to fundamentally reshape its domain
- **Overall Innovation Quality**: Comprehensive assessment across all dimensions

## Output

A scalar score between 0 and 1:

| Score Range | Category | Description |
|-------------|----------|-------------|
| 0.0 - 0.2 | Derivative | Essentially a copy with no distinguishing insight |
| 0.2 - 0.4 | Incremental | Modest improvements to existing concepts |
| 0.4 - 0.6 | Solid | Genuine thought and some novelty |
| 0.6 - 0.8 | Innovative | Genuinely new approaches or non-obvious insights |
| 0.8 - 1.0 | Exceptional | Potential paradigm shift with profound originality |

## Example Usage

```json
{
  "idea": "A platform that uses satellite imagery and machine learning to predict crop yields 6 months in advance, enabling farmers in developing countries to secure fair-price forward contracts before harvest."
}
```

## Key Distinctions

The function distinguishes between:
- Being first in a geography vs. conceptual novelty
- Using AI/blockchain as buzzwords vs. specific technical innovation
- "Faster/cheaper/better" vs. paradigm shifts
- Pattern-matching to successful companies vs. first-principles reasoning
- Surface-level market claims vs. genuine customer insight

## Note

This scorer evaluates innovation merit, not execution viability. A highly innovative idea may still face significant market, technical, or operational challenges. The question answered is "How innovative is this thinking?" not "Will this succeed?"
