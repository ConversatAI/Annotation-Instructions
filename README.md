# Instructions to Annotators for Dataset Quality Assessment

## 1. Purpose of the Annotation Task

The objective of this annotation task is to assess the quality of the TopicGuidedChat (TGC) dataset and to compare it against the Multi-Session Chat (MSC) dataset. The evaluation focuses on the quality of generated conversational turns, speaker-specific knowledge graphs, and memory-grounded Question Answer (QA) pairs.

Annotators were asked to assess:

- Conversational turns
- Knowledge graphs derived from MSC conversations
- Question Answer (QA) pairs generated from new conversational turns or speaker-specific knowledge graphs

Annotators should evaluate the correctness and structural quality of the data, rather than expressing personal preferences or stylistic judgments.

---

## 2. Annotator Background and Preparation

Four annotators participated in the human evaluation. All annotators were NLP researchers with prior experience in Natural Language Processing, conversational AI systems, conversational datasets, or Large Language Model evaluation. None of the annotators participated in developing AgenticAI-DialogGen or constructing the TGC dataset.

Before beginning the annotation task, annotators were provided with:

- Written definitions of all evaluation metrics
- Scoring instructions using a standardized 1–5 Likert scale
- Examples illustrating all score levels from 1 to 5
- A 10-instance calibration round containing example annotations

Annotators completed the calibration round independently before evaluating the actual samples. The calibration round was used only to familiarize annotators with the scoring criteria and was not included in the final reported results.

---

## 3. Annotation Procedure

Each sampled item was independently evaluated by four annotators. Annotators worked independently without discussion or collaboration during scoring.

Conversational turns were evaluated for both MSC and TGC. During conversational turn evaluation, annotators were not informed whether a sample originated from a human-written or generated dataset. Knowledge graph and Question Answer pair evaluations were conducted only for TGC, because MSC does not provide these structured components.

Annotators assigned integer scores from 1 to 5 for each evaluation criterion, where 1 indicates very poor quality and 5 indicates excellent quality. Final reported scores were computed by first averaging annotator ratings for each sampled instance and then aggregating scores across all sampled instances for each evaluation metric. Human evaluation results are reported as mean ± standard deviation.

### 3.1 Additional Information

- Annotators should not penalize stylistic variation unless it negatively affects clarity, coherence, correctness, informativeness, factual grounding, or conversational realism.
- All speaker identities are anonymized and abstract.
- No real personal information is present in any sample.

---

## 4. Data Presented to Annotators

Depending on the evaluation type, annotators were shown one or more of the following.

### 4.1 Conversational Turns (TGC and MSC)

- A complete multi-turn conversation between two speakers.
- Speaker identifiers were anonymized and abstract.
- No metadata about dataset origin was revealed during annotation.

### 4.2 Knowledge Graphs (TGC only)

- A set of subject–relation–object triples derived from MSC dataset conversations.
- Knowledge triples were grouped by topic and speaker.

### 4.3 QA Pairs (TGC only)

- A question and its corresponding answer.
- Questions involve speaker1 asking about their prior events or preferences, while speaker2 provides brief factual responses.
- Questions are grounded in either short-term conversational turns or long-term speaker knowledge graphs of speaker1.

---

## 5. Scoring Scale

All metrics are rated using a 1–5 Likert scale.

Annotators should assign scores based on the severity, frequency, and impact of observed issues. The score should reflect the quality of the sample with respect to the specific metric being evaluated.

| Score | Interpretation |
|---|---|
| 1 | Very poor quality. The sample contains major issues and is largely unreliable, unsupported, incoherent, irrelevant, or unsuitable. |
| 2 | Poor quality. The sample contains several noticeable issues that substantially affect quality, although some useful content may remain. |
| 3 | Acceptable quality. The sample is usable but contains clear weaknesses, i.e., partial incompleteness, repetition, minor inconsistency, limited informativeness, ambiguity, or weak grounding. |
| 4 | Good quality. The sample is mostly strong, with only minor issues that do not significantly affect interpretation. |
| 5 | Excellent quality. The sample is highly accurate, coherent, relevant, natural, informative, and well-grounded, with no major issues. |

Annotators should not treat the scale as a personal preference rating.

A score of 5 should be reserved for samples that are consistently strong under the specific evaluation metric. A sample should not receive a 5 if it contains noticeable repetition, unsupported information, major ambiguity, unnatural phrasing, weak contextual grounding, or structural weakness.

---

## 6. Evaluation Metrics and Definitions

## 6.1 Conversational Turn Evaluation

Annotators rated each conversation using the following five metrics:

1. Topic Consistency
2. Factual Correctness
3. Completeness
4. Coherence
5. Naturalness

