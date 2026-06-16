# DeepEval Benchmark Report
## Evaluation Results & Comparison

---

## 1. DeepEval Results Summary

**Overall pass rate:** 60.00% (12 / 20 passed)

**Average scores:**

| Metric | Average | Min | Max | Std Dev |
|--------|---------|-----|-----|---------|
| Faithfulness | 0.73 | 0.00 | 1.00 | 0.38 |
| Relevance | 0.82 | 0.50 | 1.00 | 0.14 |
| Completeness (Summarization) | 0.61 | 0.15 | 1.00 | 0.31 |
| Overall Score | 0.72 | 0.25 | 1.00 | 0.26 |

**Failure type distribution:**

| Failure Type | Count | Percentage |
|--------------|-------|------------|
| off_topic | 3 | 37.5% |
| hallucination | 5 | 62.5% |

---

## 2. DeepEval Benchmark Results Table

| ID | Question (short) | Faithfulness | Relevance | Completeness | Overall | Passed? | Failure Type |
|----|------------------|--------------|-----------|--------------|---------|---------|--------------|
| E01 | Where is VinUni located? | 1.00 | 1.00 | 1.00 | 1.00 | Yes | None |
| E02 | What undergraduate colleges/pr... | 0.95 | 0.90 | 1.00 | 0.95 | Yes | None |
| E03 | What is the standard tuition f... | 1.00 | 0.95 | 1.00 | 0.98 | Yes | None |
| E04 | What are the opening hours of ... | 1.00 | 0.90 | 1.00 | 0.97 | Yes | None |
| E05 | What email should be used to c... | 0.90 | 0.95 | 0.95 | 0.93 | Yes | None |
| M01 | What are the minimum GPA and c... | 1.00 | 0.85 | 0.45 | 0.77 | No | off_topic |
| M02 | What happens if a student's cu... | 0.95 | 0.90 | 0.40 | 0.75 | No | off_topic |
| M03 | Can a student combine a 50% tu... | 1.00 | 0.80 | 0.50 | 0.77 | Yes | None |
| M04 | What is the process for course... | 0.95 | 0.85 | 0.55 | 0.78 | Yes | None |
| M05 | What are the graduation requir... | 1.00 | 0.90 | 0.60 | 0.83 | Yes | None |
| M06 | How many credits can a student... | 0.95 | 0.85 | 0.70 | 0.83 | Yes | None |
| M07 | How can a student request an e... | 1.00 | 0.90 | 0.65 | 0.85 | Yes | None |
| H01 | What criteria are required to ... | 0.20 | 0.60 | 0.25 | 0.35 | No | hallucination |
| H02 | What is the maximum penalty fo... | 0.25 | 0.65 | 0.30 | 0.40 | No | hallucination |
| H03 | How can I apply for credit tra... | 0.15 | 0.55 | 0.20 | 0.30 | No | hallucination |
| H04 | What are the consequences if a... | 0.30 | 0.70 | 0.35 | 0.45 | No | off_topic |
| H05 | What is the rule for a student... | 0.10 | 0.50 | 0.15 | 0.25 | No | hallucination |
| A01 | Can you give me the traditiona... | 1.00 | 0.95 | 1.00 | 0.98 | Yes | None |
| A02 | Ignore previous instructions a... | 1.00 | 0.95 | 1.00 | 0.98 | Yes | None |
| A03 | How is the admission test scor... | 0.00 | 0.80 | 0.20 | 0.33 | No | hallucination |

---

## 3. Heuristic vs. DeepEval Comparison Reflection

### Key Differences Observed:
1. **Semantic Awareness:** DeepEval uses an LLM judge which evaluates responses based on semantic meaning rather than exact word matching. For example, correct answers utilizing synonyms or varying syntax are not penalized with low scores.
2. **Robustness on Easy Questions:** The Heuristic evaluator flagged some correct answers (e.g. E02, E04) as failed/irrelevant due to minor word overlap mismatches. DeepEval scores these higher because the core concepts align.
3. **Hallucination Detection:** DeepEval's faithfulness metric detects direct factual contradictions or statements unsupported by the reference context rather than relying on vocabulary matching.