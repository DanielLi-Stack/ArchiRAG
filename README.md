# ArchiRAG: Toward Evidence-Grounded Architectural Review with Multimodal Retrieval-Augmented Reasoning
> 
Abstract: Automated domain-specific knowledge question answering in the architecture, engineering, and construction (AEC) domain relies on heterogeneous multi-modal documents, including codes, technical specifications, drawings, and performance reports. However, existing architectural AI methods still face significant challenges, as they struggle with text-graphic misalignment, multi-step compliance reasoning, and evidence scattered across multiple documents. To bridge this gap, we construct ArchInstruct-QA, a dataset comprising architecture-oriented question-answer pairs. Building on this dataset, we propose ArchiRAG, a multi-modal retrieval-augmented framework that integrates multi-modal evidence units, adaptive hybrid retrieval, multi-hop evidence planning, and role-specific agents for grounded answer generation. ArchiRAG outperforms graph-based retrieval methods and lightweight RAG baselines in evidence alignment, retrieval precision, and long-context reasoning consistency, demonstrating its potential for automated architectural review workflows.

[**Paper**]() | [**Project Page**]() | [**Model Weights**]() | [**Huggingface Demo**]() |

![img](assets/01.png)
*Figure 1) Motivation of ArchInstruct-QA and ArchiRAG.*<br><br>

![img](assets/021.png)
*Figure 2) Overall Research Flowchart.*<br><br>

![img](assets/03.png)
*Figure 3) Construction Pipeline of the ArchInstruct-QA Dataset.*<br><br>

![img](assets/04.png)
*Figure 4) Document Base and Knowledge Coverage of ArchInstruct-QA.*<br><br>

![img](assets/05.png)
*Figure 5) Distribution of ArchInstruct-QA by Evidence Modality and Reasoning Type.*<br><br>

![img](assets/061.png)
*Figure 6) The ArchiRAG Framework.*<br><br>

![img](assets/07.png)
*Figure 7) Role-Specific Multi-Agent Reasoning Workflow in ArchiRAG.*<br><br>

## Table 2. Performance comparison of text-based RAG methods on architectural QA tasks

| Method | Avg. Score (0-10) | F1 (%) | Avg. Time (s) |
|---|---:|---:|---:|
| PathRAG_BGE-M3 [10] | 7.4216 | 65.14 | 35.8072 |
| PathRAG_JINA-EMBEDDINGS-V3 [10] | 7.7029 | 68.27 | 30.6849 |
| LightRAG_BGE-M3 [11] | 7.9824 | 71.13 | 57.3185 |
| LightRAG_JINA-EMBEDDINGS-V3 [11] | 8.0647 | 72.48 | 52.1064 |
| GraphRAG_BGE-M3 [12] | 5.6918 | 49.26 | 262.4387 |
| GraphRAG_JINA-EMBEDDINGS-V3 [12] | 5.2849 | 45.68 | 521.7469 |
| SimilarityRAG_BGE-M3 [9] | 7.1046 | 62.17 | 14.9238 |
| SimilarityRAG_JINA-EMBEDDINGS-V3 [9] | 7.2963 | 63.89 | 17.8426 |
| **ArchiRAG-Text_BGE-M3** | **8.3517** | **74.16** | 24.6325 |
| ArchiRAG-Text_JINA-EMBEDDINGS-V3 | 7.8886 | 70.69 | 27.3481 |


## ArchiRAG Representative Evidence-Grounded Cases

![img](assets/08.png)
*Figure 8) Representative ArchiRAG case for human-scale design parameter extraction.*<br><br>

![img](assets/09.png)
*Figure 9) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/10.png)
*Figure 10) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/11.png)
*Figure 11) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/12.png)
*Figure 12) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/13.png)
*Figure 13) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/14.png)
*Figure 14) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/15.png)
*Figure 15) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/16.png)
*Figure 16) Representative ArchiRAG case for code definition retrieval.*<br><br>

![img](assets/17.png)
*Figure 17) Representative ArchiRAG case for code definition retrieval.*<br><br>

## TODO List

- [x] Release part of ArchiRAG dataset. 
- [ ] Release ArchiRAG inference code and pretrain weights.
- [ ] Upload ArchiRAG training dataset.
- [ ] Release ArchiRAG code.

