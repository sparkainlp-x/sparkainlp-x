<p align="center">
  <img
    src="assets/banner.jpg"
    alt="Spark AI NLP banner: glowing brain-circuit logo with the words SPARK AI NLP over a dark lab scene"
    width="1024"
  />
</p>

# Spark AI NLP

I build reproducible research software for telemetry analysis, evidence auditing, and interactive learning.

I’m Jean-François Brisson, founder of Spark AI NLP, a disability-led research-software initiative based in Fredericton, New Brunswick, Canada.

My projects make assumptions, baseline comparisons, and failure cases explicit. The portfolio includes classical simulations, browser demos, offline audit tools, and C++/HLS prototypes. Each repository documents its own scope and evidence status.

## Start here

- Explore the evidence: Spark Evidence Lab — experiments, baselines, and rerun instructions.
- Try a demo: Thought-Input Game — draw a pattern and explore associative recall.
- Inspect an engineering project: OES-32 HLS — a software-tested C++ prototype; FPGA synthesis remains unrun.

Open to research-software and applied-AI roles in Canada, independent replication, and focused technical collaborations.

## Contact / links

<p align="center">
  <a href="https://sparkainlpx.xyz">sparkainlpx.xyz</a> ·
  <a href="https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4">LinkedIn</a> ·
  <a href="https://notebook.google.com/notebook/cfd4dba3-0a62-4076-8169-99c2e092d56f">Research notebook</a> ·
  <a href="https://sparkainlp-x.github.io/holographic-thoughts/">Live demo: Holographic Thoughts</a> ·
  <a href="https://orcid.org/0009-0000-9778-5374">ORCID</a> ·
  <a href="https://zenodo.org/communities/spark-ai-nlp/">Zenodo community</a><br/>
  Français (langue maternelle) · English (fluent)
</p>

