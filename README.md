# Beamforming-LLM: Semantic Spatial Recall of Missed Conversations

**Beamforming-LLM** is a research prototype that enables users to semantically recall conversations they may have missed in multi-speaker environments. It combines spatial audio processing using beamforming with Whisper ASR and Retrieval-Augmented Generation (RAG) via large language models (LLMs). Users can query the system in natural language to understand what was said in overlapping conversations.

### 🧾 What the System Outputs

The system produces:
- ✅ **Contrastive natural language summaries** of attended vs. missed conversations
- 📍 **Direction metadata** (e.g., left, right, front) indicating spatial origin of speech
- ⏱️ **Timestamps** for each conversation segment
- 🔊 **Audio playback snippets** for both target and non-target streams

This enables intuitive memory-like re-engagement with multi-party conversations, making it useful for meetings, social settings, and assistive recall applications.

---

## 🧠 Paper Overview

In real-world social or professional settings—such as dinner tables, meetings, or poster sessions—we often focus on one conversation and miss others happening simultaneously. Beamforming-LLM captures and separates these spatial conversations and enables natural language recall of what was missed.

Key technologies:
- **Beamforming** for directional audio separation
- **Whisper ASR** for transcription and timestamping
- **LLM-RAG** for semantic retrieval and summarization (via GPT-4o-mini)
- **FAISS** for fast vector-based retrieval

---

## 📁 Notebooks

### `1. Beamforming.ipynb`
Fits beamforming filters and separates multi-channel audio into spatially distinct `.wav` files using:
- MVDR beamforming
- Direction of Arrival (DOA) estimation via Pyroomacoustics

### `2. Beamforming-LLM.ipynb`
Integrates the full pipeline:
- Transcribes separated audio with Whisper
- Chunks and embeds text with sentence transformers
- Stores embeddings in FAISS
- Accepts natural language queries
- Retrieves and filters relevant segments using GPT-4o-mini
- Summarizes what was missed based on temporal-spatial alignment

### `3. Evaluation.ipynb`
Quantitatively evaluates the effectiveness of beamforming using:
- PESQ (Perceptual Evaluation of Speech Quality)
- STOI (Short-Time Objective Intelligibility)
- Comparison of scores before and after beamforming

---

## 📄 Citation & Preprint  

This work is described in the following preprint:  

**Beamforming-LLM: What, Where and When Did I Miss?**  
Vishal Choudhari  
*arXiv preprint, 2025.*  
[![arXiv](https://img.shields.io/badge/arXiv-2509.06221-b31b1b.svg)](https://arxiv.org/abs/2509.06221)

If you use or build on this work, please cite it as:  

```bibtex
@article{choudhari2025beamformingllm,
      title={Beamforming-LLM: What, Where and When Did I Miss?}, 
      author={Vishal Choudhari},
      year={2025},
      eprint={2509.06221},
      archivePrefix={arXiv},
      primaryClass={eess.AS},
      url={https://arxiv.org/abs/2509.06221}, 
}
