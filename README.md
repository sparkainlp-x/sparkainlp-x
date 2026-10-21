<p align="center">
  <img
    src="assets/banner.jpg"
    alt="Spark AI NLP banner: glowing brain-circuit logo with the words SPARK AI NLP over a dark lab scene"
    width="1024"
  />
</p>

<div align="center">

# Spark AI NLP

### Deterministic runtimes, quantum-error-correction research software and telemetry integrity tools

*Independent research lead and founder: Jean-François Brisson*<br/>
*Fredericton, New Brunswick, Canada*<br/>
*Classical software prioritising verifiability, audit transparency and minimal dependencies.*

</div>

<p align="center">
  Disability-led research software: telemetry research, C++/HLS prototypes, RAG guardrails, and offline evidence-audit tools, with scope and evidence status documented per project.
</p>

<p align="center">
  <a href="https://sparkainlpx.xyz">sparkainlpx.xyz</a> ·
  <a href="https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4">LinkedIn</a> ·
  <a href="https://notebook.google.com/notebook/cfd4dba3-0a62-4076-8169-99c2e092d56f">Research notebook</a> ·
  <a href="https://sparkainlp-x.github.io/holographic-thoughts/">Live demo: Holographic Thoughts</a> ·
  <a href="https://orcid.org/0009-0000-9778-5374"><img src="https://img.shields.io/badge/ORCID-0009--0000--9778--5374-A6CE39?logo=orcid&logoColor=white" alt="ORCID iD 0009-0000-9778-5374" height="20" /></a> ·
  <a href="https://zenodo.org/communities/spark-ai-nlp/"><img src="https://img.shields.io/badge/Zenodo-Spark%20AI%20NLP-1682D4?logo=zenodo&logoColor=white" alt="Zenodo community: Spark AI NLP: Research Software" height="20" /></a><br/>
  Français (langue maternelle) · English (fluent)
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-Research%20Prototyping-2563EB?style=for-the-badge" alt="Research prototyping" />
  <img src="https://img.shields.io/badge/Systems-C%2B%2B%20%7C%20Python-0F766E?style=for-the-badge" alt="C++ and Python" />
  <img src="https://img.shields.io/badge/HLS%20%2F%20FPGA-TARGET-7C3AED?style=for-the-badge" alt="HLS and FPGA: TARGET (design goal, synthesis not yet run)" />
  <img src="https://img.shields.io/badge/Method-Evidence--tagged-0891B2?style=for-the-badge" alt="Evidence-tagged research" />
</p>

