# AI Model Selection and Training

## Context
This ADR focuses on choosing and training the AI model responsible for resume parsing, S.M.A.R.T goal construction, and candidate-job matching.

## Decision: 
We have decided to go with a pre-trained NLP model with fine-tuning. This approach offers a faster development cycle and leverages existing expertise within the NLP domain. We will fine-tune the chosen model with job descriptions, S.M.A.R.T goal examples, and anonymized resumes to enhance its performance for ClearView's specific tasks.

## Status
Proposed

## Options
 * Pre-trained NLP Model: Utilize a pre-trained Natural Language Processing (NLP) model and fine-tune it for resume processing and S.M.A.R.T goal generation.
 * Custom-built NLP Model: Develop a custom NLP model specifically tailored for the ClearView platform's needs.

## Consequences
Pre-trained NLP Model: Faster development, potentially lower cost, but might require significant fine-tuning for optimal performance.

## Useful links
- [C4 diagram](https://github.com/octaviaah/ClearView/blob/main/2.ArchitectureVisualization/C4Diagram.md)
