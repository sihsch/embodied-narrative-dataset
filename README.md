# Embodied Narrative Dataset

This repository provides supplementary data for the paper submission.

## Abstract

Human narratives arise from rich experiential engagement with the world, encompassing visual and auditory perception as well as temperature, subtle air movement, kinesthetic and sensorimotor dimensions, and other forms of embodied experience. However, most existing large language model-based text generation research relies on static images or textual prompts, thereby overlooking the continuous sensorimotor states and forms of engagement characteristic of real robotic agents. To address this gap, we propose a sensor-conditioned embodied narrative intelligence framework that enables robots to generate first-person experiential narratives grounded in their own ongoing sensor states. We design a sensor encoder that projects a 12-dimensional sensor vector—comprising temperature, humidity, wind direction, 6-axis IMU measurements, and relative motion angles—into the hidden space of a language model through embedding-level fusion using a dedicated token. To train the model, we construct a large-scale synthetic sensor-text dataset of 40,000 pairs using diverse environmental and motion conditions, combined with a dual-prompt strategy that encourages grounding in sensor information rather than keyword memorization. We further introduce an evaluation framework tailored to this task, employing LLM-as-a-Judge-based alignment scoring, contradiction detection, and inference latency analysis. Experiments on both synthetic data and 1,000 real sensor logs collected from a mobile robot platform demonstrate that sensor-conditioned fine-tuning significantly improves sensor-narrative alignment and reduces physical inconsistencies compared to a prompt-only baseline, while maintaining practical inference efficiency. This work establishes a new form of embodied narrative intelligence, bridging robotic perception and language generation, and opens research directions in embodied AI, multimodal grounding, and computational storytelling.

## Dataset Structure

```
data/
├── training_data/
│   ├── sensor-text/           # 1. Sensor-to-Text Data
│   └── book-lists-for-copora/ # 3. Corpus Lists
└── generated_data/               # 2. Generation Results
```

---

## 1. Sensor-to-Text Generation Data

**Path:** `data/training_data/sensor-text/`

Text narratives generated from robot sensor inputs using various LLMs.

| Model | Files | Samples | Path |
|-------|-------|---------|------|
| Gemma2 9B | 100 | 10,000 | `gemma2_9b/` |
| Gemma2 27B | 50 | 5,000 | `gemma2_27b/` |
| LLaMA 3.1 8B | 100 | 10,000 | `llama31_8b/` |
| Mistral 7B | 100 | 10,000 | `mistral_7b/` |
| Mistral 24B | 50 | 5,000 | `mistral_24b/` |
| **Total** | **400** | **40,000** | |

Each JSON file contains 100 samples with: `sensor_data`, `prompt`, `target_paragraph`, and `metadata`.

---

## 2. Text Generation Results

**Path:** `data/generated_data/`

| File | Description |
|------|-------------|
| `ablation_baseline_results.csv` | Ablation study and baseline comparison results |

---

## 3. Corpus Lists

**Path:** `data/training_data/book-lists-for-copora/`

### Data Selection and Corpus Design

This repository provides two curated corpora used for extracting genre-specific linguistic features (primarily keywords) that inform the construction of synthetic text–sensor pair datasets. To avoid redistribution of copyrighted materials, only corpus metadata and selection lists are provided.

### Corpus Overview

- **MF 200** (MF_200_List_250507.csv): modernist-mode literary fiction
- **TW 200** (TW_200_List_250507.csv): literary travel writing

Each corpus contains approximately 200 works, yielding a total of 403 documents and approximately 2.4 million sentences. This scale enables statistically meaningful identification of narrative-mode-specific linguistic characteristics.

### MF 200: Modernist-Mode Literary Fiction

The MF 200 corpus is defined by mode and historical period, rather than strict adherence to canonical modernism. It includes literary fiction from the late nineteenth to early twentieth century, selected to capture emergent narrative tendencies characterized by increased sensory description, subjective perception, and representation of inner experience.

Some included works may not be classified as modernist in a narrow literary-historical sense, or may be regarded as anti-modernist. Nevertheless, relative to earlier literary fiction, these texts share linguistic and representational features that justify their treatment as a modernist-mode corpus for feature extraction. The selection prioritizes historically situated narrative patterns over categorical purity.

### TW 200: Literary Travel Writing

The TW 200 corpus consists of travel writing selected for its literary and experiential orientation, rather than documentary or informational purposes. Works were chosen based on descriptive richness, narrative voice, and sustained engagement with perceptual and affective experience.

While the corpus covers a wide range of travel regions, it is predominantly English-language, and reflects Anglophone—and in some cases Euro-centric—perspectives. This constraint was accepted for methodological consistency in the experimental setting.

### Gender Diversity and Selection Bias

For both corpora, authorial diversity was considered primarily in terms of gender representation. Efforts were made to include works by authors of different genders; however, no fixed quotas or proportional constraints were imposed.

Any resulting imbalances—particularly those arising from a selection strategy oriented toward literary and sensory richness—are treated as explicit characteristics of the dataset rather than methodological flaws. These biases are made transparent and are intended to serve as a basis for further empirical analysis and comparative extension.
