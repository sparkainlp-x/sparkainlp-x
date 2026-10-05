<p align="center">
  <img
    src="assets/banner.jpg"
    alt="Spark AI NLP banner: glowing brain-circuit logo with the words SPARK AI NLP over a dark lab scene"
    width="1024"
  />
</p>

<h1 align="center">Spark AI NLP</h1>

<p align="center">
  Disability-led research software from Fredericton, NB, Canada.<br/>
  Reproducible telemetry anomaly detection, C++/HLS research prototypes, RAG guardrails, and offline provenance tools, with an evidence tag on every number.
</p>

<p align="center">
  <a href="https://sparkainlpx.xyz">sparkainlpx.xyz</a> ·
  <a href="https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4">LinkedIn</a> ·
  <a href="https://orcid.org/0009-0000-9778-5374"><img src="https://img.shields.io/badge/ORCID-0009--0000--9778--5374-A6CE39?logo=orcid&logoColor=white" alt="ORCID iD 0009-0000-9778-5374" height="20" /></a> ·
  <a href="https://zenodo.org/communities/spark-ai-nlp/"><img src="https://img.shields.io/badge/Zenodo-Spark%20AI%20NLP-1682D4?logo=zenodo&logoColor=white" alt="Zenodo community: Spark AI NLP: Research Software" height="20" /></a><br/>
  Founder: Jean-François Brisson · Français (langue maternelle) · English (fluent)
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Focus-Research%20Prototyping-2563EB?style=for-the-badge" alt="Research prototyping" />
  <img src="https://img.shields.io/badge/Systems-C%2B%2B%20%7C%20Python-0F766E?style=for-the-badge" alt="C++ and Python" />
  <img src="https://img.shields.io/badge/HLS%20%2F%20FPGA-TARGET-7C3AED?style=for-the-badge" alt="HLS and FPGA: TARGET (design goal, synthesis not yet run)" />
  <img src="https://img.shields.io/badge/Method-Evidence--tagged-0891B2?style=for-the-badge" alt="Evidence-tagged research" />
</p>

