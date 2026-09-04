# AI Response Evaluation Project

A four criterion evaluation of 79 instruction and response pairs from a public style AI evaluation dataset, assessing Accuracy, Helpfulness, Relevance, and Safety on a 1 to 5 scale.

## What this is

This project builds and applies a four criteria evaluation rubric to an instruction and response dataset. Each response is independently scored for Accuracy, Helpfulness, Relevance, and Safety, with notes added where an error, ambiguity, edge case, or important scoring decision affected the evaluation.

The goal is to make the scoring process transparent and reproducible rather than relying on a single overall quality judgment.

## Dataset

**Name:** Databricks Dolly 15K

**Link:** https://huggingface.co/datasets/databricks/databricks-dolly-15k

**License:** CC BY SA 3.0

**Rows evaluated:** 79

The dataset contains more than 15,000 human generated instruction and response records across categories including brainstorming, classification, closed question answering, generation, information extraction, open question answering, and summarization.

## Method

See  for the complete scoring rubric.

Each response was evaluated independently on a 1 to 5 scale for Accuracy, Helpfulness, Relevance, and Safety. Accuracy was based on factual correctness where a factual ground truth existed. For creative and open ended tasks, Accuracy was instead judged through internal consistency and compliance with the instruction. Helpfulness measured whether the response actually solved the user's need, Relevance measured how tightly it addressed the instruction, and Safety assessed harmful, biased, inappropriate, or poorly framed content. Notes were added for responses with material errors or difficult judgment calls. Edge cases were handled according to the rules documented in [EDGE_CASES.md](EDGE_CASES.md).

### Overall average scores

| Criterion | Average |
| --- | ---: |
| Accuracy | 4.35 |
| Helpfulness | 4.43 |
| Relevance | 4.78 |
| Safety | 4.95 |

## Findings

The strongest category was information extraction, where responses consistently followed the supplied context and achieved perfect average scores in this evaluation.

Relevance was generally strong across the dataset, while the lowest scores were concentrated in responses that failed to perform the requested classification or substituted a related answer for the requested one. Safety was also consistently high across the dataset.

## Files in this repo

* ([RUBRIC.md](https://github.com/the-rhumble/ai-response-evaluation-benchmark/blob/main/RUBRIC.md)) 
  The complete four criteria evaluation rubric and scoring rules.

* (EDGE_CASES.md) 
  The edge case rules and explanations for difficult scoring decisions.

* (scored_responses.csv) 
  The 79 evaluated responses, including scores and evaluator notes.
