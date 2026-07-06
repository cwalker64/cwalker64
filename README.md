```python
# Wen Tao — Nanjing University
# code large models & code intelligence
#
# I build the two halves of an LLM coding loop:
#   1. give the model the right context      -> repoctx
#   2. check that what it wrote actually runs -> synthforge
```

**[repoctx](https://github.com/cwalker64/repoctx)** — repository-level code context
NumPy-core code embeddings, AST symbol / dependency graph, and hybrid semantic + BM25 search. Offline-first.

**[synthforge](https://github.com/cwalker64/synthforge)** — code generation & evaluation
Prompt-based program synthesis, test-based functional evaluation, and iterative repair.

Pure-Python reference implementations — no GPU, no network needed to run the core and tests; optional PyTorch backend. CI green.
