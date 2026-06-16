[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red)]() [![VSA Reasoning](https://img.shields.io/badge/VSA%20Reasoning-Live%20Site-blue?style=for-the-badge)](https://fakeonomics.github.io/vsa-reasoning-overview/) [![GraphKAN](https://img.shields.io/badge/GraphKAN-Live%20Site-228b22?style=for-the-badge)](https://fakeonomics.github.io/graphkan-overview/)

**VSA Reasoning Live Site** · **GraphKAN Live Site**

---

# VSA Reasoning: CPU Neural Reasoner

First **learned neural reasoner** over Vector-Symbolic Architecture with **ternary weights**.  
**90% exact multi-hop QA · 16 KB resonator · <100 KB total · No LLM · No GPU**

## Overview

Classical VSA reasoning is algorithmic (not learned) and hits an ~80% accuracy ceiling due to superposition noise. We introduce three **learned components** — all with ternary or compact float weights — that break this ceiling:

**90% exact multi-hop QA** on a benchmark of 96 facts, 53 entities, 30 queries.

## Key Results

| Method | Overall | 1-hop | 2-hop | 3-hop |
|--------|:-------:|:-----:|:-----:|:-----:|
| VSA direct query | 30% | 90% | 0% | 0% |
| Resonator only | 30% | 90% | 0% | 0% |
| Controller + Resonator | 73% | 80% | 60% | 80% |
| **Ctrl + Res + ChainScorer (ours)** | **90%** | **100%** | **100%** | **70%** |

## Architecture

- **Hybrid memory**: Exact dict (O(1), no noise) + VSA fallback
- **GraphKANResonator**: 16 KB ternary. Replaces O(n) brute-force cleanup (77s → 1.1ms). 93% positive accuracy, **0% false positives**.
- **FastController**: <1 KB. Predicts next predicate action. 90% inference accuracy.
- **ChainScorer**: Lightweight Transformer, <1 KB. 100% ranking accuracy.
- **Beam search**: Multi-hop exploration.

## Key Breakthroughs

1. **First learned VSA resonator** — replaces algorithmic cleanup with a trained ternary network
2. **Negative training** — contrastive learning eliminates false positives (1.3% → 0%)
3. **Multi-hop without LLM** — 90% exact using only learned components + beam search
4. **Superposition noise solved** — hybrid exact+VSA memory architecture breaks the ~80% theoretical ceiling

## Hardware

| Component | Size | Deployment |
|-----------|:----:|:----------:|
| GraphKANResonator | **16 KB** | Any MCU |
| FastController | **<1 KB** | Any MCU |
| ChainScorer | **<1 KB** | Any MCU |
| VSA Memory | ~44 KB | Cortex-M4+ |
| **Total pipeline** | **<100 KB** | $0.50 MCUs |

Combined with GraphKAN for perception: **38 KB total** for a complete AI pipeline.

## Status

Proprietary technology — All Rights Reserved.  
Codebase is private. [Full site](https://fakeonomics.github.io/vsa-reasoning-overview/) available.  
For licensing inquiries, contact via GitHub.

*Created by Fakeonomics, June 2026.*