> **Open to work:** applied AI research and research-software roles, remote within Canada or on site in Fredericton. Contact details are [below](#contact).

## About

Spark AI NLP is a disability-led research-software company based in Fredericton, New Brunswick, Canada. The public repositories are **research prototypes**: a reproducible telemetry anomaly-detection benchmark, the OES-32/OES-512 residual-latch family, C++/HLS kernels, a source-grounded RAG guardrail, and small offline tools for provenance and consent-first data sharing. They are not hardware products, field products, or medical products, and they do not report results on quantum hardware.

## Featured work

| Repository | What it is | Evidence status | Archive |
|---|---|---|---|
| [**oes-resilience**](https://github.com/sparkainlp-x/oes-resilience) · v0.5.0 | Open, reproducible benchmark for 512-channel telemetry anomaly detection with the transparent one-line OES32 reference detector; stress suite, replay evaluation, detector plugin API, and a preregistered NASA SMAP/MSL comparison | Baseline SYNTHETIC (byte-reproduced in CI). On SMAP/MSL under the locked protocol, OES32 did **not** meet its success criterion | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23071166.svg)](https://doi.org/10.5281/zenodo.23071166) |
| [**oes32-hls**](https://github.com/sparkainlp-x/oes32-hls) · v0.3.0 | C++ HLS prototype of OES-32 triage: streaming AXI4-Stream kernel, pybind11 bindings, and pytest + Hypothesis tests comparing it bit for bit with a Python reference model | `g++` testbenches and Python tests run in CI on SYNTHETIC stimuli; FPGA synthesis UNRUN (ZCU111 is a TARGET) | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22985525.svg)](https://doi.org/10.5281/zenodo.22985525) |
| [**oes512q-latch**](https://github.com/sparkainlp-x/oes512q-latch) · v0.2.0 | OES-32/OES-512 classical residual latch with a self-calibrated threshold, compared with standard unsupervised detectors on all 47 labelled real-data series in the Numenta Anomaly Benchmark (NAB) | NAB numbers REPORTED (mixed results, reported as measured); unit tests SYNTHETIC; not a quantum code | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22998570.svg)](https://doi.org/10.5281/zenodo.22998570) |
| [**multi-quantum-oes**](https://github.com/sparkainlp-x/multi-quantum-oes) · v0.1.1 | Offline, standard-library-only OES-512 replay-triage workbench with a preregistered stress evaluation, plus an isolated "AI ∩ quantum" toy lab | Stress result is **negative** and published as such; SYNTHETIC data; exact classical simulation, not a QPU | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23113851.svg)](https://doi.org/10.5281/zenodo.23113851) |
| [**digital-to-wave-testbench**](https://github.com/sparkainlp-x/digital-to-wave-testbench) · v0.4.1 | Synthetic, dimensionless software testbench for a signed-amplitude sine encoding (noise, phase, CFO, timing; Wilson CIs) | All results SYNTHETIC; no physical validity claimed | [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23122876.svg)](https://doi.org/10.5281/zenodo.23122876) |
| [**evidence-passport**](https://github.com/sparkainlp-x/evidence-passport) · v0.1.0 | Offline stdlib MVP: one experiment-run manifest → static HTML evidence passport + normalized JSON (fail-closed SHA-256) | Bundled OES-Resilience SMAP/MSL sample: criterion **not** met; three further examples labelled SYNTHETIC; [sample pages](https://sparkainlp-x.github.io/evidence-passport/); DOI pending | — |

<details>
<summary>Other public repositories</summary>

**More research software**

- [oes32-residual](https://github.com/sparkainlp-x/oes32-residual): the **normative** OES-32 residual (ADR-001) with 12 contract tests in CI (Python 3.11–3.13).
- [oes32-membrane-shield](https://github.com/sparkainlp-x/oes32-membrane-shield): 32-slot state machine gated by Ed25519 capabilities, with dual-approval calibration; 25 tests, including fuzz tests, pass in CI; independent security review UNRUN.
- [spark-rag-guardrail](https://github.com/sparkainlp-x/spark-rag-guardrail): source-grounded RAG (ChromaDB + Ollama) that refuses to answer when retrieval relevance is too low; 10 tests on SYNTHETIC fixtures; answer quality UNRUN.

**Offline tools**

- [context-wallet](https://github.com/sparkainlp-x/context-wallet): user-selected, short-lived JSON context packets (preview before export). [DOI 10.5281/zenodo.23061441](https://doi.org/10.5281/zenodo.23061441)
- [measurement-trail](https://github.com/sparkainlp-x/measurement-trail): SHA-256 hash-chained measurement provenance trails. [DOI 10.5281/zenodo.23067465](https://doi.org/10.5281/zenodo.23067465)
- [coil-efficiency-bench](https://github.com/sparkainlp-x/coil-efficiency-bench): paired motor-efficiency analysis with a Student's t CI; bundled data SYNTHETIC. [DOI 10.5281/zenodo.23067995](https://doi.org/10.5281/zenodo.23067995)

**Smaller prototypes and demos**

[address-phase-demo](https://github.com/sparkainlp-x/address-phase-demo) (FR educational HTML; SYNTHETIC) ·
[spark-oes512-demo](https://github.com/sparkainlp-x/spark-oes512-demo) (browser OES32-style demo; SYNTHETIC) ·
[oes512-residual](https://github.com/sparkainlp-x/oes512-residual) ·
[pilottrace](https://github.com/sparkainlp-x/pilottrace) ·
[signal-commons](https://github.com/sparkainlp-x/signal-commons) ·
[signal-test-commons](https://github.com/sparkainlp-x/signal-test-commons) ·
[internal-outage-radar](https://github.com/sparkainlp-x/internal-outage-radar) ·
[web-delta-feed](https://github.com/sparkainlp-x/web-delta-feed) ·
[pocket-internet](https://github.com/sparkainlp-x/pocket-internet) ·
[oes32_engine](https://github.com/sparkainlp-x/oes32_engine) ·
[qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp) (C++/HLS decoder scaffold; BP kernel placeholder; hardware UNRUN) ·
[phmt4-montecarlo](https://github.com/sparkainlp-x/phmt4-montecarlo) (heuristic classical simulation) ·
[quantum-error-correction-demo](https://github.com/sparkainlp-x/quantum-error-correction-demo) (classical toy; no qubits, no QEC code)

Each repository's README covers its scope, its limits, and evidence tags.

</details>

Most public research repositories are archived on Zenodo with DOIs (see each README) and grouped in the [Spark AI NLP: Research Software](https://zenodo.org/communities/spark-ai-nlp/) Zenodo community.

## How I work

- **Contracts first.** Each definition lives in one normative place with executable tests. For OES-32 that is [oes32-residual@b77b612](https://github.com/sparkainlp-x/oes32-residual/tree/b77b61254f15778c6ae221843dceac7a8571158e) (ADR-001); other implementations are labelled Profile A sidecars and document how they differ.
- **Fail-closed.** Invalid input is rejected rather than guessed, and so are claims: if something has not been run or measured, the README says so. Negative results are published too.
- **Evidence tags on every number.**

  | Tag | Meaning |
  |---|---|
  | **SYNTHETIC** | Produced by our own simulation or tests on generated inputs |
  | **REPORTED** | Measured by us; not independently reproduced. The README gives the host and conditions, or states plainly that they are unspecified |
  | **TARGET** | A design goal; not yet achieved or measured |
  | **UNRUN** | Tooling or scripts exist; the run has not been performed |

- **Reproducible by default.** Each README's Quickstart was run from a fresh clone or is marked UNRUN, and repositories with code run their tests in CI on every change.
- **Accessibility first.** Ask for alternative formats by opening an issue in any repository.

Contribution guidelines, the code of conduct, and the security policy are shared across all repositories: [sparkainlp-x/.github](https://github.com/sparkainlp-x/.github).

## Cite

Each archived repository has a `CITATION.cff` file (use GitHub's **"Cite this repository"** button) and a Zenodo concept DOI covering all versions. To refer to exact code, cite the version DOI listed in that repository's README. All records are in the [Zenodo community](https://zenodo.org/communities/spark-ai-nlp/).

## Contact

Open to applied AI research and research-software roles (remote within Canada, or Fredericton, NB), and to collaboration with research groups, FPGA/decoder engineers, and accessibility-focused partners.

- Website: [sparkainlpx.xyz](https://sparkainlpx.xyz)
- LinkedIn: [Jean-François Brisson](https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4)
- ORCID: [0009-0000-9778-5374](https://orcid.org/0009-0000-9778-5374)
- Questions about code: open an issue in the relevant repository
