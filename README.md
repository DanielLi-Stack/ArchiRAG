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

## Inference

```
python inference.py \
  --dataset ElecInsp-QA \
  --base_model Qwen2.5-VL-7B \
  --model_path ckpts/elecvision_r1 \
  --enable_rag \
  --temperature 1.0 \
  --max_new_tokens 1024
```
## Train

```
# Stage 1: supervised fine-tuning (SFT)
python train_sft.py \
  --dataset ElecInsp-QA \
  --base_model Qwen2.5-VL-7B \
  --freeze_visual true \
  --lora_r 8 \
  --lora_alpha 32 \
  --lora_dropout 0.05 \
  --max_seq_len 8192 \
  --epochs 3 \
  --lr 5e-5

# Stage 2: GRPO post-training
python train_grpo.py \
  --dataset ElecInsp-QA \
  --base_model Qwen2.5-VL-7B \
  --init_ckpt ckpts/elecvision_sft \
  --max_image_resolution 1280x784 \
  --num_generations 8 \
  --temperature 1.0 \
  --max_completion_len 1024 \
  --epochs 1 \
  --lr 1e-6 \
  --per_device_batch_size 4
