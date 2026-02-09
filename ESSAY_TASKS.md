# Innovation Quality Scorer: Task Definitions

This document defines the key evaluation tasks that the Innovation Quality Scorer function must perform. Each task corresponds to a specific dimension or sub-dimension of innovation quality as articulated in ESSAY.md. These tasks will be implemented as `vector.completion` tasks in the function's `tasks` array.

---

## Overview of Task Structure

The function evaluates startup ideas across five core dimensions, with some dimensions benefiting from sub-task decomposition for more nuanced evaluation:

1. **Conceptual Novelty** (2 tasks)
2. **Technical/Business Model Innovation** (2 tasks)
3. **Insight Depth** (2 tasks)
4. **Cliché Avoidance** (2 tasks)
5. **First-Principles Thinking** (2 tasks)

Each task produces a score that contributes to the final innovation quality assessment.

---

## Dimension 1: Conceptual Novelty

### Task 1.1: Domain Combination Novelty

**Purpose**: Evaluate whether the idea combines elements from disparate domains in unexpected ways, or whether it remains within a single familiar category.

**Evaluation Criteria**:
- Does the idea connect concepts from different industries, fields, or problem spaces?
- Is the combination unprecedented or has it been done many times before?
- Does the synthesis create emergent properties greater than the sum of parts?
- Would the combination surprise domain experts?

**Response Scale**: Binary (LOW/HIGH)
- LOW: The idea operates within a single familiar domain or combines elements that are commonly combined
- HIGH: The idea synthesizes disparate domains in unexpected ways, creating genuinely novel conceptual territory

**Rationale**: True conceptual novelty often emerges at the intersection of domains. Airbnb combined hospitality with peer-to-peer marketplaces; Stripe combined developer tools with payment processing. This task captures that cross-pollination dimension.

---

### Task 1.2: Problem Framing Novelty

**Purpose**: Evaluate whether the idea reframes an existing problem in a genuinely new way, or whether it accepts the conventional problem definition.

**Evaluation Criteria**:
- Does the idea define the problem differently than existing solutions?
- Is there a novel perspective on what the "real" problem is?
- Does the framing reveal something hidden about the problem space?
- Would the problem statement itself surprise people familiar with the space?

**Response Scale**: Binary (LOW/HIGH)
- LOW: The idea accepts conventional problem framing and offers a solution within that frame
- HIGH: The idea reframes the problem in a novel way that changes what solutions are even possible

**Rationale**: Sometimes innovation lies not in the solution but in reconceptualizing the problem. Reframing "how do we make taxis faster?" as "how do we optimize idle transportation capacity?" opens entirely different solution spaces.

---

## Dimension 2: Technical/Business Model Innovation

### Task 2.1: Technical Approach Innovation

**Purpose**: Evaluate whether the idea proposes genuinely novel technical approaches, algorithms, architectures, or uses of technology.

**Evaluation Criteria**:
- Does the idea propose new technical methods rather than applying existing ones conventionally?
- Is there innovation in how technologies are combined or integrated?
- Does the technical approach enable something previously impossible (not just easier)?
- Is the technology use substantive rather than decorative?

**Response Scale**: 4-level (None/Low/Medium/High)
- None: No meaningful technical component, or technology is purely conventional
- Low: Uses existing technology in standard ways; technology is incidental to the idea
- Medium: Applies existing technology in somewhat novel ways or to new domains
- High: Proposes genuinely novel technical approaches, architectures, or unprecedented technology combinations

**Rationale**: Technical innovation is a key driver of startup differentiation. This task distinguishes ideas that merely use technology from those that advance it.

---

### Task 2.2: Business Model Innovation

**Purpose**: Evaluate whether the idea proposes novel mechanisms for creating, delivering, or capturing value.

**Evaluation Criteria**:
- Is there innovation in how value is created (new value propositions, new resource configurations)?
- Is there innovation in how value is delivered (new channels, new partnerships)?
- Is there innovation in how value is captured (novel pricing, new revenue mechanisms)?
- Does the business model challenge industry conventions?

**Response Scale**: 4-level (None/Low/Medium/High)
- None: Standard business model for the category; nothing novel in how value flows
- Low: Minor variations on established business models
- Medium: Meaningful business model variations or creative combinations of existing models
- High: Genuinely novel business model that creates new categories of value creation or capture

**Rationale**: Business model innovation is often underappreciated. Many successful startups (Spotify, Airbnb, Uber) succeeded partly through business model innovation, not just product innovation.

---

## Dimension 3: Insight Depth

### Task 3.1: Domain Knowledge Depth

**Purpose**: Evaluate whether the idea reveals deep understanding of the problem domain, or whether it appears to be surface-level pattern matching.

**Evaluation Criteria**:
- Does the pitch reveal non-obvious knowledge about the domain?
- Is there evidence of understanding why existing solutions fail?
- Does the idea anticipate objections that would only occur to domain experts?
- Is there evidence of genuine experience with the problem space?

**Response Scale**: 4-level (Shallow/Surface/Moderate/Deep)
- Shallow: No evidence of domain understanding; could have been generated from a template
- Surface: Basic understanding of the domain but no non-obvious insights
- Moderate: Shows solid domain knowledge with some non-obvious observations
- Deep: Reveals expert-level understanding with insights that would surprise domain experts

**Rationale**: Ideas born from genuine domain expertise have a different quality than those born from trend-following. This task attempts to detect the depth of understanding behind the idea.

---

### Task 3.2: Contrarian Insight Presence

**Purpose**: Evaluate whether the idea contains a "secret"—a belief that is both non-consensus and potentially correct.

**Evaluation Criteria**:
- Does the idea rest on a belief that most people would disagree with?
- Is there an explanation for why the conventional wisdom is wrong?
- Does the contrarian element seem well-reasoned rather than arbitrary?
- Would success of the idea prove something surprising about the world?

