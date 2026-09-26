<p align="center">
  <img
    src=".github/assets/profile-header.svg"
    alt="Spark AI NLP: disability-led holographic systems and research"
    width="1200"
  />
</p>

<h1 align="center">Spark AI NLP</h1>

<p align="center">
  Disability-led holographic systems &amp; research from Atlantic Canada.<br/>
  Deterministic residual research software, C++/HLS research prototypes, and evidence-tagged artifacts.
</p>

<p align="center">
  <a href="https://sparkainlpx.xyz">sparkainlpx.xyz</a> ·
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

## Evidence tags used across these repositories

| Tag | Meaning |
|---|---|
| **SYNTHETIC** | Produced by our own simulation on generated inputs |
| **REPORTED** | Measured by us; host details and raw data should accompany it; not independently reproduced |
| **TARGET** | A design goal; not yet achieved or measured |
| **UNRUN** | Tooling or scripts exist; the run has not been performed |

## Public research repositories

| Repository | Role | Status |
|---|---|---|
| [oes32-residual](https://github.com/sparkainlp-x/oes32-residual) | **Normative** OES-32 residual definition (ADR-001, `b77b612`) | Research software; contract tests pass in CI; SYNTHETIC inputs |
| [oes32_engine](https://github.com/sparkainlp-x/oes32_engine) | Profile A sidecar: Python telemetry-triage harness | Research software; unit tests; SYNTHETIC |
| [oes32-hls](https://github.com/sparkainlp-x/oes32-hls) | Profile A sidecar: C++ HLS prototype, ZCU111 as TARGET | g++ testbench only; FPGA synthesis UNRUN |
| [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp) | C++/HLS qLDPC decoder scaffold | Software CI; hardware path UNRUN |
| [quantum-error-correction-demo](https://github.com/sparkainlp-x/quantum-error-correction-demo) | Classical Python toy simulation (no qubits, no QEC code) | All outputs SYNTHETIC |
| [oes512-residual](https://github.com/sparkainlp-x/oes512-residual) | Placeholder for OES-512 | TARGET; source not published |

OES-512 (512 channels as 16 × 32 blocks, τ = 0.50, seed 42) is a **TARGET** design and is not published.

## Working principles

- Research is labelled as research; scope and limitations are stated in every README
- Simulation output is never presented as hardware, clinical, or quantum-hardware evidence
- Every number carries an evidence tag and, where possible, a reproduction path
- Accessibility first: ask for alternative formats by opening an issue in any repository

## Collaboration

Open to research groups, FPGA/decoder engineers, and accessibility-focused partners.
Open an issue in the relevant repository or reach us through [sparkainlpx.xyz](https://sparkainlpx.xyz). Also on social media as @ai4handicaps.
