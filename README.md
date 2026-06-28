# LLM Watermark Semantic Rewrite Attacks

> Reproducing and evaluating the robustness of LLM watermarking against paraphrasing and extreme semantic rewriting attacks.

---

## Overview

This project studies how robust current LLM watermarking techniques are when the generated text is rewritten while keeping the original meaning.

The work starts by reproducing the watermarking algorithm proposed by Kirchenbauer et al. to verify that the implementation behaves similarly to the original paper. After reproducing the baseline results, two attack scenarios are evaluated. The first experiment applies a standard paraphrasing attack, while the second performs a much stronger semantic rewrite that changes sentence structure, wording, and writing style without intentionally changing the meaning.

The goal is not to design a new watermarking algorithm, but to understand how existing watermark detectors behave under increasingly stronger semantic-preserving transformations.

---

## Motivation

Watermarking has become one of the main approaches for identifying AI-generated text. However, most generated content is often edited before publication. This raises an important research question:

**Can watermark signals survive after the text has been rewritten multiple times while preserving its meaning?**

This repository investigates that question through a series of controlled experiments.

---

## Project Structure

```
.
├── notebooks/
├── src/
├── data/
├── results/
├── figures/
└── paper/
```

---

## Experiments

### Experiment 1 — Baseline Reproduction

The first experiment reproduces the original watermarking algorithm and evaluates its detection performance on watermarked text. The purpose is to verify that the implementation closely follows the original publication before performing additional experiments.

---

### Experiment 2 — Paraphrasing Attack

The second experiment evaluates how watermark detection changes after applying a semantic paraphrasing model.

Each generated text is paraphrased and then evaluated again using the same watermark detector. Detection accuracy and z-score changes are compared with the baseline.

---

### Experiment 3 — Extreme Semantic Rewrite Attack

The final experiment extends previous work by applying a much stronger semantic rewriting strategy.

Instead of simple paraphrasing, the text is aggressively rewritten by modifying sentence structure, vocabulary, writing style, and information ordering while attempting to preserve the original meaning.

The rewritten text is then evaluated again using the watermark detector to measure how much the watermark signal changes.

---

## Evaluation

The experiments compare:

- Watermark detection rate
- Average z-score
- z-score reduction after rewriting
- Detection success and failure cases

The evaluation is performed on hundreds of generated samples using the same detector configuration across all experiments.

---

## Repository Contents

- Complete experiment notebooks
- Watermark detection source code
- Experimental results
- Reproducible evaluation pipeline
- Paper source and figures

---

## Current Status

-  Baseline reproduction completed
-  Paraphrasing attack completed
-  Extreme semantic rewrite evaluation completed
-  Paper preparation in progress

---

## Citation

If you find this repository useful for your research, please consider citing both the original watermarking paper and this repository.
