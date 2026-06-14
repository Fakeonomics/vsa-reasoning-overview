# VSA Reasoning — CPU Neural Reasoner

[![License](https://img.shields.io/badge/License-All%20Rights%20Reserved-red)]() [![VSA Reasoning](https://img.shields.io/badge/VSA%20Reasoning-Live%20Site-blue?style=for-the-badge)](https://fakeonomics.github.io/vsa-reasoning-overview/) [![GraphKAN](https://img.shields.io/badge/GraphKAN-Live%20Site-228b22?style=for-the-badge)](https://fakeonomics.github.io/graphkan-overview/)

**🌐 [VSA Reasoning Live Site](https://fakeonomics.github.io/vsa-reasoning-overview/) · [GraphKAN Live Site](https://fakeonomics.github.io/graphkan-overview/)**

First learned neural reasoner on **Vector-Symbolic Architecture** with **ternary weights**. 90% exact multi-hop QA without LLM or GPU. 16 KB ternary resonator. Total pipeline <100 KB.

---

## Key Results

| Method | Overall | 1-hop | 2-hop | 3-hop |
|--------|:-------:|:-----:|:-----:|:-----:|
| VSA direct | 30% | 90% | 0% | 0% |
| Controller + Resonator | 73% | 80% | 60% | 80% |
| **Ctrl+Res+ChainScorer** | **90%** | **100%** | **100%** | **70%** |

---

## Components

| Component | Params | Size |
|-----------|:------:|:----:|
| GraphKANResonator | 65,536 ternary | **16 KB** |
| FastController | 37,384 float | **<1 KB** |
| ChainScorer (Transformer 2L/4H/128d) | 50K float | **<1 KB** |
| VSA Memory | — | ~44 KB |

---

## Status

Proprietary technology — All Rights Reserved. Codebase is private.
For licensing inquiries or collaboration, contact via [GitHub](https://github.com/Fakeonomics).

*Created by Fakeonomics, June 2026.*
