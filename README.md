# Innovation Quality Scorer

A scalar function that evaluates the creative and innovative merit of startup ideas.

## Overview

This function assesses startup ideas across five key dimensions of innovation quality, returning a score from 0 (purely derivative) to 1 (breakthrough innovation).

## Input

The function accepts a single `idea` field which can be:

- **Text**: A written pitch or description of the startup idea
- **Image**: A pitch deck slide, mockup, or diagram
- **Audio**: A verbal pitch or audio explanation
- **Video**: A demo video or pitch recording
- **Composite**: An array combining multiple formats (e.g., slides with narration)

### Example Input

```json
{
  "idea": "We're building a prediction market for scientific reproducibility. Researchers stake tokens on whether published studies will replicate, creating financial incentives for honest assessment."
}
```

## Output

A scalar score in the range [0, 1]:

- **0.0**: Purely derivative thinking, no innovation
- **0.25**: Low innovation, mostly familiar patterns
- **0.50**: Moderate innovation, some novel elements
- **0.75**: High innovation, significant novel elements
- **1.0**: Breakthrough innovation, category-defining

## Evaluation Dimensions

The function evaluates ideas across five dimensions:

### 1. Conceptual Novelty (20%)
- **Domain Combination**: Does the idea synthesize disparate domains unexpectedly?
- **Problem Framing**: Does it reframe the problem in a genuinely new way?

### 2. Technical/Business Model Innovation (20%)
- **Technical Approach**: Does it propose genuinely novel technical methods?
- **Business Model**: Does it create/capture value in a novel way?

### 3. Insight Depth (25%)
- **Domain Knowledge**: Does it reveal deep domain understanding?
- **Contrarian Insight**: Does it contain a non-consensus "secret"?

### 4. Cliché Avoidance (15%)
- **Formula Language**: Does it avoid "Uber for X" patterns?
- **Specificity**: Does it contain concrete substance, not buzzwords?

### 5. First-Principles Thinking (20%)
- **Assumption Questioning**: Does it challenge industry conventions?
- **Foundational Reasoning**: Does it reason from fundamentals, not analogy?

## Use Cases

- **Venture Capital**: Screen startup pitches for innovative potential
- **Accelerators**: Evaluate applications for innovative merit
- **Corporate Innovation**: Assess internal innovation proposals
- **Founders**: Self-assess ideas before pitching
- **Research**: Study patterns in startup innovation

## Multimodal Support

The function handles all input modalities natively:

```json
// Image input
{
  "idea": {"type": "image_url", "image_url": {"url": "https://example.com/pitch-slide.png"}}
}

// Video input  
{
  "idea": {"type": "video_url", "video_url": {"url": "https://example.com/demo.mp4"}}
}

// Composite input
{
  "idea": [
    "Our pitch:",
    {"type": "image_url", "image_url": {"url": "https://example.com/slide1.png"}},
    {"type": "image_url", "image_url": {"url": "https://example.com/slide2.png"}}
  ]
}
```
