# Hi, I'm Likhit 👋

Second-year engineering student building things from the socket layer up. Currently exploring systems programming and ML engineering.

### 🔨 What I'm building right now

**mini-vllm** — a from-scratch LLM inference engine implementing the core ideas behind [vLLM](https://github.com/vllm-project/vllm), built on PyTorch and GPT-2. In progress.

Serving an LLM well is mostly a memory and scheduling problem. A naive server handles one request at a time, or batches requests together and makes short ones wait for the longest to finish, and reserves a big contiguous block of GPU memory per request whether it's used or not. mini-vllm rebuilds the techniques that fix this, one stage at a time, and measures how much each stage actually improves throughput and latency.

- **Custom generation loop** — token-by-token decoding with a manually managed KV cache, no HuggingFace `generate()`
- **Static → continuous batching** — a scheduler where requests join and leave the active batch at every generation step instead of waiting for the whole batch
- **Paged KV cache** — fixed-size memory blocks, a block table per sequence mapping logical positions to physical blocks, and a free list for allocation and reuse
- **Benchmarks at every stage** — tokens/sec, time-to-first-token, and time-per-token compared across naive, static, continuous, and paged versions

Stack: Python, PyTorch, HuggingFace Transformers (model loading only), FastAPI

### 🧰 Tech I've been working with

![C](https://img.shields.io/badge/C-00599C?style=flat-square&logo=c&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black)
![Git](https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white)

### 📫 Find me elsewhere

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/likhit-katta)
[![X](https://img.shields.io/badge/X-000000?style=flat-square&logo=x&logoColor=white)](https://x.com/20wenty_)

---

<sub>I'd rather write a socket than import a framework</sub>