---

### 6.1.1 Topic Consistency

Topic Consistency measures whether conversational turns remain focused on a coherent topic throughout the interaction.

| Score | Description |
|---|---|
| 1 | The conversational turns have no stable topic, or it frequently shifts to unrelated topics, making the main topic unclear. |
| 2 | The conversational turns contain several topic shifts that noticeably weaken topical focus. |
| 3 | The conversational turns remain partly focused on the main topic but include some topic drift or loosely connected content. |
| 4 | The conversational turns mostly stay on topic, with only minor digressions that do not disrupt the overall topic. |
| 5 | All or nearly all conversational turns are clearly aligned with the main topic, with no meaningful irrelevant digressions. |

#### Examples

| Score | Example |
|---|---|
| 1 | A conversation begins with cooking but abruptly shifts to politics, finance, and travel without meaningful transitions. |
| 2 | A conversation about cooking repeatedly moves into unrelated personal activities, making the cooking topic difficult to follow. |
| 3 | A conversation about cooking mostly discusses food, but several conversational turns mention unrelated hobbies or plans before returning to cooking. |
| 4 | A conversation about cooking mostly discusses recipes, ingredients, and food preferences, with one minor digression that still feels loosely connected. |
| 5 | A conversation about cooking consistently discusses recipes, ingredients, cooking methods, food preferences, and related experiences throughout. |

---

### 6.1.2 Factual Correctness

Factual Correctness measures whether statements are factually accurate, semantically plausible, and internally consistent within the conversational context.

| Score | Description |
|---|---|
| 1 | Conversational turns contain major contradictions, hallucinated information, unsupported claims, or implausible statements. |
| 2 | Conversational turns contain several factual or semantic issues that reduce reliability. |
| 3 | Conversational turns are mostly understandable but contain minor inconsistencies, vague factual grounding, or questionable claims. |
| 4 | Conversational turns are factually sound overall, with only minor issues that do not substantially affect interpretation. |
| 5 | Conversational turns are factually correct or plausibly correct within the given context, with no contradictions or implausible claims. |

#### Examples

| Score | Example |
|---|---|
| 1 | A speaker claims they are allergic to peanuts and later says they eat peanut butter every day without clarification. |
| 2 | A speaker states several facts that conflict with earlier conversational turns, making the information unreliable. |
| 3 | A speaker says they placed fifth in a race in one conversational turn and sixth in another, but the inconsistency does not fully break the conversation. |
| 4 | A conversation contains mostly consistent facts, with one minor vague or imprecise statement that does not affect the main meaning. |
| 5 | A speaker consistently states, “I placed sixth in the 100m race,” and this information remains unchanged across the conversation. |

---

### 6.1.3 Completeness

Completeness evaluates whether conversational turns adequately respond to prior conversational turns and meaningfully develop the interaction.

| Score | Description |
|---|---|
| 1 | Conversational turns are mostly vague, incomplete, irrelevant, or fail to address preceding conversational turns. |
| 2 | Conversational turns often address the preceding conversational turn only partially and provide limited useful information. |
| 3 | Conversational turns are generally relevant but may be shallow, repetitive, or only partially developed. |
| 4 | Conversational turns mostly address preceding conversational turns and usually provide meaningful information. |
| 5 | Conversational turns directly address preceding conversational turns and consistently contribute meaningful, informative, and well-developed content. |

#### Examples

| Score | Example |
|---|---|
| 1 | Speaker 1 asks, “How do you make pasta sauce?” and Speaker 2 replies, “That sounds good,” without answering. |
| 2 | Speaker 1 asks about pasta sauce, and Speaker 2 replies, “I use sauce from a jar,” without explaining anything further. |
| 3 | Speaker 1 asks about pasta sauce, and Speaker 2 gives a brief but limited answer, i.e., “I use tomatoes, garlic, and herbs.” |
| 4 | Speaker 2 answers with useful details, i.e., “I cook tomatoes with garlic, onion, olive oil, and herbs for about twenty minutes.” |
| 5 | Speaker 2 gives a complete and informative answer with ingredients, cooking steps, and a personal tip, while clearly responding to the question. |

---

### 6.1.4 Coherence

Coherence measures logical flow and semantic continuity between consecutive conversational turns.

| Score | Description |
|---|---|
| 1 | Conversational turns are frequently disconnected, contradictory, or unrelated to preceding turns. |
| 2 | Several transitions are abrupt or weakly connected, making the conversation difficult to follow. |
| 3 | Conversational turns are generally understandable but contain some loose connections, abrupt transitions, or repetitive progression. |
| 4 | Conversational turns mostly connect naturally and progress logically, with only minor discontinuities. |
| 5 | Conversational turns connect naturally and progress logically with strong semantic continuity throughout. |

