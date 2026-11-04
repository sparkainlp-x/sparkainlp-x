<p align="center">
  <img src="assets/banner.jpg" alt="Spark AI NLP banner" width="1024" />
</p>

# Jean-François Brisson · Spark AI NLP

### Applied AI research software · reproducible evaluation · evidence-first engineering

I build research software that makes claims testable: telemetry anomaly detection, evidence auditing, RAG guardrails, optical simulation, interactive AI systems, and classical simulation infrastructure.

My guiding rule is simple: **a result is useful only if another person can inspect its assumptions, rerun it, and see where it fails.**

I am Jean-François Brisson, founder of **Spark AI NLP**, a disability-led research-software initiative based in Fredericton, New Brunswick, Canada. The portfolio includes classical simulations, browser demos, offline audit tools, and C++/HLS prototypes. Each repository documents its own scope, evidence status, and limitations.

## Start here

- **Inspect the evidence:** [Spark Evidence Lab](https://sparkainlp-x.github.io/spark-evidence-lab/) — rerunnable experiment cards, explicit baselines, and negative results.
- **Review benchmarking:** [OES Resilience](https://github.com/sparkainlp-x/oes-resilience) — telemetry anomaly detection evaluated under locked conditions.
- **Explore optical simulation:** [WaveHolo](https://github.com/sparkainlp-x/waveholo) and [WaveHolo Telescope](https://github.com/sparkainlp-x/waveholo-telescope).
- **Inspect engineering rigor:** [OES-32 HLS](https://github.com/sparkainlp-x/oes32-hls) — C++/HLS prototype with bit-for-bit Python reference tests; FPGA synthesis remains unrun.
- **Try a demo:** [WaveHolo game](https://sparkainlp-x.github.io/waveholo/game/) or [Holographic Thoughts](https://sparkainlp-x.github.io/holographic-thoughts/).

I am open to applied-AI and research-software roles in Canada, independent replication, and focused technical collaborations.

## Featured scientific work

### 1. [Spark Evidence Lab](https://github.com/sparkainlp-x/spark-evidence-lab)

**Reproducible experiment cards with explicit baselines and negative results.**

Spark Evidence Lab is the evidence layer for this portfolio. Each card records the claim tested, conditions, baseline comparison, uncertainty, status, source commit, DOI where available, and commands to rerun the experiment from a clean checkout.

Its central scientific commitment is unusual and important: it reports not only reproduced results, but also cases where a simple baseline is stronger and questions that remain open.

| Verdict | Meaning |
|---|---|
| **Reproduced** | The result was rerun and matched the recorded evidence. |
| **Baseline stronger** | A simple baseline outperformed the proposed method under the stated conditions. |
| **Open question** | The result is incomplete, conditional, or requires further evaluation. |
| **Exploratory** | The experiment is directional and is not treated as confirmed evidence. |

- Live evidence board: https://sparkainlp-x.github.io/spark-evidence-lab/
- Zenodo concept DOI: [10.5281/zenodo.23403169](https://doi.org/10.5281/zenodo.23403169)
- Repository: [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab)

### 2. [OES Resilience](https://github.com/sparkainlp-x/oes-resilience)

**Telemetry anomaly detection evaluated against explicit baselines.**

This project tests anomaly-detection methods on public telemetry benchmarks, including NASA SMAP/MSL, with locked evaluation conditions and transparent reporting.

The current public result is a **negative result**: under the locked protocol, OES-32 did not meet its success criterion, and the locked OES-32-v2 re-attempt did not meet its predeclared improvement criterion. That outcome is published rather than hidden.

- Repository: [oes-resilience](https://github.com/sparkainlp-x/oes-resilience)
- DOI: [10.5281/zenodo.23071166](https://doi.org/10.5281/zenodo.23071166)
- Scientific value: transparent benchmarking, preregistered comparison, and explicit reporting of failure.

### 3. [WaveHolo](https://github.com/sparkainlp-x/waveholo)

**End-to-end off-axis digital holography: record, reconstruct, and estimate focus.**

WaveHolo implements a complete digital-holography pipeline: off-axis hologram recording, angular-spectrum reconstruction, sub-bin carrier estimation, and focus-distance estimation from the complex wavefield.

Its v0.1.5 release includes a vectorized pair-spectrum solver, a browser-only Pyodide/NetCDF research sandbox, a real-data benchmark harness, CI tests, and a public focus-estimation game.

The real-data check uses 530 microscope holograms at 6 logged stage positions. WaveHolo’s focus estimate tracks stage position with a reported slope of approximately -96.4 ± 1.3 µm/µm; the repository correctly describes this as a slope check rather than an absolute-focus validation.

- Repository: [waveholo](https://github.com/sparkainlp-x/waveholo)
- Live game: https://sparkainlp-x.github.io/waveholo/game/
- Zenodo concept DOI: [10.5281/zenodo.23644416](https://doi.org/10.5281/zenodo.23644416)
- v0.1.5 DOI: [10.5281/zenodo.23653721](https://doi.org/10.5281/zenodo.23653721)
- Honest limitation: the real-data result is a slope check, not an absolute-focus test; no metric wins on every object.

### 4. [WaveHolo Telescope](https://github.com/sparkainlp-x/waveholo-telescope)

**Synthetic telescope-pupil adaptation of the WaveHolo pipeline.**

This project applies WaveHolo’s off-axis digital-holography pipeline to a simulated telescope pupil carrying known Zernike aberrations. It measures pupil-plane focus, recovered wavefront agreement, pipeline floor, noise sensitivity, and metric failure modes.

The repository reports a measured negative result: WaveHolo’s `phase_variance` metric does not locate focus on telescope-pupil data. It also distinguishes the numerical pipeline floor from aberration-dependent error and states clearly that no real telescope data has been used.

- Repository: [waveholo-telescope](https://github.com/sparkainlp-x/waveholo-telescope)
- Status: **Synthetic only; no real telescope or instrument claim**
- Scientific value: ground-truth benchmarking, explicit limitations, and transparent reporting of a failed metric.

### 5. [OES-32 Residual](https://github.com/sparkainlp-x/oes32-residual)

**Cross-language numerical contract testing.**

A JavaScript residual port of the OES-32 reference implementation, validated against Python-generated contract vectors for bit-exact replay.

The repository demonstrates a practical pattern for keeping numerical behavior aligned across languages: generate vectors from a reference implementation, pin the source commit, regenerate them in CI, and fail the build on divergence.

- Repository: [oes32-residual](https://github.com/sparkainlp-x/oes32-residual)

### 6. [Evidence Passport](https://github.com/sparkainlp-x/evidence-passport)

**Provenance and disclosure infrastructure for AI experiments.**

A lightweight offline audit tool that turns an experiment-run manifest into a static HTML evidence passport and normalized JSON. It records declared evidence, synthetic-data status, commands, commits, DOIs, and limitations; it does not re-score or validate evidence.

- Repository: [evidence-passport](https://github.com/sparkainlp-x/evidence-passport)
- DOI: [10.5281/zenodo.23165143](https://doi.org/10.5281/zenodo.23165143)
- Sample passports: https://sparkainlp-x.github.io/evidence-passport/

## Research principles

1. **Baselines first.** A method is meaningful only relative to a clearly specified alternative.
2. **Negative results are results.** Where a baseline wins, I report it.
3. **Pin the evidence.** Important claims link to an exact commit, dataset definition, command, or DOI.
4. **Label uncertainty.** Reproduced, exploratory, and open questions are not presented as equivalent.
5. **Separate simulation from reality.** Synthetic data, browser replays, simulator-only work, and hardware claims are explicitly distinguished.
6. **Make rerunning easy.** A clean checkout should be enough to reproduce the result.

## Technical focus

| Area | Focus | Representative work |
|---|---|---|
| Anomaly detection | Telemetry benchmarks, baselines, threshold transparency | [oes-resilience](https://github.com/sparkainlp-x/oes-resilience), [oes512q-latch](https://github.com/sparkainlp-x/oes512q-latch) |
| Evidence infrastructure | Experiment cards, provenance, reproducibility | [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab), [evidence-passport](https://github.com/sparkainlp-x/evidence-passport) |
| Optical simulation and holography | Digital holography, wavefront reconstruction, focus estimation | [waveholo](https://github.com/sparkainlp-x/waveholo), [waveholo-telescope](https://github.com/sparkainlp-x/waveholo-telescope) |
| RAG reliability | Retrieval guardrails, failure modes, evaluation | [spark-rag-guardrail](https://github.com/sparkainlp-x/spark-rag-guardrail) |
| Numerical software | Contract vectors, cross-language replay, CI | [oes32-residual](https://github.com/sparkainlp-x/oes32-residual) |
| C++ / HLS | Decoder prototyping, testbenches, hardware readiness | [oes32-hls](https://github.com/sparkainlp-x/oes32-hls), [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp) |
| Simulation | Classical toy models, scaling experiments, visualization | [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench), [membrane-crystallization](https://github.com/sparkainlp-x/membrane-crystallization) |
| Interactive systems | Accessibility-oriented AI interfaces and prototypes | [thought-input-game](https://github.com/sparkainlp-x/thought-input-game), [world-holobridge](https://github.com/sparkainlp-x/world-holobridge) |

## Recommended pinned repositories

1. [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab)
2. [oes-resilience](https://github.com/sparkainlp-x/oes-resilience)
3. [waveholo](https://github.com/sparkainlp-x/waveholo)
4. [waveholo-telescope](https://github.com/sparkainlp-x/waveholo-telescope)
5. [oes32-residual](https://github.com/sparkainlp-x/oes32-residual)
6. [evidence-passport](https://github.com/sparkainlp-x/evidence-passport)

## Evidence and maturity labels

Each project is placed on one rung. The rung says what exists today, not what is hoped for.

| Rung | Meaning |
|---|---|
| **Demonstrated** | The code runs, tests pass in CI, and the stated result was reproduced from a fixed seed or named dataset. |
| **Prototype** | A working simulation or browser demo with tests, but no measurement outside the repository. |
| **Concept** | An architectural idea, model, or proposed measurement with little or no running code. |
| **Target** | A design goal that has not been reached or measured. |

These rungs sit on top of evidence tags used across repositories:

| Tag | Meaning |
|---|---|
| **SYNTHETIC** | Produced by our own simulation or tests on generated inputs. |
| **REPORTED** | Based on identified measurements or benchmark data, with source, conditions, and reproduction status stated. |
| **TARGET** | A design goal; not yet achieved or measured. |
| **UNRUN** | Tooling or scripts exist; the run has not been performed. |

## Claims policy

- Everything here is classical software. Results are SYNTHETIC unless a README names a measured dataset and its protocol, in which case they are tagged REPORTED.
- No repository reports a result from quantum hardware, a physical membrane, a medical device, or a field deployment.
- Nothing is described as established beyond what its tests and data support. Negative results are published as measured.
- Unrun work—including FPGA synthesis, hardware-in-the-loop testing, and independent review—is labelled UNRUN.
- Design goals are labelled TARGET.
- If a statement looks unsupported, open a Claim correction issue using the template in [sparkainlp-x/.github](https://github.com/sparkainlp-x/.github).

## How the work is done

- **Contracts first:** definitions live in one normative place with executable tests; for OES-32, see [oes32-residual ADR-001](https://github.com/sparkainlp-x/oes32-residual/tree/b77b61254f15778c6ae221843dceac7a8571158e).
- **Fail closed:** selected READMEs label unrun or unmeasured work, including negative outcomes where evaluations were performed.
- **Minimal dependencies:** many tools use only the Python standard library; others use NumPy, Stim, PyMatching, or upstream `ldpc` where justified.
- **Tests and CI:** repositories include tests and continuous integration where appropriate.
- **Open licensing:** most repositories are AGPL-3.0-only with a commercial-licence option; some use MIT or MIT OR Apache-2.0. Each repository’s LICENSE file is authoritative.
- **Archived releases:** released versions are archived on Zenodo with concept and version DOIs.
- **Accessibility first:** ask for alternative formats by opening an issue in any repository.

## Selected evidence

| Experiment | Status | Source |
|---|---|---|
| Blind NASA SMAP/MSL test, OES32 v1 vs baselines | **Baseline stronger / criterion not met** | [oes-resilience](https://github.com/sparkainlp-x/oes-resilience) |
| OES-32-v2 locked re-attempt | **Criterion not met** | [oes-resilience](https://github.com/sparkainlp-x/oes-resilience) |
| OES-32 residual JS port and live replay | **Reproduced** | [oes32-residual](https://github.com/sparkainlp-x/oes32-residual) |
| WaveHolo real-data microscope slope check | **REPORTED; slope check, not absolute-focus validation** | [waveholo](https://github.com/sparkainlp-x/waveholo) |
| WaveHolo Telescope pupil reconstruction and metric failure | **Synthetic; negative result for `phase_variance`** | [waveholo-telescope](https://github.com/sparkainlp-x/waveholo-telescope) |
| OES-512 synthetic 512-channel stream | **Exploratory** | [oes512-telemetry-engine](https://github.com/sparkainlp-x/oes512-telemetry-engine) |
| Surface-code memory toy, Stim + PyMatching | **Open question** | [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench) |

These entries are drawn from the public Spark Evidence Lab and the relevant repository READMEs, where each result includes conditions, uncertainty, source commit, rerun instructions, and links to archived artifacts where available.

## Core project tracks

Every public repository belongs to one of six tracks. Repositories remain separate so each keeps its own licence, release history, and, where released, Zenodo DOI.

### 1. Evidence and reproducibility

Evidence records, provenance, replay, guardrails, and small offline tools, plus deterministic runtimes and audit trails that make a run checkable.

Main repositories: [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab), [failure-capsules](https://github.com/sparkainlp-x/failure-capsules), [evidence-passport](https://github.com/sparkainlp-x/evidence-passport), [measurement-trail](https://github.com/sparkainlp-x/measurement-trail), [spark-rag-guardrail](https://github.com/sparkainlp-x/spark-rag-guardrail), [identity-runtime](https://github.com/sparkainlp-x/identity-runtime).

### 2. Telemetry anomaly detection

The OES-32 / OES-512 residual-latch family, benchmarks, a normative residual definition, and HLS testbenches. Detectors are benchmarked against simple baselines; outcomes are published as measured, including negative results.

Main repositories: [oes-resilience](https://github.com/sparkainlp-x/oes-resilience), [oes32-residual](https://github.com/sparkainlp-x/oes32-residual), [oes32-hls](https://github.com/sparkainlp-x/oes32-hls), [oes512q-latch](https://github.com/sparkainlp-x/oes512q-latch), [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp).

### 3. Holographic and interactive systems

Classical models of holographic memory, digital holography, streaming PCA, capacity limits, refusal gates, browser games, teaching prototypes, and visual/interface experiments. These are synthetic or prototype systems unless a repository states otherwise.

Main repositories: [waveholo](https://github.com/sparkainlp-x/waveholo), [waveholo-telescope](https://github.com/sparkainlp-x/waveholo-telescope), [membrane-crystallization](https://github.com/sparkainlp-x/membrane-crystallization), [crystallization-contest](https://github.com/sparkainlp-x/crystallization-contest), [membrane-committee](https://github.com/sparkainlp-x/membrane-committee), [holographic-thoughts](https://github.com/sparkainlp-x/holographic-thoughts), [thought-input-game](https://github.com/sparkainlp-x/thought-input-game).

### 4. Quantum-inspired experiments

Classical emulations and toy models, plus tools that audit how scientific claims are worded. All results are classical software; no quantum hardware is involved.

Main repositories: [quantum-projection](https://github.com/sparkainlp-x/quantum-projection), [claims-layer](https://github.com/sparkainlp-x/claims-layer), [quantum-claims-passport](https://github.com/sparkainlp-x/quantum-claims-passport), [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench).

### 5. C++ / HLS engineering

C++ software and HLS automation scripts for a qLDPC decoder targeting the AMD ZCU111 RFSoC. CI builds and tests the portable C++ code. FPGA synthesis, timing closure, and hardware-in-the-loop runs are UNRUN; there are no hardware results.

Main repositories: [oes32-hls](https://github.com/sparkainlp-x/oes32-hls), [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp).

### 6. Community and accessibility

Governance and accessibility-first work, including a reference prototype for community-led cultural and spatial-media projects and a bilingual browser plan generator. It is not legal advice and no community endorsement is claimed.

Main repositories: [world-holobridge](https://github.com/sparkainlp-x/world-holobridge), [signal-loom](https://github.com/sparkainlp-x/signal-loom).

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

## Contact and links

<p align="center">
  <a href="https://sparkainlpx.xyz">sparkainlpx.xyz</a> ·
  <a href="https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4">LinkedIn</a> ·
  <a href="https://sparkainlp-x.github.io/spark-evidence-lab/">Spark Evidence Lab</a> ·
  <a href="https://sparkainlp-x.github.io/waveholo/game/">WaveHolo</a> ·
  <a href="https://sparkainlp-x.github.io/holographic-thoughts/">Holographic Thoughts</a> ·
  <a href="https://orcid.org/0009-0000-9778-5374">ORCID</a> ·
  <a href="https://zenodo.org/communities/spark-ai-nlp/">Zenodo community</a>
</p>

- Website: [sparkainlpx.xyz](https://sparkainlpx.xyz)
- LinkedIn: [Jean-François Brisson](https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4)
- ORCID: [0009-0000-9778-5374](https://orcid.org/0009-0000-9778-5374)
- Questions about code: open an issue in the relevant repository
- Français (langue maternelle) · English (fluent)

## Acknowledgements

Mun Seok Lee and Somnath Laha are acknowledged as collaborators. Lee’s *Digital to Wave* preprints and packages received under his name are the source for the Digital-to-Wave repositories and the membrane-related repositories that say so in their Provenance sections. Laha’s related discussion of a satellite concept motivated the framing of [orbit-wave-oes-lab](https://github.com/sparkainlp-x/orbit-wave-oes-lab).

This is an acknowledgement only. It implies no endorsement of these repositories and no authorship. The software is by Jean-François Brisson, and each repository’s README states what it derives from.

## Open to

Applied AI research and research-software roles, remote within Canada or on site in Fredericton; collaboration with research groups, FPGA/decoder engineers, optics researchers, and accessibility-focused partners; independent replication and focused technical collaborations.

## Full project index

This index links project names to their canonical public repositories. A direct match identifies the corresponding public project; it is not a claim of scientific validation. Related projects are separate implementations or tools, and their individual READMEs define their scope and evidence.

The account currently contains 115 public repositories. Zenodo records are being added to the [Spark AI NLP: Research Software](https://zenodo.org/communities/spark-ai-nlp/) community; use each repository README for its authoritative citation and DOI details.

For the complete repository list, see: https://github.com/sparkainlp-x?tab=repositories

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