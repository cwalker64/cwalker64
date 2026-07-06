## Wen Tao

Graduate student at **Nanjing University**, working on **code large language models & code intelligence**. My research sits where retrieval meets generation: giving models the *right* repository context and then judging their code the only way that really counts — by running the tests.

**Interests**
- 🔎 **Code retrieval** — hybrid semantic + lexical search over source, sub-token aware
- 🗂️ **Repository-level context** — AST symbol & dependency graphs, context packs for a query
- 🧪 **Code generation with test-based evaluation** — `generate → test → repair`, scored with `pass@k`
- ♻️ **Reproducibility** — deterministic, **offline-first** tooling that runs in CI with the checkout you already have

---

### Featured projects

| Project | What it does |
| --- | --- |
| [**repoctx**](https://github.com/cwalker64/repoctx) | Repository-level code context toolkit. Builds three complementary views of a codebase — dense embeddings, a lexical BM25 index, and an AST symbol/dependency graph — and answers *"where is the code about X?"* (hybrid search with Reciprocal Rank Fusion) and *"what does this symbol depend on?"* (graph-expanded context packs). Core needs only NumPy; the default feature-hashing embedder is byte-for-byte reproducible, with an optional PyTorch backend. |
| [**synthforge**](https://github.com/cwalker64/synthforge) | Small, offline-first framework for program synthesis and test-based evaluation. Turns a task prompt into candidate programs, runs them against unit tests in a sandboxed subprocess with a wall-clock timeout, and repairs failures via AST-driven single-edit search — the classic *generate → test → repair* loop, rolled up into `pass@k`. Pure Python, no runtime dependencies, no network. |

Both projects are MIT-licensed, target Python `3.9+`, and share a design stance: **dependency-light, deterministic, and runnable without a network** so results reproduce anywhere.

---

### How the pieces fit

```
repoctx    ──►  retrieve the right context   ──►  ┐
                                                   ├──►  a reproducible loop for
synthforge ──►  generate → test → repair          ┘      code-LLM experiments
```

`repoctx` handles the *input* problem — assembling faithful, repository-level context for a model. `synthforge` handles the *output* problem — evaluating and repairing what the model writes, judged by executing tests rather than by string match. Together they're the offline scaffolding I use to study code LLMs.

---

### Tech & focus

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-core-013243?logo=numpy&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-optional-EE4C2C?logo=pytorch&logoColor=white)
![Offline-first](https://img.shields.io/badge/offline--first-yes-2ea44f)
![Reproducible](https://img.shields.io/badge/reproducible-deterministic-2ea44f)
![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)

**Research areas:** code retrieval · repository-level context · code generation · test-based evaluation (`pass@k`) · program repair · reproducible ML tooling

---

<sub>Currently building offline-first tooling for code-LLM research at Nanjing University. Issues and PRs on the projects above are welcome.</sub>