#### Examples

| Score | Example |
|---|---|
| 1 | Speaker 1 discusses cooking, Speaker 2 responds about car repairs, and the next turn moves to exam results without transition. |
| 2 | The conversation has some connected turns, but several responses ignore the immediately preceding turn. |
| 3 | The conversation is understandable, but some turns feel loosely connected or repeat the same idea without progressing. |
| 4 | The conversation mostly flows naturally from one idea to the next, with only a minor abrupt transition. |
| 5 | The conversation progresses smoothly from hobbies to specific activities, personal experiences, and follow-up questions. |

---

### 6.1.5 Naturalness

Naturalness assesses whether the conversation feels human-like, fluent, varied, and realistic.

| Score | Description |
|---|---|
| 1 | The conversational turns are robotic, unnatural, and do not sound like realistic human conversation. |
| 2 | The conversational turns are understandable, but they are repetitive and strongly formulaic. |
| 3 | The conversational turns are fluent and understandable, but they feel generic and slightly artificial. |
| 4 | The conversational turns are mostly natural, relevant, and conversational, with only minor generic phrasing. |
| 5 | The conversational turns are fluent, specific, realistic, and human-like. They add personal experience and naturally continue the conversation. |

#### Examples

| Score | Example |
|---|---|
| 1 | Speaker 1: “I tried making pasta yesterday.” Speaker 2: “That is good. Cooking is good. Pasta is food. Food is good |
| 2 | Speaker 1: “I tried making pasta yesterday.” Speaker 2: “That sounds great. I also like pasta. Pasta is great. Cooking pasta is also great.” |
| 3 | Speaker 1: “I tried making pasta yesterday.” Speaker 2: “That sounds nice. I like pasta too. It is fun to cook food at home.” |
| 4 | Speaker 1: “I tried making pasta yesterday.” Speaker 2: “Nice, homemade pasta is always worth the effort. Did you make the sauce yourself as well?” |
| 5 | Speaker 1: “I tried making pasta yesterday.” Speaker 2: “That’s great. What kind did you make? I tried making ravioli once, but sealing the edges properly was harder than I expected.” |

---

## 6.2 Knowledge Graph Evaluation

Annotators evaluated speaker-specific knowledge graphs using the following three metrics:

1. Topic Consistency
2. Factual Correctness
3. Relevance

---

### 6.2.1 Topic Consistency

Topic Consistency measures whether extracted triples align with the assigned topic.

| Score | Description |
|---|---|
| 1 | Most triples are unrelated to the assigned topic. |
| 2 | Several triples are unrelated or only weakly connected to the topic. |
| 3 | Some triples align with the topic, but noticeable irrelevant or loosely related triples are present. |
| 4 | Most triples clearly relate to the topic, with only minor irrelevant information. |
| 5 | All triples clearly relate to the assigned topic. |

#### Examples

For the assigned topic cooking:

| Score | Example |
|---|---|
| 1 | (speaker1, works as, software engineer), (speaker1, plans to, travel next month), (speaker1, owns, a bicycle) |
| 2 | (speaker1, likes, cooking pasta), (speaker1, works as, software engineer), (speaker1, owns, a bicycle) |
| 3 | (speaker1, likes, cooking pasta), (speaker1, prefers, spicy food), (speaker1, enjoys, watching movies) |
| 4 | (speaker1, likes, cooking pasta), (speaker1, prefers, spicy food), (speaker1, shops for fresh ingredients) |
| 5 | (speaker1, likes, cooking pasta), (speaker1, prefers, spicy food), (speaker1, cooks, dinner on weekends) |

---

### 6.2.2 Factual Correctness

Factual Correctness measures whether triples accurately represent information expressed or strongly implied in the conversation.

| Score | Description |
|---|---|
| 1 | Most triples misrepresent, hallucinate, contradict, or incorrectly infer conversational information. |
| 2 | Several triples contain factual inaccuracies, unsupported information, or distorted relations. |
| 3 | Some triples are correct, but others are overly broad, imprecise, or weakly grounded. |
| 4 | Most triples accurately represent conversational facts, with only minor inaccuracies or imprecision. |
| 5 | All triples correctly represent conversational facts without semantic distortion or hallucination. |

#### Examples

Assume the conversation states: “speaker1 likes jerk chicken and cooks it on weekends.”

