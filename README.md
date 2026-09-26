<p align="center">
  <img
    src="assets/banner.jpg"
    alt="Spark AI NLP banner: glowing brain-circuit logo with the words SPARK AI NLP over a dark holographic lab scene"
    width="1024"
  />
</p>

<h1 align="center">Spark AI NLP</h1>

<p align="center">
  Disability-led holographic systems &amp; research from Atlantic Canada.<br/>
  Deterministic residual research software, C++/HLS research prototypes, and evidence-tagged artifacts.
</p>

<p align="center">
  <a href="https://sparkainlpx.xyz">sparkainlpx.xyz</a> ·
  <a href="https://www.linkedin.com/in/jean-francois-brisson-41927b3a4">LinkedIn</a> ·
  Founder: Jean-François Brisson ·
  Français (langue maternelle) · English (fluent)
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-Research%20Prototyping-2563EB?style=for-the-badge" alt="Research prototyping" />
  <img src="https://img.shields.io/badge/Systems-C%2B%2B%20%7C%20Python-0F766E?style=for-the-badge" alt="C++ and Python" />
  <img src="https://img.shields.io/badge/HLS%20%2F%20FPGA-TARGET-7C3AED?style=for-the-badge" alt="HLS and FPGA: TARGET (design goal, synthesis not yet run)" />
  <img src="https://img.shields.io/badge/Method-Evidence--tagged-0891B2?style=for-the-badge" alt="Evidence-tagged research" />
</p>

## About

Spark AI NLP is a disability-led company working on holographic systems and research. The public repositories below are **research prototypes**: deterministic residual research software and C++/HLS exploration. They are not hardware products, field products, or medical products, and they do not report results on quantum hardware.

## Featured work

| Repository | What it is | Evidence status |
|---|---|---|
| [oes32-residual](https://github.com/sparkainlp-x/oes32-residual) | **Normative** OES-32 residual (ADR-001): max-absolute residual over two 32-vectors, strict `>` tolerance rule, contract tests. Release [v0.1.0](https://github.com/sparkainlp-x/oes32-residual/releases/tag/v0.1.0) | 12 contract tests pass in CI (Python 3.11–3.13); SYNTHETIC inputs |
| [oes32_engine](https://github.com/sparkainlp-x/oes32_engine) | Profile A sidecar: standard-library Python telemetry-triage harness (residual latch, EVEN/ODD symmetry, FOLD8) with a technical specification | 7 unit tests pass in CI (Python 3.11/3.12); SYNTHETIC inputs; not certified control software |
| [oes32-hls](https://github.com/sparkainlp-x/oes32-hls) | Profile A sidecar: C++ HLS prototype of the same checks; AMD ZCU111 as a design target | `g++` testbench passes in CI (8/8 checks); FPGA synthesis and latency UNRUN / TARGET |
| [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp) | C++/HLS qLDPC decoder scaffold: CMake + Catch2 + GF(2) micro-benchmark, Vitis/Vivado/PetaLinux scripts | Software build and tests pass in CI; BP kernel is a placeholder; hardware results UNRUN |

<details>
<summary>Other public repositories</summary>

| Repository | What it is | Evidence status |
|---|---|---|
| [quantum-error-correction-demo](https://github.com/sparkainlp-x/quantum-error-correction-demo) | Classical Python toy simulation (no qubits, no QEC code) | All outputs SYNTHETIC; seeded smoke run in CI |
| [oes512-residual](https://github.com/sparkainlp-x/oes512-residual) | Placeholder for OES-512 (16 × OES-32 blocks) | TARGET; source not published |

</details>

OES-512 (512 channels as 16 × 32 blocks; weighted latch S = 0.45·Peak + 0.35·RMS + 0.20·MeanAbs, τ = 0.50) is a **TARGET** design and is not published.

## How I work

- **Contracts first.** Each definition lives in one normative place with executable tests. For OES-32 that is [oes32-residual@b77b612](https://github.com/sparkainlp-x/oes32-residual/tree/b77b61254f15778c6ae221843dceac7a8571158e) (ADR-001); other implementations are labelled Profile A sidecars and document how they differ.
- **Fail-closed.** Invalid input is rejected rather than guessed, and so are claims: if something has not been run or measured, the README says so.
- **Evidence tags on every number.**

  | Tag | Meaning |
  |---|---|
  | **SYNTHETIC** | Produced by our own simulation or tests on generated inputs |
  | **REPORTED** | Measured by us; host details and raw data accompany it; not independently reproduced |
  | **TARGET** | A design goal; not yet achieved or measured |
  | **UNRUN** | Tooling or scripts exist; the run has not been performed |

- **Reproducible by default.** Every README has a Quickstart that was run from a fresh clone, and CI runs the tests on every change.
- **Accessibility first.** Ask for alternative formats by opening an issue in any repository.

Contribution guidelines, the code of conduct, and the security policy are shared across all repositories: [sparkainlp-x/.github](https://github.com/sparkainlp-x/.github).

## Contact

Open to research groups, FPGA/decoder engineers, and accessibility-focused partners.

- Website: [sparkainlpx.xyz](https://sparkainlpx.xyz)
- LinkedIn: [Jean-François Brisson](https://www.linkedin.com/in/jean-francois-brisson-41927b3a4)
- Questions about code: open an issue in the relevant repository
