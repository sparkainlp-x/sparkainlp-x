# Spark AI NLP — Full portfolio

This document contains the detailed project index, release snapshot, research tracks, acknowledgements, and citation records for [Jean-François Brisson / Spark AI NLP](https://github.com/sparkainlp-x).

The profile README is intentionally concise; this page preserves the full evidence context. Each repository README remains authoritative for its own scope, evidence status, licence, and limitations.

## Evidence and maturity labels

| Rung | Meaning |
|---|---|
| **Demonstrated** | Code runs, tests pass in CI, and the stated result was reproduced from a fixed seed or named dataset. |
| **Prototype** | A working simulation or browser demo with tests, but no measurement outside the repository. |
| **Concept** | An architectural idea, model, or proposed measurement with little or no running code. |
| **Target** | A design goal that has not been reached or measured. |

| Tag | Meaning |
|---|---|
| **SYNTHETIC** | Produced by our own simulation or tests on generated inputs. |
| **REPORTED** | Based on identified measurements or benchmark data, with source, conditions, and reproduction status stated. |
| **TARGET** | A design goal; not yet achieved or measured. |
| **UNRUN** | Tooling or scripts exist; the run has not been performed. |

## Core project tracks

### 1. Evidence and reproducibility

Evidence records, provenance, replay, guardrails, and offline tools, plus deterministic runtimes and audit trails that make a run checkable.

Main repositories:

- [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab)
- [failure-capsules](https://github.com/sparkainlp-x/failure-capsules)
- [evidence-passport](https://github.com/sparkainlp-x/evidence-passport)
- [measurement-trail](https://github.com/sparkainlp-x/measurement-trail)
- [spark-rag-guardrail](https://github.com/sparkainlp-x/spark-rag-guardrail)
- [identity-runtime](https://github.com/sparkainlp-x/identity-runtime)

### 2. Telemetry anomaly detection

The OES-32 / OES-512 residual-latch family, benchmarks, a normative residual definition, and HLS testbenches. Detectors are benchmarked against simple baselines; outcomes are published as measured, including negative results.

Main repositories:

- [oes-resilience](https://github.com/sparkainlp-x/oes-resilience)
- [oes32-residual](https://github.com/sparkainlp-x/oes32-residual)
- [oes32-hls](https://github.com/sparkainlp-x/oes32-hls)
- [oes512q-latch](https://github.com/sparkainlp-x/oes512q-latch)
- [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp)

### 3. Holographic and interactive systems

Classical models of holographic memory, digital holography, streaming PCA, capacity limits, refusal gates, browser games, teaching prototypes, and visual/interface experiments. These are synthetic or prototype systems unless a repository states otherwise.

Main repositories:

- [waveholo](https://github.com/sparkainlp-x/waveholo)
- [waveholo-telescope](https://github.com/sparkainlp-x/waveholo-telescope)
- [membrane-crystallization](https://github.com/sparkainlp-x/membrane-crystallization)
- [crystallization-contest](https://github.com/sparkainlp-x/crystallization-contest)
- [membrane-committee](https://github.com/sparkainlp-x/membrane-committee)
- [holographic-thoughts](https://github.com/sparkainlp-x/holographic-thoughts)
- [thought-input-game](https://github.com/sparkainlp-x/thought-input-game)

### 4. Quantum-inspired experiments

Classical emulations and toy models, plus tools that audit how scientific claims are worded. All results are classical software; no quantum hardware is involved.

Main repositories:

- [quantum-projection](https://github.com/sparkainlp-x/quantum-projection)
- [claims-layer](https://github.com/sparkainlp-x/claims-layer)
- [quantum-claims-passport](https://github.com/sparkainlp-x/quantum-claims-passport)
- [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench)

### 5. C++ / HLS engineering

C++ software and HLS automation scripts for a qLDPC decoder targeting the AMD ZCU111 RFSoC. CI builds and tests the portable C++ code. FPGA synthesis, timing closure, and hardware-in-the-loop runs are **UNRUN**; there are no hardware results.

Main repositories:

- [oes32-hls](https://github.com/sparkainlp-x/oes32-hls)
- [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp)

### 6. Community and accessibility

Governance and accessibility-first work, including a reference prototype for community-led cultural and spatial-media projects and a bilingual browser plan generator. It is not legal advice and no community endorsement is claimed.

Main repositories:

- [world-holobridge](https://github.com/sparkainlp-x/world-holobridge)
- [signal-loom](https://github.com/sparkainlp-x/signal-loom)

## Latest release snapshot

- **[oes-resilience](https://github.com/sparkainlp-x/oes-resilience) · v0.6.0** — Reproducible benchmark for 512-channel telemetry anomaly detection with a transparent one-line OES32 reference detector, stress suite, replay evaluation, plugin API, and preregistered NASA SMAP/MSL comparison. **Limitation:** OES32 did not meet its success criterion; this is a negative result. [DOI](https://doi.org/10.5281/zenodo.23071166)
- **[waveholo](https://github.com/sparkainlp-x/waveholo) · v0.1.5** — End-to-end off-axis digital holography pipeline with reconstruction, focus estimation, browser sandbox, research studies, CI tests, and a real-data benchmark harness. **Limitation:** the real-data check is a slope check on 530 microscope holograms at 6 stage positions, not an absolute-focus test. [DOI](https://doi.org/10.5281/zenodo.23653721)
- **[waveholo-telescope](https://github.com/sparkainlp-x/waveholo-telescope) · v0.1.0** — Synthetic telescope-pupil adaptation of WaveHolo with Zernike aberrations, ground-truth focus and wavefront comparisons, noise tests, and a reported `phase_variance` failure. **Limitation:** synthetic only; no real telescope data or instrument claim.
- **[oes32-hls](https://github.com/sparkainlp-x/oes32-hls) · v0.3.1** — C++ HLS prototype of OES-32 triage with streaming AXI4-Stream kernel, pybind11 bindings, and pytest/Hypothesis tests comparing it bit for bit with a Python reference model. **Limitation:** FPGA synthesis is UNRUN. [DOI](https://doi.org/10.5281/zenodo.22985525)
- **[oes512q-latch](https://github.com/sparkainlp-x/oes512q-latch) · v0.2.1** — OES-32/OES-512 classical residual latch compared with standard unsupervised detectors on all 47 labelled real-data NAB series. **Limitation:** NAB results are mixed and reported as measured. [DOI](https://doi.org/10.5281/zenodo.22998570)
- **[multi-quantum-oes](https://github.com/sparkainlp-x/multi-quantum-oes) · v0.1.2** — Offline standard-library OES-512 replay-triage workbench with preregistered stress evaluation and an isolated “AI ∩ quantum” toy lab. **Limitation:** stress result is negative and synthetic. [DOI](https://doi.org/10.5281/zenodo.23113851)
- **[digital-to-wave-testbench](https://github.com/sparkainlp-x/digital-to-wave-testbench) · v0.4.2** — Synthetic, dimensionless software testbench for signed-amplitude sine encoding, including noise, phase, CFO, timing, and Wilson confidence intervals. **Limitation:** synthetic only; no physical validity claim. [DOI](https://doi.org/10.5281/zenodo.23122876)
- **[evidence-passport](https://github.com/sparkainlp-x/evidence-passport) · v0.1.1** — Offline standard-library audit tool producing a static HTML evidence passport and normalized JSON from an experiment-run manifest. **Limitation:** records declared evidence; does not re-score or validate it. [DOI](https://doi.org/10.5281/zenodo.23165143)
- **[quantum-claims-passport](https://github.com/sparkainlp-x/quantum-claims-passport) · v0.1.0** — Offline claims audit for scientific communication, classifying public claims as announcement, computational model, animal behavioral result, hypothesis, or unsupported inference. **Limitation:** source audit of wording, not a re-experiment. [DOI](https://doi.org/10.5281/zenodo.23167801)

## How the work is done

- **Contracts first:** definitions live in one normative place with executable tests; for OES-32, see [oes32-residual ADR-001](https://github.com/sparkainlp-x/oes32-residual/tree/b77b61254f15778c6ae221843dceac7a8571158e).
- **Fail closed:** selected READMEs label unrun or unmeasured work, including negative outcomes where evaluations were performed.
- **Minimal dependencies:** many tools use only the Python standard library; others use NumPy, Stim, PyMatching, or upstream `ldpc` where justified.
- **Tests and CI:** repositories include tests and continuous integration where appropriate.
- **Open licensing:** most repositories are AGPL-3.0-only with a commercial-licence option; some use MIT or MIT OR Apache-2.0. Each repository’s LICENSE file is authoritative.
- **Archived releases:** released versions are archived on Zenodo with concept and version DOIs.
- **Accessibility first:** ask for alternative formats by opening an issue in any repository.

## Acknowledgements

Mun Seok Lee and Somnath Laha are acknowledged as collaborators. Lee’s *Digital to Wave* preprints and packages received under his name are the source for the Digital-to-Wave repositories and the membrane-related repositories that say so in their Provenance sections. Laha’s related discussion of a satellite concept motivated the framing of [orbit-wave-oes-lab](https://github.com/sparkainlp-x/orbit-wave-oes-lab).

This is an acknowledgement only. It implies no endorsement of these repositories and no authorship. The software is by Jean-François Brisson, and each repository’s README states what it derives from.

## Full project index

The account currently contains 115 public repositories. Zenodo records are being added to the [Spark AI NLP: Research Software](https://zenodo.org/communities/spark-ai-nlp/) community; use each repository README for its authoritative citation and DOI details.

For the complete repository list, see: <https://github.com/sparkainlp-x?tab=repositories>

A direct match identifies the corresponding public project; it is not a claim of scientific validation. Related projects are separate implementations or tools, and their individual READMEs define their scope and evidence.

## Citation

If you use or build on Spark Evidence Lab, please cite:

```bibtex
@software{brisson_spark_evidence_lab,
  author = {Brisson, Jean-Fran{\\c{c}}ois},
  title = {Spark Evidence Lab},
  year = {2026},
  doi = {10.5281/zenodo.23403169},
  url = {https://github.com/sparkainlp-x/spark-evidence-lab}
}
```

If you use or build on WaveHolo, please cite:

```bibtex
@software{brisson_waveholo,
  author = {Brisson, Jean-Fran{\\c{c}}ois},
  title = {WaveHolo},
  year = {2026},
  doi = {10.5281/zenodo.23644416},
  url = {https://github.com/sparkainlp-x/waveholo}
}
```