> **Open to work:** applied AI research and research-software roles, remote within Canada or on site in Fredericton. Contact details are [below](#contact).

## About

Spark AI NLP is a disability-led research-software company based in Fredericton, New Brunswick, Canada. The public repositories are **research prototypes**: a reproducible telemetry anomaly-detection benchmark, the OES-32/OES-512 residual-latch family, C++/HLS kernels, a source-grounded RAG guardrail, two offline audit tools (Evidence Passport for run-level evidence, Quantum Claims Evidence Passport for public claims against their sources), and small offline tools for provenance and consent-first data sharing. They are not hardware products, field products, or medical products, and they do not report results on quantum hardware.

## Ecosystem overview

Four projects that show the main strands of the work. Each repository's README defines its own scope and evidence status.

| Project | Domain | What it is | Stack | Archive |
|---|---|---|---|---|
| [**identity-runtime**](https://github.com/sparkainlp-x/identity-runtime) | Runtime governance and audit | Governed, reversible avatar personalities: human-approved versions, short revocable capability leases, the OES-61440 tripwire and a hash-chained audit ledger. Research prototype; not tested against real attackers; [demo page](https://sparkainlp-x.github.io/identity-runtime/) | Python 3.10+, standard library only; SHA-256 ledger; optional HMAC-SHA256 approvals | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23448946.svg)](https://doi.org/10.5281/zenodo.23448946) |
| [**qldpc_decoder_cpp**](https://github.com/sparkainlp-x/qldpc_decoder_cpp) | Quantum-error-correction research software | C++/HLS research scaffold for a qLDPC decoder, with Vitis HLS, Vivado and PetaLinux scripts **targeting** the AMD ZCU111 RFSoC board. The belief-propagation kernel is a placeholder; HLS synthesis, timing closure and HIL runs are **UNRUN** | C++20, CMake, Catch2, OpenMP, upstream [`ldpc`](https://github.com/quantumgizmos/ldpc) library; Vitis HLS / Vivado TCL scripts | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22985527.svg)](https://doi.org/10.5281/zenodo.22985527) |
| [**OES-512 / OES-32**](https://github.com/sparkainlp-x/oes-resilience) (oes-resilience) | Telemetry triage | Reproducible benchmark: 512 channels split into sixteen 32-channel blocks, scored by the transparent one-line OES32 detector against z-score, EWMA and CUSUM baselines, with a seeded stress suite and replay evaluation. Mostly SYNTHETIC; on the preregistered NASA SMAP/MSL test OES32 did **not** meet its success criterion | Python, NumPy (only required dependency); CLI; CI on Python 3.10–3.13 | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23071166.svg)](https://doi.org/10.5281/zenodo.23071166) |
| [**infinite-becoming**](https://github.com/sparkainlp-x/infinite-becoming) | Synthetic ecosystem game | Small browser-playable ecosystem toy: agents forage, reproduce and get sick on a reaction–diffusion substrate, with seeded deterministic runs. Synthetic and uncalibrated; no claim to simulate consciousness or predict real ecosystems; [play online](https://sparkainlp-x.github.io/infinite-becoming/) | JavaScript, HTML canvas, no third-party runtime dependencies; Node.js tests; GitHub Pages | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23423943.svg)](https://doi.org/10.5281/zenodo.23423943) |

## Core research pillars

### 1. Deterministic runtimes and audit trails

- **OES-61440 tripwire** (in identity-runtime): 61,440 fixed threshold channels, grouped as 1,920 membranes of 32 channels (120 sectors × 4 supervisors × 4 membranes = 1,920; 1,920 × 32 = 61,440). Each channel compares a fixed weighted sum of four risk signals with a fixed threshold.
- **Nothing learned:** weights and thresholds come from SHA-256 of the channel index. The settings are illustrative, not calibrated against incident data, and the tripwire is not a safety guarantee; a plain rule holds any action with effective risk of 0.5 or more for a human.
- **Hash-chained ledger:** every step is appended to a JSONL ledger in which each entry's hash covers the previous entry's hash. Editing, reordering or deleting lines breaks verification. The ledger is tamper-evident, not tamper-proof.

### 2. qLDPC decoder co-design (classical software)

- C++ software and HLS automation scripts for a qLDPC decoder targeting the AMD ZCU111 RFSoC; see [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp).
- CI builds and tests the portable C++ code. FPGA synthesis, timing closure and hardware-in-the-loop runs are UNRUN, and no qubits or quantum hardware are involved. There are no hardware results.

### 3. Residual-telemetry triage

- Deterministic residual-telemetry triage across the OES-32/OES-512 family: fixed 32-channel blocks, transparent scores and fail-closed input contracts, with one normative residual definition ([oes32-residual](https://github.com/sparkainlp-x/oes32-residual), ADR-001).
- Detectors are benchmarked against simple baselines and the outcomes are published as measured, including negative results; see [Featured work](#featured-work).

## Project index

This index links project names to their canonical public repositories. A **direct match** identifies the corresponding public project; it is not a claim of scientific validation. Related projects are separate implementations or tools, and their individual READMEs define their scope and evidence.

### Direct public matches

| Project | Canonical public repository |
|---|---|
| PilotTrace | [pilottrace](https://github.com/sparkainlp-x/pilottrace) |
| Flip Observer 1024 | [flip-observer-1024](https://github.com/sparkainlp-x/flip-observer-1024) |
| Signal Loom | [signal-loom](https://github.com/sparkainlp-x/signal-loom) |
| OES telemetry bench | [oes-telemetry-bench](https://github.com/sparkainlp-x/oes-telemetry-bench) |
| OES-Resilience | [oes-resilience](https://github.com/sparkainlp-x/oes-resilience) |
| OES32 membrane array | [oes32-membrane-array](https://github.com/sparkainlp-x/oes32-membrane-array) |
| Three-node graph demo | [conserved-message-graph-demo](https://github.com/sparkainlp-x/conserved-message-graph-demo) |
| OES-32 HLS | [oes32-hls](https://github.com/sparkainlp-x/oes32-hls) |
| Thermoelectric Ledger | [thermoelectric-ledger](https://github.com/sparkainlp-x/thermoelectric-ledger) |
| Residual Gradient Workbench | [residual-gradient-workbench](https://github.com/sparkainlp-x/residual-gradient-workbench) |

### Related or partial public work

| Area | Public repository or repositories | Relationship and boundary |
|---|---|---|
| Digital-to-Wave | [digital-to-wave-testbench](https://github.com/sparkainlp-x/digital-to-wave-testbench) | Related synthetic, dimensionless software testbench; no physical validity claim. |
| OES residual and replay tools | [oes32-residual](https://github.com/sparkainlp-x/oes32-residual), [oes32_engine](https://github.com/sparkainlp-x/oes32_engine), [spark-membrane](https://github.com/sparkainlp-x/spark-membrane), [multi-quantum-oes](https://github.com/sparkainlp-x/multi-quantum-oes) | Related implementations and workbenches with distinct scopes; see each repository before treating one as a substitute for another. |
| Evidence, provenance, and claims audits | [evidence-passport](https://github.com/sparkainlp-x/evidence-passport), [measurement-trail](https://github.com/sparkainlp-x/measurement-trail), [quantum-claims-passport](https://github.com/sparkainlp-x/quantum-claims-passport) | Separate tools for run evidence, provenance, and public-claim review. |
| Classical QEC scaling | [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench) | Partial match: a classical surface-/repetition-code scaling simulation only; no quantum-hardware results. |
| qLDPC decoder scaffold | [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp) | A separate unfinished C++/HLS scaffold; the belief-propagation kernel is a placeholder and HLS/HIL runs are UNRUN. |

The profile and repository READMEs distinguish synthetic or theoretical results from measured results, targets, and runs that have not been performed. Code quality or reproducibility alone does not establish scientific validity.

## Featured work

| Repository | What it is | Evidence status | Archive |
|---|---|---|---|
| [**oes-resilience**](https://github.com/sparkainlp-x/oes-resilience) · v0.6.0 | Open, reproducible benchmark for 512-channel telemetry anomaly detection with the transparent one-line OES32 reference detector; stress suite, replay evaluation, detector plugin API, a preregistered NASA SMAP/MSL comparison, and adaptive methods (v0.6.0) | Baseline SYNTHETIC (byte-reproduced in CI). On SMAP/MSL under the locked protocol, OES32 did **not** meet its success criterion; the locked OES-32-v2 re-attempt did **not** meet its predeclared improvement criterion | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23071166.svg)](https://doi.org/10.5281/zenodo.23071166) |
| [**oes32-hls**](https://github.com/sparkainlp-x/oes32-hls) · v0.3.0 | C++ HLS prototype of OES-32 triage: streaming AXI4-Stream kernel, pybind11 bindings, and pytest + Hypothesis tests comparing it bit for bit with a Python reference model | `g++` testbenches and Python tests run in CI on SYNTHETIC stimuli; FPGA synthesis UNRUN (ZCU111 is a TARGET) | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22985525.svg)](https://doi.org/10.5281/zenodo.22985525) |
| [**oes512q-latch**](https://github.com/sparkainlp-x/oes512q-latch) · v0.2.1 | OES-32/OES-512 classical residual latch with a self-calibrated threshold, compared with standard unsupervised detectors on all 47 labelled real-data series in the Numenta Anomaly Benchmark (NAB) | NAB numbers REPORTED (mixed results, reported as measured); unit tests SYNTHETIC; not a quantum code | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22998570.svg)](https://doi.org/10.5281/zenodo.22998570) |
| [**multi-quantum-oes**](https://github.com/sparkainlp-x/multi-quantum-oes) · v0.1.2 | Offline, standard-library-only OES-512 replay-triage workbench with a preregistered stress evaluation, plus an isolated "AI ∩ quantum" toy lab | Stress result is **negative** and published as such; SYNTHETIC data; exact classical simulation, not a QPU | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23113851.svg)](https://doi.org/10.5281/zenodo.23113851) |
| [**digital-to-wave-testbench**](https://github.com/sparkainlp-x/digital-to-wave-testbench) · v0.4.2 | Synthetic, dimensionless software testbench for a signed-amplitude sine encoding (noise, phase, CFO, timing; Wilson CIs) | All results SYNTHETIC; no physical validity claimed | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23122876.svg)](https://doi.org/10.5281/zenodo.23122876) |
| [**evidence-passport**](https://github.com/sparkainlp-x/evidence-passport) · v0.1.0 | Offline stdlib audit tool: one experiment-run manifest → static HTML evidence passport + normalized JSON (fail-closed SHA-256); records declared evidence, never re-scores it | Bundled OES-Resilience SMAP/MSL sample keeps the verdict: criterion **not** met; three further examples labelled SYNTHETIC; [sample pages](https://sparkainlp-x.github.io/evidence-passport/) | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23165143.svg)](https://doi.org/10.5281/zenodo.23165143) |
| [**quantum-claims-passport**](https://github.com/sparkainlp-x/quantum-claims-passport) · v0.1.0 | Offline claims audit for scientific communication: classifies public claims (a planned Swiss quantum-computer hub; a modeled 613 THz tubulin frequency band; a rat behavioral study) as announcement, computational model, animal behavioral result, hypothesis, or unsupported inference, with exact-SI conversions and no combined score | Source audit only, snapshot 2026-10-05; makes none of the audited claims; no affiliation with the institutions named; [report](https://sparkainlp-x.github.io/quantum-claims-passport/report.html) | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23167801.svg)](https://doi.org/10.5281/zenodo.23167801) |

### Recent work

- [identity-runtime](https://github.com/sparkainlp-x/identity-runtime): standard-library Python runtime for governed, reversible avatar personalities, with human approval quorums, expiring capability leases, the OES-61440 tripwire and a hash-chained ledger; 99 tests in CI; not tested against real attackers; [demo page](https://sparkainlp-x.github.io/identity-runtime/). [DOI 10.5281/zenodo.23448946](https://doi.org/10.5281/zenodo.23448946)
- [infinite-becoming](https://github.com/sparkainlp-x/infinite-becoming): browser-playable synthetic ecosystem game on a reaction–diffusion substrate; uncalibrated; its frozen persistence regression is disclosed (1 of 5 seeds); [play online](https://sparkainlp-x.github.io/infinite-becoming/). [DOI 10.5281/zenodo.23423943](https://doi.org/10.5281/zenodo.23423943)
- [world-holobridge](https://github.com/sparkainlp-x/world-holobridge): standard-library Python + SQLite reference prototype of a governance workflow for community-led cultural and spatial-media projects, with a bilingual browser plan generator; not legal advice; no community endorsement claimed (MIT OR Apache-2.0); [plan generator](https://sparkainlp-x.github.io/world-holobridge/). [DOI 10.5281/zenodo.23423941](https://doi.org/10.5281/zenodo.23423941)
- [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab): rerunnable experiment cards that put my methods next to simple baselines, including where the baseline wins; every number copied from a committed source file; [live page](https://sparkainlp-x.github.io/spark-evidence-lab/). [DOI 10.5281/zenodo.23403169](https://doi.org/10.5281/zenodo.23403169)
- [digital-to-wave-2-thz-validity](https://github.com/sparkainlp-x/digital-to-wave-2-thz-validity): engineering-validity study of the THz equations in Mun Seok Lee's *Digital to Wave* Part II preprint (equation inventory, dimensional checks, protocol-locked synthetic channel benchmark); SYNTHETIC; no physical, biological or safety claim. [DOI 10.5281/zenodo.23375690](https://doi.org/10.5281/zenodo.23375690)
- [orbit-wave-oes-lab](https://github.com/sparkainlp-x/orbit-wave-oes-lab): software-only path from a stylized orbit timeline to a synthetic signed-wave payload, fixed-threshold readout, optional OES replay and evidence passport, plus offline binaural capture analysis; SYNTHETIC; orbit, spacecraft, quantum and acoustic hardware UNRUN. [DOI 10.5281/zenodo.23372536](https://doi.org/10.5281/zenodo.23372536)
- [spark-membrane](https://github.com/sparkainlp-x/spark-membrane): fail-closed console that audits SYNTHETIC 32-channel frames against the OES repositories, pinned by commit SHA, with a hash-chained run trail, evidence passport and claims gate; thresholds uncalibrated; [demo page](https://sparkainlp-x.github.io/spark-membrane/). [DOI 10.5281/zenodo.23175490](https://doi.org/10.5281/zenodo.23175490)
- [oes-telemetry-bench](https://github.com/sparkainlp-x/oes-telemetry-bench): offline replay bench for synchronized 32-channel OES32 telemetry frames, with a strict input contract and frozen thresholds; synthetic demo. [DOI 10.5281/zenodo.23175492](https://doi.org/10.5281/zenodo.23175492)
- [residual-gradient-workbench](https://github.com/sparkainlp-x/residual-gradient-workbench): browser workbench that keeps an OES-32 residual replay and a classical thermoelectric generator model in separate lanes; [demo page](https://sparkainlp-x.github.io/residual-gradient-workbench/). [DOI 10.5281/zenodo.23187280](https://doi.org/10.5281/zenodo.23187280)
- [thermoelectric-ledger](https://github.com/sparkainlp-x/thermoelectric-ledger): signed heat-flow accounting that withholds exergy and efficiency figures unless the uncertainty bounds support them; 104 contract tests in CI (MIT). [DOI 10.5281/zenodo.23241554](https://doi.org/10.5281/zenodo.23241554)
- [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench): classical toy simulation of surface- and repetition-code memory scaling with Stim and PyMatching; seeded and reproducible, no hardware results. [DOI 10.5281/zenodo.23241631](https://doi.org/10.5281/zenodo.23241631)
- [flip-observer-1024](https://github.com/sparkainlp-x/flip-observer-1024): calibration prototype for a classical weighted readout under a hidden channel-order reversal (512 inputs, two noisy banks); SYNTHETIC; [demo page](https://sparkainlp-x.github.io/flip-observer-1024/). [DOI 10.5281/zenodo.23173449](https://doi.org/10.5281/zenodo.23173449)
- [oes-quantum-binaural-lab](https://github.com/sparkainlp-x/oes-quantum-binaural-lab): classical toy simulation with three separate lanes (Bell-correlation Monte Carlo, scalar metrics ledger, digital stereo loopback); SYNTHETIC. [DOI 10.5281/zenodo.23175494](https://doi.org/10.5281/zenodo.23175494)
- [signal-loom](https://github.com/sparkainlp-x/signal-loom): offline performance-art prototype in which synthetic signal streams drive an interactive visual score (MIT); [demo page](https://sparkainlp-x.github.io/signal-loom/). [DOI 10.5281/zenodo.23173453](https://doi.org/10.5281/zenodo.23173453)

<details>
<summary>Other public repositories</summary>

**More research software**

- [oes32-membrane-array](https://github.com/sparkainlp-x/oes32-membrane-array): software-only scale-out wrapper for the fixed 32-slot OES32 membrane contract; generated inputs, no hardware or performance claims.
- [oes32-residual](https://github.com/sparkainlp-x/oes32-residual): the **normative** OES-32 residual (ADR-001) with 12 contract tests in CI (Python 3.11–3.13).
- [oes32-membrane-shield](https://github.com/sparkainlp-x/oes32-membrane-shield): 32-slot state machine gated by Ed25519 capabilities, with dual-approval calibration; 25 tests, including fuzz tests, pass in CI; independent security review UNRUN.
- [homological-cascade-engine](https://github.com/sparkainlp-x/homological-cascade-engine): experimental Python framework for topological signal representations and robust anomaly scoring; synthetic tests do not establish real-telemetry performance or operational false-alarm control.
- [oes512-telemetry-engine](https://github.com/sparkainlp-x/oes512-telemetry-engine): asynchronous Python prototype for 512-channel telemetry ingestion, DSP, and monitoring; see its README for current implementation scope.
- [oes32-dashboard](https://github.com/sparkainlp-x/oes32-dashboard): PyQt6/PyQtGraph desktop dashboard using synthetic stimuli; not a medical or field system.
- [spark-rag-guardrail](https://github.com/sparkainlp-x/spark-rag-guardrail): source-grounded RAG (ChromaDB + Ollama) that refuses to answer when retrieval relevance is too low; 10 tests on SYNTHETIC fixtures; answer quality UNRUN.

**Offline tools**

- [context-wallet](https://github.com/sparkainlp-x/context-wallet): user-selected, short-lived JSON context packets (preview before export). [DOI 10.5281/zenodo.23061441](https://doi.org/10.5281/zenodo.23061441)
- [measurement-trail](https://github.com/sparkainlp-x/measurement-trail): SHA-256 hash-chained measurement provenance trails. [DOI 10.5281/zenodo.23067465](https://doi.org/10.5281/zenodo.23067465)
- [coil-efficiency-bench](https://github.com/sparkainlp-x/coil-efficiency-bench): paired motor-efficiency analysis with a Student's t CI; bundled data SYNTHETIC. [DOI 10.5281/zenodo.23067995](https://doi.org/10.5281/zenodo.23067995)
- [signal-commons](https://github.com/sparkainlp-x/signal-commons): coarse categorical incident postcards from 512-channel residual frames, without sharing raw data. [DOI 10.5281/zenodo.23049349](https://doi.org/10.5281/zenodo.23049349)
- [signal-test-commons](https://github.com/sparkainlp-x/signal-test-commons): deterministic synthetic challenge suite for 512-channel signal monitors. [DOI 10.5281/zenodo.23057992](https://doi.org/10.5281/zenodo.23057992)
- [internal-outage-radar](https://github.com/sparkainlp-x/internal-outage-radar): offline scope classification of multi-site service-check snapshots. [DOI 10.5281/zenodo.23057994](https://doi.org/10.5281/zenodo.23057994)
- [gnss-log-stats](https://github.com/sparkainlp-x/gnss-log-stats): local-only descriptive statistics for approved GNSS CSV logs; no receiver validation or physical-evidence claim.
- [web-delta-feed](https://github.com/sparkainlp-x/web-delta-feed): reproducible comparison reports for two saved text snapshots. [DOI 10.5281/zenodo.23069164](https://doi.org/10.5281/zenodo.23069164)
- [pocket-internet](https://github.com/sparkainlp-x/pocket-internet): offline exchange and merge of public-information bundles between disconnected devices. [DOI 10.5281/zenodo.23187284](https://doi.org/10.5281/zenodo.23187284)
- [pilottrace](https://github.com/sparkainlp-x/pilottrace): offline validation and block scoring of 512-value numeric trace frames. [DOI 10.5281/zenodo.23187278](https://doi.org/10.5281/zenodo.23187278)

**Smaller prototypes and demos**

[address-phase-demo](https://github.com/sparkainlp-x/address-phase-demo) (FR educational HTML; SYNTHETIC) ·
[conserved-message-graph-demo](https://github.com/sparkainlp-x/conserved-message-graph-demo) (synthetic graph-routing analogy; not general relativity or OES32) ·
[empty-state-observatory](https://github.com/sparkainlp-x/empty-state-observatory) (synthetic guessing game and benchmark; not physical-universe or hardware evidence) ·
[max-slate-einstein](https://github.com/sparkainlp-x/max-slate-einstein) (bounded educational character-engine prototype; not Einstein or historical authenticity) ·
[spark-oes512-demo](https://github.com/sparkainlp-x/spark-oes512-demo) (browser OES32-style demo; SYNTHETIC) ·
[oes512-residual](https://github.com/sparkainlp-x/oes512-residual) ·
[oes32_engine](https://github.com/sparkainlp-x/oes32_engine) ·
[qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp) (unfinished C++/HLS decoder scaffold; BP kernel and correction checks are placeholders; HLS/HIL UNRUN) ·
[phmt4-montecarlo](https://github.com/sparkainlp-x/phmt4-montecarlo) (heuristic classical simulation) ·
[quantum-error-correction-demo](https://github.com/sparkainlp-x/quantum-error-correction-demo) (classical toy; no qubits, no QEC code)

Repository documentation varies; check each README for its specific scope, limits, evidence status, and setup.

</details>

Nearly all public repositories (45 of 47) have Zenodo DOIs; the two without are this profile README and the shared `.github` community-files repository. Use each repository's README for its citation and DOI details. Records are being added to the [Spark AI NLP: Research Software](https://zenodo.org/communities/spark-ai-nlp/) Zenodo community.

## Engineering principles

- **Minimal dependencies.** Many tools use only the Python standard library (for example identity-runtime, world-holobridge, evidence-passport and multi-quantum-oes), and infinite-becoming has no third-party runtime dependencies. Others depend on what the work needs: oes-resilience requires NumPy, qec-scaling-bench uses Stim and PyMatching, and qldpc_decoder_cpp builds against the upstream `ldpc` library.
- **Tests and CI per repository.** Test suites and GitHub Actions workflows are maintained repository by repository; identity-runtime and oes-resilience, for example, run in CI on Python 3.10–3.13.
- **Open licences, per repository.** Most repositories are AGPL-3.0-only with a commercial-licence option; some are MIT, and world-holobridge is MIT OR Apache-2.0. Each repository's LICENSE file is authoritative.
- **Archived releases.** Released versions are archived on Zenodo with concept and version DOIs (see [Cite](#cite)).

## How I work

- **Contracts first.** Each definition lives in one normative place with executable tests. For OES-32 that is [oes32-residual@b77b612](https://github.com/sparkainlp-x/oes32-residual/tree/b77b61254f15778c6ae221843dceac7a8571158e) (ADR-001); other implementations are labelled Profile A sidecars and document how they differ.
- **Fail-closed where specified.** Selected READMEs label unrun or unmeasured work; results and caveats are documented per project, including negative outcomes where evaluations were performed.
- **Evidence labels where reported.** Project READMEs define their own evidence status; labels and coverage are not universal across every repository.

  | Tag | Meaning |
  |---|---|
  | **SYNTHETIC** | Produced by our own simulation or tests on generated inputs |
  | **REPORTED** | A project result based on identified measurements or benchmark data. The README states whether data were collected for this project or pre-existing, names the source and conditions/protocol, and says whether independently reproduced |
  | **TARGET** | A design goal; not yet achieved or measured |
  | **UNRUN** | Tooling or scripts exist; the run has not been performed |

- **Reproducibility varies by project.** Some repositories document tested Quickstarts, automated tests, or CI; check the individual README and workflow for current coverage.
- **Accessibility first.** Ask for alternative formats by opening an issue in any repository.

Contribution guidelines, the code of conduct, and the security policy are shared across all repositories: [sparkainlp-x/.github](https://github.com/sparkainlp-x/.github).

## Cite

Nearly all public repositories (45 of 47) have Zenodo concept and version DOIs, and archived repositories include `CITATION.cff`. Use GitHub's **"Cite this repository"** button or the citation links in the specific repository when available. Records are being added to the [Spark AI NLP: Research Software](https://zenodo.org/communities/spark-ai-nlp/) Zenodo community.

## Contact

Open to applied AI research and research-software roles (remote within Canada, or Fredericton, NB), and to collaboration with research groups, FPGA/decoder engineers, and accessibility-focused partners.

- Website: [sparkainlpx.xyz](https://sparkainlpx.xyz)
- LinkedIn: [Jean-François Brisson](https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4)
- Research notebook: [Spark AI NLP notebook](https://notebook.google.com/notebook/cfd4dba3-0a62-4076-8169-99c2e092d56f)
- Live demo: [Holographic Thoughts](https://sparkainlp-x.github.io/holographic-thoughts/) (interactive toy views; synthetic, classical simulation)
- ORCID: [0009-0000-9778-5374](https://orcid.org/0009-0000-9778-5374)
- Questions about code: open an issue in the relevant repository