**Response Scale**: Binary (ABSENT/PRESENT)
- ABSENT: The idea follows conventional wisdom; success would not prove anything surprising
- PRESENT: The idea rests on a contrarian insight that, if correct, would overturn common assumptions

**Rationale**: Peter Thiel's famous question "What important truth do few people agree with you on?" captures this dimension. The best innovations often involve being right when most people are wrong.

---

## Dimension 4: Cliché Avoidance

### Task 4.1: Formula Language Avoidance

**Purpose**: Evaluate whether the idea relies on startup formula language and clichés, or whether it communicates authentically.

**Evaluation Criteria**:
- Does the pitch avoid "Uber for X" and similar formulaic descriptions?
- Are buzzwords (AI, blockchain, disruption) used with precision or as empty placeholders?
- Does the language feel authentic and specific rather than templated?
- Would removing buzzwords leave substantive content?

**Response Scale**: Binary (FORMULAIC/AUTHENTIC)
- FORMULAIC: Heavy reliance on startup clichés, formula descriptions, and buzzword accumulation
- AUTHENTIC: Communicates in specific, precise language that couldn't apply to any other idea

**Rationale**: Clichéd language often signals clichéd thinking. Ideas that require startup formula language to be understood may lack genuine distinctiveness.

---

### Task 4.2: Specificity and Substance

**Purpose**: Evaluate whether the idea contains concrete, specific content or remains at an abstract, hand-wavy level.

**Evaluation Criteria**:
- Are claims specific and verifiable rather than vague and aspirational?
- Does the pitch include concrete details about how things work?
- Is the problem described with specificity (which customers, what pain, why now)?
- Does the solution explain mechanisms rather than just outcomes?

**Response Scale**: 4-level (Vague/General/Specific/Highly Specific)
- Vague: Purely abstract; no concrete details about problem, solution, or mechanism
- General: Some specificity but mostly high-level; could describe many different ideas
- Specific: Clear specificity about problem, solution, and mechanism; distinguishable from alternatives
- Highly Specific: Exceptionally concrete; reveals deep thought about exactly how things work

**Rationale**: Substance is the antidote to cliché. Ideas with genuine specificity are less likely to be buzzword-driven vapourware.

---

## Dimension 5: First-Principles Thinking

### Task 5.1: Assumption Questioning

**Purpose**: Evaluate whether the idea questions assumptions that others take for granted, or whether it accepts industry conventions.

**Evaluation Criteria**:
- Does the idea challenge fundamental assumptions in its space?
- Is there evidence of asking "why?" repeatedly to reach foundational truths?
- Does the idea reject constraints that others accept as given?
- Are industry conventions examined rather than assumed?

**Response Scale**: Binary (CONVENTIONAL/QUESTIONING)
- CONVENTIONAL: Accepts industry assumptions and conventions; innovates within established constraints
- QUESTIONING: Challenges fundamental assumptions; asks why things must be as they are

**Rationale**: First-principles thinking starts with questioning what everyone else takes for granted. This task detects whether the idea does that questioning.

---

### Task 5.2: Foundational Reasoning Evidence

**Purpose**: Evaluate whether the idea demonstrates reasoning from fundamental constraints and possibilities, rather than from analogy to existing solutions.

**Evaluation Criteria**:
- Does the pitch explain why the solution must be this way based on fundamental constraints?
- Is there evidence of working backward from physics, economics, or human nature?
- Does the reasoning avoid "because competitors do it" or "because that's how it's done"?
- Would the idea survive if industry conventions changed completely?

**Response Scale**: 4-level (Pure Analogy/Mostly Analogy/Mostly First-Principles/Pure First-Principles)
- Pure Analogy: Entirely based on copying or adapting existing solutions; no fundamental reasoning
- Mostly Analogy: Primarily analogical with minor first-principles elements
- Mostly First-Principles: Primarily derived from fundamentals with some analogical elements
- Pure First-Principles: Entirely derived from fundamental constraints and possibilities; industry-convention-independent

**Rationale**: This task distinguishes ideas that represent genuine reasoning from those that are merely pattern-matching on existing successes.

---

## Task Weighting and Score Aggregation

The final innovation score is computed by aggregating task outputs. While all dimensions are important, the relative weighting reflects the philosophy articulated in ESSAY.md:

- **Insight Depth** (Tasks 3.1, 3.2): 25% weight — The most important dimension; deep insight is the foundation of genuine innovation
- **Conceptual Novelty** (Tasks 1.1, 1.2): 20% weight — Novel concepts create new categories
- **First-Principles Thinking** (Tasks 5.1, 5.2): 20% weight — Reasoning from fundamentals generates durable innovation
- **Technical/Business Model Innovation** (Tasks 2.1, 2.2): 20% weight — Innovation in mechanism enables differentiation
- **Cliché Avoidance** (Tasks 4.1, 4.2): 15% weight — Signals genuine thinking but is more about expression than substance

Within each dimension, tasks are weighted equally.

---

## Implementation Notes

### Input Handling

Each task receives the startup idea in its native format (text, image, audio, video, or composite). The task prompts should be written to handle any modality, instructing the evaluator to assess the idea as presented regardless of format.

### Response Design

Tasks use either binary (LOW/HIGH or similar) or 4-level response scales:
- Binary scales are used when the distinction is categorical rather than gradated
- 4-level scales are used when meaningful intermediate positions exist

### Score Computation

Each task outputs a normalized score in [0, 1]:
- Binary tasks: 0.0 for the low response, 1.0 for the high response
- 4-level tasks: 0.0, 0.33, 0.67, 1.0 for the four levels

The final score aggregates these using the dimension weights described above.
