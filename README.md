# VotingBooklets

This repository contains code and data files accompanying the paper:

**"How Good is AI on Swiss Voting Booklets? A Multilingual OCR and Alignment Benchmark"**
Elina Stüssi and Jannis Vamvas, SwissText 2026

[Read the paper](https://aclanthology.org/2026.swisstext-1.22.pdf)

---

## Overview

Swiss voting booklets are multilingual government documents distributed to citizens before each federal vote. This project benchmarks AI systems on two tasks: optical character recognition (OCR) and cross-lingual alignment of these booklets. The repository includes all experimental code, OCR outputs, alignment experiments, gold-standard annotations, and the final aligned corpus.

---

## Repository Structure

```
VotingBooklets/
├── OCR/
├── gold_files/
├── full_corpus-gemini-ocr-2.5-flash-lite/
├── alignment_experiments/
└── aligned_corpus/
```

### `OCR/`

Code and output files for three OCR pipelines:

- **Pytesseract** — classical open-source OCR baseline
- **Gemini 2.5 Flash Lite** — direct AI-based OCR
- **Post-OCR correction** — Gemini 2.5 Flash Lite applied on top of Pytesseract output to correct recognition errors

### `gold_files/`

Gold-standard annotations for both OCR and alignment, covering three voting dates:

- `1977-06-12`
- `1985-12-01`
- `2007-03-11`

These files form the **VotingBooklets-Diamond** corpus, also available on Hugging Face:
[eljuanina/VotingBooklets-Diamond-v1](https://huggingface.co/datasets/eljuanina/VotingBooklets-Diamond-v1)

### `full_corpus-gemini-ocr-2.5-flash-lite/`

Gemini 2.5 Flash Lite OCR output for all voting booklets in the VotingBooklets corpus, organized by language (German, French, Italian).

### `alignment_experiments/`

Code for the alignment experiments conducted to identify the best method for cross-lingual alignment of voting booklet content.

### `aligned_corpus/`

The full aligned corpus, containing:

- Raw PDFs of all voting booklets in the VotingBooklets corpus
- Voting booklet content aligned per voting date, across all languages

This corresponds to the **VotingBooklets** corpus on Hugging Face:
[eljuanina/VotingBooklets-v1](https://huggingface.co/datasets/eljuanina/VotingBooklets-v1)

---

## Datasets on Hugging Face

| Dataset | Description | Link |
|---|---|---|
| VotingBooklets-v1 | Full aligned corpus | [eljuanina/VotingBooklets-v1](https://huggingface.co/datasets/eljuanina/VotingBooklets-v1) |
| VotingBooklets-Diamond-v1 | Gold-standard OCR and alignment annotations | [eljuanina/VotingBooklets-Diamond-v1](https://huggingface.co/datasets/eljuanina/VotingBooklets-Diamond-v1) |

---

## Citation

If you use this code, data, or the associated datasets, please cite:

```bibtex
@inproceedings{stussi-vamvas-2026-good,
    title = "How Good is {AI} on {S}wiss Voting Booklets? A Multilingual {OCR} and Alignment Benchmark",
    author = {St{\"u}ssi, Elina  and
      Vamvas, Jannis},
    editor = "Sennrich, Rico  and
      Schneider, Gerold  and
      Ellendorff, Tilia  and
      Gao, Yingqiang  and
      Vamvas, Jannis  and
      Cieliebak, Mark",
    booktitle = "Proceedings of the 11th Edition of the {S}wiss Text Analytics Conference",
    month = jun,
    year = "2026",
    address = "Zurich, Switzerland",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2026.swisstext-1.22/",
    pages = "232--242"
}
```