| Score | Example |
|---|---|
| 1 | (speaker1, dislikes, jerk chicken), (speaker1, cooks, fish every day) |
| 2 | (speaker1, likes, fish), (speaker1, cooks, every day), (speaker1, dislikes, chicken) |
| 3 | (speaker1, likes, chicken), (speaker1, cooks, sometimes) |
| 4 | (speaker1, likes, jerk chicken), (speaker1, cooks, on weekends), with one minor imprecise triple such as (speaker1, likes, chicken) |
| 5 | (speaker1, likes, jerk chicken), (speaker1, cooks, jerk chicken on weekends) |

---

### 6.2.3 Relevance

Relevance measures whether triples capture meaningful, informative, and useful speaker-specific knowledge.

| Score | Description |
|---|---|
| 1 | Triples are mostly trivial, generic, repetitive, or uninformative. |
| 2 | Several triples are weakly useful, redundant, or not meaningful for representing speaker knowledge. |
| 3 | Triples contain some useful information, but there is noticeable redundancy or limited informativeness. |
| 4 | Most triples are meaningful and useful, with only minor redundancy or weakly informative content. |
| 5 | Triples capture salient, informative, and useful speaker-specific facts with no redundancy. |

#### Examples

| Score | Example |
|---|---|
| 1 | (speaker1, is, human), (speaker1, speaks, English), (speaker1, has, thoughts) |
| 2 | (speaker1, likes, food), (speaker1, eats, meals), (speaker1, talks about, cooking) |
| 3 | (speaker1, likes, jerk chicken), (speaker1, enjoys, jerk chicken), (speaker1, prefers, jerk chicken) |
| 4 | (speaker1, likes, jerk chicken), (speaker1, cooks, on weekends), (speaker1, enjoys, chicken) |
| 5 | (speaker1, favourite dish, jerk chicken), (speaker1, cooks, on weekends), (speaker1, prefers, spicy food) |

---

## 6.3 Question Answer Pair Evaluation

Annotators evaluated Question Answer pairs using the following two metrics:

1. Factual Correctness
2. Relevance

---

### 6.3.1 Factual Correctness

Factual Correctness measures whether the question and answer pair is factually correct, contextually supported, and logically aligned with the provided conversational or knowledge graph context.

| Score | Description |
|---|---|
| 1 | The QA pair is incorrect, unsupported, contradictory, misleading, or not grounded in the provided context. |
| 2 | The QA pair is mostly unsupported or contains significant factual errors in either the question or the answer. |
| 3 | The QA pair is partly correct but incomplete, imprecise, ambiguous, or weakly grounded. |
| 4 | The QA pair is mostly correct and grounded, with only minor incompleteness, imprecision, or unsupported extra detail. |
| 5 | The QA pair is fully correct, contextually supported, specific, logically aligned, and unambiguous. |

#### Examples

Assume the provided context states:

“speaker1 likes jerk chicken and enjoys cooking it on weekends.”

| Score | Example | Reason |
|---|---|---|
| 1 | Q: “What seafood do I like?” A: “Jerk chicken.” | The question contains an unsupported assumption, and the answer does not logically match the question. |
| 2 | Q: “What dish do I dislike?” A: “Jerk chicken.” | The question contradicts the context because the context says the speaker likes jerk chicken. |
| 3 | Q: “What food do I like?” A: “Chicken.” | The pair is partly grounded, but the question is broad and the answer is imprecise because the context specifically states “jerk chicken.” |
| 4 | Q: “What chicken dish do I like?” A: “Jerk chicken with rice.” | The question is grounded and the main answer is correct, but the answer adds an unsupported extra detail. |
| 5 | Q: “What dish do I like to cook?” A: “Jerk chicken.” | The question is answerable from the context, and the answer is fully correct, specific, grounded, and unambiguous. |

---

### 6.3.2 Relevance

Relevance measures whether the question meaningfully probes speaker-specific memory or contextual information.

| Score | Description |
|---|---|
| 1 | The question is unrelated, unsupported, vague, or not answerable from the provided context. |
| 2 | The question is weakly related but mostly trivial, generic, repetitive, or poorly grounded. |
| 3 | The question is related to the context but focuses on less important or weakly informative details. |
| 4 | The question is meaningful and grounded, with only minor issues in specificity or importance. |
| 5 | The question targets meaningful, contextually grounded, speaker-specific information that is useful for memory-based evaluation. |

#### Examples

Assume the provided context states: “speaker1 likes jerk chicken and enjoys cooking it on weekends.”

| Score | Example |
|---|---|
| 1 | Question: “What is my favourite colour?” |
| 2 | Question: “Do I like things?” |
| 3 | Question: “What kind of food do I like?” |
| 4 | Question: “What chicken dish do I like?” |
| 5 | Question: “What dish do I like to cook on weekends?” |
