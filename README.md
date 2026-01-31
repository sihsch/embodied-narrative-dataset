# Embodied Narrative Dataset

This repository provides supplementary data for the paper submission.

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

**Path:** `data/train_data/sensor-text/`

Text narratives generated from robot sensor inputs using various LLMs.

| Model | Files | Path |
|-------|-------|------|
| Gemma2 9B | 100 | `gemma2_9b/` |
| Gemma2 27B | 50 | `gemma2_27b/` |
| LLaMA 3.1 8B | 100 | `llama31_8b/` |
| Mistral 7B | 100 | `mistral_7b/` |
| Mistral 24B | 50 | `mistral_24b/` |

Each JSON file contains: `sensor_data`, `prompt`, `target_paragraph`, and `metadata`.

---

## 2. Text Generation Results

**Path:** `data/result_data/`

| File | Description |
|------|-------------|
| `ablation_baseline_results.csv` | Ablation study and baseline comparison results |

---

## 3. Corpus Lists

**Path:** `data/train_data/book-lists-for-copora/`

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