- Website: [sparkainlpx.xyz](https://sparkainlpx.xyz)
- LinkedIn: [Jean-François Brisson](https://www.linkedin.com/in/jean-fran%C3%A7ois-brisson-41927b3a4)
- Research notebook: [Spark AI NLP notebook](https://notebook.google.com/notebook/cfd4dba3-0a62-4076-8169-99c2e092d56f)
- Live demo: [Holographic Thoughts](https://sparkainlp-x.github.io/holographic-thoughts/) (interactive toy views; synthetic, classical simulation)
- ORCID: [0009-0000-9778-5374](https://orcid.org/0009-0000-9778-5374)
- Questions about code: open an issue in the relevant repository

Acknowledgements: Mun Seok Lee and Somnath Laha are acknowledged as collaborators. Lee's *Digital to Wave* preprints and packages received under his name are the source for the Digital-to-Wave repositories and the membrane-related repositories that say so in their Provenance sections. Laha's related discussion of a satellite concept motivated the framing of [orbit-wave-oes-lab](https://github.com/sparkainlp-x/orbit-wave-oes-lab). This is an acknowledgement only: it implies no endorsement of these repositories and no authorship. The software is by Jean-François Brisson, and each repository's README states what it derives from.

## Open to

Applied AI research and research-software roles, remote within Canada or on site in Fredericton; collaboration with research groups, FPGA/decoder engineers, and accessibility-focused partners; independent replication and focused technical collaborations.

## Evidence and maturity labels

Each project is placed on one rung. The rung says what exists today, not what is hoped for.

| Rung | Meaning |
|---|---|
| Demonstrated | The code runs, the tests pass in CI, and the stated result was reproduced from a fixed seed or a named dataset |
| Prototype | A working simulation or browser demo with tests, but no measurement outside the repository |
| Concept | An architectural idea, a model or a proposed measurement, with little or no running code |
| Target | A design goal that has not been reached or measured |

The rungs sit on top of the evidence tags used in every repository:

| Tag | Meaning |
|---|---|
| **SYNTHETIC** | Produced by our own simulation or tests on generated inputs |
| **REPORTED** | A project result based on identified measurements or benchmark data. The README states whether data were collected for this project or pre-existing, names the source and conditions/protocol, and says whether independently reproduced |
| **TARGET** | A design goal; not yet achieved or measured |
| **UNRUN** | Tooling or scripts exist; the run has not been performed |

Claims policy:

- Everything here is classical software. Results are SYNTHETIC unless a README names a measured dataset and its protocol, and then they are tagged REPORTED.
- No repository reports a result from quantum hardware, a physical membrane, a medical device or a field deployment.
- Nothing is described as established beyond what its tests and data support. Negative results are published as measured.
- Unrun work (hardware synthesis, hardware-in-the-loop, independent review) is labelled UNRUN, and design goals are labelled TARGET.
- If a statement here or in a repository looks unsupported, open a Claim correction issue; the template is in [sparkainlp-x/.github](https://github.com/sparkainlp-x/.github).

How this work is done, in brief: contracts first (each definition lives in one normative place with executable tests; for OES-32 that is [oes32-residual@b77b612](https://github.com/sparkainlp-x/oes32-residual/tree/b77b61254f15778c6ae221843dceac7a8571158e) (ADR-001)); fail-closed where specified (selected READMEs label unrun or unmeasured work, including negative outcomes where evaluations were performed); minimal dependencies where the work allows (many tools use only the Python standard library, for example identity-runtime, world-holobridge, evidence-passport and multi-quantum-oes; oes-resilience requires NumPy, qec-scaling-bench uses Stim and PyMatching, and qldpc_decoder_cpp builds against the upstream `ldpc` library); tests and CI per repository; open licences per repository (most AGPL-3.0-only with a commercial-licence option; some MIT; world-holobridge MIT OR Apache-2.0; each repository's LICENSE file is authoritative); released versions archived on Zenodo with concept and version DOIs. Accessibility first: ask for alternative formats by opening an issue in any repository. Contribution guidelines, the code of conduct, and the security policy are shared across all repositories: [sparkainlp-x/.github](https://github.com/sparkainlp-x/.github).

## Core project tracks

Every public repository belongs to one of six tracks. Repositories stay separate so that each keeps its own licence and release history, and its own Zenodo DOI once released. Repositories not named here are listed in the Full project index below and on the [repository list](https://github.com/sparkainlp-x?tab=repositories).

### 1. Evidence and reproducibility

Evidence records, provenance, replay, guardrails and small offline tools, plus the deterministic runtimes and audit trails that make a run checkable: the OES-61440 tripwire (in identity-runtime: 61,440 fixed threshold channels, grouped as 1,920 membranes of 32 channels; weights and thresholds come from SHA-256 of the channel index, are illustrative, not calibrated against incident data, and the tripwire is not a safety guarantee; a plain rule holds any action with effective risk of 0.5 or more for a human) and a hash-chained ledger (every step appended to a JSONL ledger in which each entry's hash covers the previous entry's hash; tamper-evident, not tamper-proof).

Main repositories: [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab), [failure-capsules](https://github.com/sparkainlp-x/failure-capsules), [evidence-passport](https://github.com/sparkainlp-x/evidence-passport), [measurement-trail](https://github.com/sparkainlp-x/measurement-trail), [spark-rag-guardrail](https://github.com/sparkainlp-x/spark-rag-guardrail), [identity-runtime](https://github.com/sparkainlp-x/identity-runtime)

### 2. Telemetry anomaly detection

The OES-32 / OES-512 residual-latch family, benchmarks, a normative residual definition and HLS testbenches. Deterministic residual-telemetry triage: fixed 32-channel blocks, transparent scores and fail-closed input contracts, with one normative residual definition ([oes32-residual](https://github.com/sparkainlp-x/oes32-residual), ADR-001). Detectors are benchmarked against simple baselines and the outcomes are published as measured, including negative results.

Main repositories: [oes-resilience](https://github.com/sparkainlp-x/oes-resilience), [oes32-residual](https://github.com/sparkainlp-x/oes32-residual), [oes32-hls](https://github.com/sparkainlp-x/oes32-hls), [oes512q-latch](https://github.com/sparkainlp-x/oes512q-latch), [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp)

### 3. Holographic and interactive systems

Classical models of holographic memory, streaming PCA with a Hebbian running average, committees, capacity limits, refusal gates and reward contests between agents; a heart-shaped associative-memory toy and a sonification of a phase-oscillator ring, both SYNTHETIC; several negative results. Visual and interface prototypes, governance for community media, and browser games and teaching prototypes, seeded and offline.

Main repositories: [membrane-crystallization](https://github.com/sparkainlp-x/membrane-crystallization), [crystallization-contest](https://github.com/sparkainlp-x/crystallization-contest), [membrane-committee](https://github.com/sparkainlp-x/membrane-committee), [refusing-membrane](https://github.com/sparkainlp-x/refusing-membrane), [membrane-capacity](https://github.com/sparkainlp-x/membrane-capacity), [membrane-heart](https://github.com/sparkainlp-x/membrane-heart), [membrane-listen](https://github.com/sparkainlp-x/membrane-listen), [holographic-thoughts](https://github.com/sparkainlp-x/holographic-thoughts), [sparky-synthetic-grove](https://github.com/sparkainlp-x/sparky-synthetic-grove), [world-holobridge](https://github.com/sparkainlp-x/world-holobridge), [signal-loom](https://github.com/sparkainlp-x/signal-loom), [crystallize](https://github.com/sparkainlp-x/crystallize), [infinite-becoming](https://github.com/sparkainlp-x/infinite-becoming), [empty-state-observatory](https://github.com/sparkainlp-x/empty-state-observatory), [address-phase-demo](https://github.com/sparkainlp-x/address-phase-demo), [thought-input-game](https://github.com/sparkainlp-x/thought-input-game)

Note on a repository name: [crystal-bci](https://github.com/sparkainlp-x/crystal-bci) is a repository name only; nothing here describes what that name abbreviates.

### 4. Quantum-inspired experiments

Classical emulations and toy models, and tools that audit how claims are worded. All results here are classical software; no quantum hardware is involved.

Main repositories: [quantum-projection](https://github.com/sparkainlp-x/quantum-projection), [claims-layer](https://github.com/sparkainlp-x/claims-layer), [quantum-claims-passport](https://github.com/sparkainlp-x/quantum-claims-passport), [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench)

### 5. C++ / HLS engineering

C++ software and HLS automation scripts for a qLDPC decoder targeting the AMD ZCU111 RFSoC; see [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp). CI builds and tests the portable C++ code. FPGA synthesis, timing closure and hardware-in-the-loop runs are UNRUN, and no qubits or quantum hardware are involved. There are no hardware results.

Main repositories: [oes32-hls](https://github.com/sparkainlp-x/oes32-hls), [qldpc_decoder_cpp](https://github.com/sparkainlp-x/qldpc_decoder_cpp)

### 6. Community and accessibility

Governance for community media and accessibility-first work: a reference prototype of a governance workflow for community-led cultural and spatial-media projects, with a bilingual browser plan generator (not legal advice; no community endorsement claimed), and the accessibility-first practice described under Evidence and maturity labels above.

Main repositories: [world-holobridge](https://github.com/sparkainlp-x/world-holobridge), [signal-loom](https://github.com/sparkainlp-x/signal-loom)

## Latest release snapshot

Featured repositories, in the five-line format (name; purpose; demonstrated result or current status; key limitation or unrun step; link). Results below are carried over from the existing profile table; they were not newly re-verified repo by repo for this restructure.

- **oes-resilience** · v0.6.0
  - Open, reproducible benchmark for 512-channel telemetry anomaly detection with the transparent one-line OES32 reference detector; stress suite, replay evaluation, detector plugin API, a preregistered NASA SMAP/MSL comparison, and adaptive methods (v0.6.0).
  - Baseline SYNTHETIC (byte-reproduced in CI). On SMAP/MSL under the locked protocol, OES32 did **not** meet its success criterion; the locked OES-32-v2 re-attempt did **not** meet its predeclared improvement criterion.
  - Limitation: the SMAP/MSL comparison is a negative result, not a success.
  - [Repository](https://github.com/sparkainlp-x/oes-resilience) · [DOI 10.5281/zenodo.23071166](https://doi.org/10.5281/zenodo.23071166)
- **oes32-hls** · v0.3.1
  - C++ HLS prototype of OES-32 triage: streaming AXI4-Stream kernel, pybind11 bindings, and pytest + Hypothesis tests comparing it bit for bit with a Python reference model.
  - `g++` testbenches and Python tests run in CI on SYNTHETIC stimuli.
  - Unrun step: FPGA synthesis UNRUN (ZCU111 is a TARGET).
  - [Repository](https://github.com/sparkainlp-x/oes32-hls) · [DOI 10.5281/zenodo.22985525](https://doi.org/10.5281/zenodo.22985525)
- **oes512q-latch** · v0.2.1
  - OES-32/OES-512 classical residual latch with a self-calibrated threshold, compared with standard unsupervised detectors on all 47 labelled real-data series in the Numenta Anomaly Benchmark (NAB).
  - NAB numbers REPORTED (mixed results, reported as measured); unit tests SYNTHETIC; not a quantum code.
  - Limitation: mixed NAB results, not a uniform win.
  - [Repository](https://github.com/sparkainlp-x/oes512q-latch) · [DOI 10.5281/zenodo.22998570](https://doi.org/10.5281/zenodo.22998570)
- **multi-quantum-oes** · v0.1.2
  - Offline, standard-library-only OES-512 replay-triage workbench with a preregistered stress evaluation, plus an isolated "AI ∩ quantum" toy lab.
  - Stress result is **negative** and published as such; SYNTHETIC data; exact classical simulation, not a QPU.
  - Limitation: the stress evaluation did not support the toy lab's premise.
  - [Repository](https://github.com/sparkainlp-x/multi-quantum-oes) · [DOI 10.5281/zenodo.23113851](https://doi.org/10.5281/zenodo.23113851)
- **digital-to-wave-testbench** · v0.4.2
  - Synthetic, dimensionless software testbench for a signed-amplitude sine encoding (noise, phase, CFO, timing; Wilson CIs).
  - All results SYNTHETIC; no physical validity claimed.
  - Limitation: synthetic only; no physical validity claim.
  - [Repository](https://github.com/sparkainlp-x/digital-to-wave-testbench) · [DOI 10.5281/zenodo.23122876](https://doi.org/10.5281/zenodo.23122876)
- **evidence-passport** · v0.1.1
  - Offline stdlib audit tool: one experiment-run manifest → static HTML evidence passport + normalized JSON (fail-closed SHA-256); records declared evidence, never re-scores it.
  - Bundled OES-Resilience SMAP/MSL sample keeps the verdict: criterion **not** met; three further examples labelled SYNTHETIC; [sample pages](https://sparkainlp-x.github.io/evidence-passport/).
  - Limitation: it records evidence, it does not re-score or validate it.
  - [Repository](https://github.com/sparkainlp-x/evidence-passport) · [DOI 10.5281/zenodo.23165143](https://doi.org/10.5281/zenodo.23165143)
- **quantum-claims-passport** · v0.1.0
  - Offline claims audit for scientific communication: classifies public claims (a planned Swiss quantum-computer hub; a modeled 613 THz tubulin frequency band; a rat behavioral study) as announcement, computational model, animal behavioral result, hypothesis, or unsupported inference, with exact-SI conversions and no combined score.
  - Source audit only, snapshot 2026-10-05; makes none of the audited claims; no affiliation with the institutions named; [report](https://sparkainlp-x.github.io/quantum-claims-passport/report.html).
  - Limitation: a source audit of wording, not a re-experiment.
  - [Repository](https://github.com/sparkainlp-x/quantum-claims-passport) · [DOI 10.5281/zenodo.23167801](https://doi.org/10.5281/zenodo.23167801)

Recent work (from the previous profile, unchanged in substance):

- [membrane-listen](https://github.com/sparkainlp-x/membrane-listen) · v0.1.0: SYNTHETIC sonification of a classical phase-oscillator ring (standard-library Python, AGPL-3.0-only); a pre-registered study with confidence intervals in which 2 of 23 hypotheses were not supported; not a recording, not a medical model; no listening test was run. [DOI 10.5281/zenodo.23687758](https://doi.org/10.5281/zenodo.23687758)
- [membrane-heart](https://github.com/sparkainlp-x/membrane-heart) · v0.1.0: SYNTHETIC toy in which a heart-shaped network of 64 simulated neurons carries a phase wave stored in an associative memory with a calibrated gate that names or refuses a probe (standard-library Python, AGPL-3.0-only); not a medical model, not a diagnosis. [DOI 10.5281/zenodo.23680672](https://doi.org/10.5281/zenodo.23680672)
- [identity-runtime](https://github.com/sparkainlp-x/identity-runtime): standard-library Python runtime for governed, reversible avatar personalities, with human approval quorums, expiring capability leases, the OES-61440 tripwire and a hash-chained ledger; 99 tests in CI; not tested against real attackers; [demo page](https://sparkainlp-x.github.io/identity-runtime/). [DOI 10.5281/zenodo.23448946](https://doi.org/10.5281/zenodo.23448946)
- [infinite-becoming](https://github.com/sparkainlp-x/infinite-becoming): browser-playable synthetic ecosystem game on a reaction–diffusion substrate; uncalibrated; its frozen persistence regression is disclosed (1 of 5 seeds); [play online](https://sparkainlp-x.github.io/infinite-becoming/). [DOI 10.5281/zenodo.23423943](https://doi.org/10.5281/zenodo.23423943)
- [world-holobridge](https://github.com/sparkainlp-x/world-holobridge): standard-library Python + SQLite reference prototype of a governance workflow for community-led cultural and spatial-media projects, with a bilingual browser plan generator; not legal advice; no community endorsement claimed (MIT OR Apache-2.0); [plan generator](https://sparkainlp-x.github.io/world-holobridge/). [DOI 10.5281/zenodo.23423941](https://doi.org/10.5281/zenodo.23423941)
- [spark-evidence-lab](https://github.com/sparkainlp-x/spark-evidence-lab): rerunnable experiment cards that put my methods next to simple baselines, including where the baseline wins; every number copied from a committed source file; [live page](https://sparkainlp-x.github.io/spark-evidence-lab/). [DOI 10.5281/zenodo.23403169](https://doi.org/10.5281/zenodo.23403169)
- [digital-to-wave-2-thz-validity](https://github.com/sparkainlp-x/digital-to-wave-2-thz-validity): engineering-validity study of the THz equations in the *Digital to Wave* Part II preprint (equation inventory, dimensional checks, protocol-locked synthetic channel benchmark); SYNTHETIC; no physical, biological or safety claim. [DOI 10.5281/zenodo.23375690](https://doi.org/10.5281/zenodo.23375690)
- [orbit-wave-oes-lab](https://github.com/sparkainlp-x/orbit-wave-oes-lab): software-only path from a stylized orbit timeline to a synthetic signed-wave payload, fixed-threshold readout, optional OES replay and evidence passport, plus offline binaural capture analysis; SYNTHETIC; orbit, spacecraft, quantum and acoustic hardware UNRUN. [DOI 10.5281/zenodo.23372536](https://doi.org/10.5281/zenodo.23372536)
- [spark-membrane](https://github.com/sparkainlp-x/spark-membrane): fail-closed console that audits SYNTHETIC 32-channel frames against the OES repositories, pinned by commit SHA, with a hash-chained run trail, evidence passport and claims gate; thresholds uncalibrated; [demo page](https://sparkainlp-x.github.io/spark-membrane/). [DOI 10.5281/zenodo.23175490](https://doi.org/10.5281/zenodo.23175490)
- [oes-telemetry-bench](https://github.com/sparkainlp-x/oes-telemetry-bench): offline replay bench for synchronized 32-channel OES32 telemetry frames, with a strict input contract and frozen thresholds; synthetic demo. [DOI 10.5281/zenodo.23175492](https://doi.org/10.5281/zenodo.23175492)
- [residual-gradient-workbench](https://github.com/sparkainlp-x/residual-gradient-workbench): browser workbench that keeps an OES-32 residual replay and a classical thermoelectric generator model in separate lanes; [demo page](https://sparkainlp-x.github.io/residual-gradient-workbench/). [DOI 10.5281/zenodo.23187280](https://doi.org/10.5281/zenodo.23187280)
- [thermoelectric-ledger](https://github.com/sparkainlp-x/thermoelectric-ledger): signed heat-flow accounting that withholds exergy and efficiency figures unless the uncertainty bounds support them; 104 contract tests in CI (MIT). [DOI 10.5281/zenodo.23241554](https://doi.org/10.5281/zenodo.23241554)
- [qec-scaling-bench](https://github.com/sparkainlp-x/qec-scaling-bench): classical toy simulation of surface- and repetition-code memory scaling with Stim and PyMatching; seeded and reproducible, no hardware results. [DOI 10.5281/zenodo.23241631](https://doi.org/10.5281/zenodo.23241631)
- [flip-observer-1024](https://github.com/sparkainlp-x/flip-observer-1024): calibration prototype for a classical weighted readout under a hidden channel-order reversal (512 inputs, two noisy banks); SYNTHETIC; [demo page](https://sparkainlp-x.github.io/flip-observer-1024/). [DOI 10.5281/zenodo.23173449](https://doi.org/10.5281/zenodo.23173449)
- [oes-quantum-binaural-lab](https://github.com/sparkainlp-x/oes-quantum-binaural-lab): classical toy simulation with three separate lanes (Bell-correlation Monte Carlo, scalar metrics ledger, digital stereo loopback); SYNTHETIC. [DOI 10.5281/zenodo.23175494](https://doi.org/10.5281/zenodo.23175494)
- [signal-loom](https://github.com/sparkainlp-x/signal-loom): offline performance-art prototype in which synthetic signal streams drive an interactive visual score (MIT); [demo page](https://sparkainlp-x.github.io/signal-loom/). [DOI 10.5281/zenodo.23173453](https://doi.org/10.5281/zenodo.23173453)

## Full project index

This index links project names to their canonical public repositories. A **direct match** identifies the corresponding public project; it is not a claim of scientific validation. Related projects are separate implementations or tools, and their individual READMEs define their scope and evidence.

**Repository count, verified fresh:** 114 public repositories on the sparkainlp-x account (live account check, 2026-10-31; 96 before the October 31 launch, plus the 18 launch packages pushed that day). **Zenodo DOI count, snapshot as previously stated:** 64 of the 75 public repositories had Zenodo DOIs (count as of 2026-10-24); that DOI count was not re-verified against the 114-repo total for this refresh — use each repository's README for its citation and DOI details. Records are being added to the [Spark AI NLP: Research Software](https://zenodo.org/communities/spark-ai-nlp/) Zenodo community.

**Pending index correction:** [holographic-thoughts](https://github.com/sparkainlp-x/holographic-thoughts) is listed here as **Five** interactive toy views of classical holographic-membrane models, with a Python reference model for each ([live page](https://sparkainlp-x.github.io/holographic-thoughts/)). The shared link serves eight views (extra views Brain, Stars, Fringe), but the 8-view source was not found in the repository (main branch and the one other branch checked still describe five views), so the count is deliberately left at five until Jean supplies the 8-view source. Changing the count alone would be a false claim.

### October 31, 2026 launch: refusal gates, membranes, and wormhole

Eighteen packages pushed to main on 2026-10-31, all AGPL-3.0-only, all synthetic classical toys unless stated otherwise. No tags or Zenodo DOIs yet, and repository descriptions are still blank — both are follow-up steps, not claims made here.

| Repository | What it is |
|---|---|
| [refusal-gate-harness](https://github.com/sparkainlp-x/refusal-gate-harness) | Unified refusal-gate harness: the same calibration probe sets run through every Youden-gate implementation in the public repos. |
| [shared-gate-recall](https://github.com/sparkainlp-x/shared-gate-recall) | Canonical Youden refusal gate + overlap recall module extracted from the duplicated gate/recall logic. |
| [lattice-crystallization](https://github.com/sparkainlp-x/lattice-crystallization) | Pattern-specific lateral score on streaming-PCA (crystallized) patterns, 13x12 grid, held-out frozen gate. |
| [adr001-arena-gate](https://github.com/sparkainlp-x/adr001-arena-gate) | ADR-001 max-abs residual swapped into the membrane arena's guard; delta exactly zero across 160 runs. |
| [brain-heart-propulsion](https://github.com/sparkainlp-x/brain-heart-propulsion) | Synthetic linked toy: a brain membrane decides, a heart clock paces, a propulsion ring moves; refused probes do not move. |
| [microtubule-crystallize](https://github.com/sparkainlp-x/microtubule-crystallize) | Falsifiable classical toy for crystallizing microtubules, 13x12 lattice with a seam; lead with the Exp4 NEGATIVE. |
| [refusing-committee](https://github.com/sparkainlp-x/refusing-committee) | Heterogeneous committee of membranes at different resolutions, each with a Youden gate; lead with the NEGATIVE. |
| [membrane-vs-hopfield](https://github.com/sparkainlp-x/membrane-vs-hopfield) | Outer-product membrane recall vs Hopfield and attention baselines, including correlated-pattern failures. |
| [membrane-skeleton](https://github.com/sparkainlp-x/membrane-skeleton) | Membrane toy on a 31-bone-node skeleton graph; synthetic only, not anatomy or medicine. |
| [membrane-muscle](https://github.com/sparkainlp-x/membrane-muscle) | Membrane toy on a 24-muscle-group-node graph; synthetic only, not physiology or medicine. |
| [holo-heart-neurons](https://github.com/sparkainlp-x/holo-heart-neurons) | 64 seeded neurons on a heart-shaped geometry, pacemaker and Dijkstra beat propagation; synthetic only, not a heart or device. |
| [bentov-kuramoto](https://github.com/sparkainlp-x/bentov-kuramoto) | Kuramoto ring and chain toys vs Bentov's 7 Hz framing, tick-time predictions and lags between rings. Version v0.2.0. |
| [hologram-compute](https://github.com/sparkainlp-x/hologram-compute) | Holographic memory as infrastructure: recall is the matrix-vector multiply Y = WX in one pass. |
| [image-hologram](https://github.com/sparkainlp-x/image-hologram) | Pictures stored as interference patterns in a complex outer-product memory, reconstructed from noisy cues. |
| [humanity-guard](https://github.com/sparkainlp-x/humanity-guard) | Human-gated defensive sensing, verification, and refusal, hash-chained ledger; only alert and decoy actions exist. |
| [arena-evidence-seal](https://github.com/sparkainlp-x/arena-evidence-seal) | Evidence-passport seal over a membrane-arena benchmark: deterministic manifest plus SHA-256 verification. |
| [bubble-arena-injection](https://github.com/sparkainlp-x/bubble-arena-injection) | Arena 3x3 with Crystallize injection under the bubble split; vendored engine unchanged inside, observer records REPORTED only. |
| [wormhole-yin-yang-matrix](https://github.com/sparkainlp-x/wormhole-yin-yang-matrix) | Yin and yang membranes linked by a wormhole in the 3x3 arena, validated crossings only. Version v0.3.0; bifurcation: order-flip confirmed, no sharp threshold. |

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

## Proposed pins (to be set manually)

GitHub profile pins are **not** set by a commit, a branch, or a pull request. They are set manually by the account owner in the GitHub profile UI (Customize your pins). The proposed pins, in order, all verified to exist on the live account, are:

1. spark-evidence-lab
2. oes-resilience
3. evidence-passport
4. membrane-crystallization
5. thought-input-game
6. oes32-hls

No pin is claimed as set by this change.
