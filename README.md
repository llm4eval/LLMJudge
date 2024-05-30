# LLMJudge
Automatic Relevance Judgments for Search and Retriveal Systems

## LLMJudge Overview
The LLMJudge challenge is organized as part of the LLM4Eval workshop at SIGIR 2024. Test collections are essential for evaluating information retrieval (IR) systems. Evaluating and tuning a search system largely depends on relevance labels, which indicate whether a document is useful for a specific search and user. However, collecting relevance judgments on a large scale is costly and resource-intensive. Consequently, typical experiments rely on third-party labellers who may not always produce accurate annotations. The LLMJudge challenge aims to explore an alternative approach by using LLMs to generate relevance judgments. Recent studies have shown that LLMs can generate reliable relevance judgments for search systems. Nevertheless, it remains unclear which LLMs can match the accuracy of human labellers, which prompts are most effective, how fine-tuned open-source LLMs compare to closed-source LLMs like GPT-4, whether there are biases in synthetically generated data, and if data leakage affects the quality of generated labels. This challenge will investigate these questions, and the collected data will be released as a package to support automatic relevance judgment research in information retrieval and search.

### LLMJudge Task Design
The challenge will be, given the query and document as input, how they are relevant. Here, we use a four-point scale judgments to evaluate the relevance of the query to document as follow:

- __[3] Perfectly relevant__: The passage is dedicated to the query and contains the exact answer. 
- __[2] Highly relevant__: The passage has some answer for the query, but the answer may be a bit unclear, or hidden amongst extraneous information. 
- __[1] Related__: The passage seems related to the query but does not answer it. 
- __[0] Irrelevant__: The passage has nothing to do with the query.

The task is, by providing to the participants the datasets that include quereis, documents, and query-document file, to ask LLMs to generate a score `[0, 1, 2, 3]` indicating the relevancy of query to document.

## LLMJudge Data

### Files
Below we list the files for the challenge:

- `./data/llm4eval_document_2024.jsonl` is a JSONL file consisting of document IDs and documents (passages).
- `./data/llm4eval_query_2024.txt` is a TXT file consisting of topic ID's, as well as queries (text).
- `./data/llm4eval_dev_qrel_2024.txt` is a TXT file consisting of train/dev topic ID's and document IDs with relevance labels. It can be used for training, fine-tuning, or in-context learning.
- `./data/llm4eval_test_qrel_2024.txt` is a TXT file consisting of test topic ID's and document IDs. This is the file that the participants must use to predict the relevance judgments of each query to document and submit as the final result file.

Note that all TXT files are tab-separated.

## Evaluation
Participants’ results will then be compared in two ways after submission:
- automated evaluation metrics on human labels in the test set hidden from the participants;
- system ordering evaluation of multiple search systems on human judgments and LLM-based judgments

## Baselines/Quick Start

## Citing

## Acknowledgments
The challenge is organized as a joint effort by the University College London, Microsoft, University of Amsterdam, Univertisy of Wateloo, and University of Padua. 

## References
- Rahmani, Hossein A., Nick Craswell, Emine Yilmaz, Bhaskar Mitra, and Daniel Campos. "Synthetic Test Collections for Retrieval Evaluation." arXiv preprint arXiv:2405.07767 (2024).
- Thomas, Paul, Seth Spielman, Nick Craswell, and Bhaskar Mitra. "Large language models can accurately predict searcher preferences." arXiv preprint arXiv:2309.10621 (2023).
