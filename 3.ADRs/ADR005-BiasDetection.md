# Bias Detection and Mitigation Strategies

## Context
This ADR addresses the crucial aspect of bias detection and mitigation within the ClearView platform. It's essential to ensure the AI model and overall system minimize bias throughout the hiring process.

## Decision: 
We will adopt a combined approach.

We will incorporate debiasing techniques during AI model training to minimize bias based on factors like gender, race, or age. Additionally, we will implement a human review process where qualified personnel can assess samples of the anonymized candidate profiles and S.M.A.R.T goals before they are presented to employers. This adds an extra layer of control to mitigate potential biases.

## Status
Proposed

## Options
 * Debiasing Techniques: Implement debiasing techniques within the AI model training process to minimize bias based on protected characteristics.
 * Human-in-the-Loop Review: Integrate human review of AI-generated candidate matches and S.M.A.R.T goals to catch potential biases before presenting them to employers.

## Consequences
Debiasing Techniques: Reduces bias within the AI model but may not eliminate it entirely.
Human-in-the-Loop Review: Increases accuracy and reduces bias but introduces additional cost.

## Useful links
- [Architectural Decision Record 3 - AI Model Selection and Training](https://github.com/octaviaah/ClearView/blob/main/3.ADRs/ADR003-AIModelSelection.md)
