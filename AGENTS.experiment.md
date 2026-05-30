# AGENTS.experiment.md

This file applies to:

* Model Reproduction
* Training Experiments
* Benchmarking
* Ablation Studies
* Hyperparameter Search
* Scientific Research Projects

This file supplements `AGENTS.md`.

---

# Core Principle

Do not trade conclusion validity for execution convenience.

Formal conclusions should be:

* Explainable
* Traceable
* Reviewable
* Reproducible

When evidence is insufficient, configurations deviate, data boundaries are unclear, or experiment records are incomplete, results should not be presented as formal conclusions.

---

## 1. Preserve Experiment Meaning

Without explicit approval, do not change:

* Dataset
* Train / Validation / Test Split
* Metrics or Evaluation Protocol
* Loss or Optimization Objective
* Model Architecture
* Checkpoints or Pretrained Weights
* Training Budget
* Model Selection Rules
* Random Seeds

Any such change creates a different experiment and must be reported.

---

## 2. Reproduction Integrity

Do not describe the following as Faithful Reproduction:

* Simplified Versions
* Partial Implementations
* Toy Versions
* Debug Versions
* Smoke Tests
* Implementations using Mock or Dummy Data

Before reproducing a method, create an implementation mapping and identify:

* Implemented Parts
* Missing Parts
* Uncertain Parts
* Deviations from the paper or plan

Uncertainty must be labeled explicitly.

---

## 3. Decision Value

Every experiment should test a hypothesis or support a decision.

Before running an experiment, identify:

* The hypothesis
* The decision it informs
* The expected information gain
* Actions implied by possible outcomes

Avoid low-information experiments.

If repeated experiments do not change the decision, reconsider the direction.

---

## 4. Experiment Levels

Distinguish:

### Smoke Test

Verifies that code runs.

### Sanity Check

Verifies data flow, shapes, loss, gradients, and metrics.

### Formal Experiment

Supports conclusions, comparisons, reproduction claims, or project decisions.

Smoke Tests and Sanity Checks are not formal evidence.

---

## 5. Evaluation Integrity

Do not use Test Data for:

* Hyperparameter Tuning
* Early Stopping
* Checkpoint Selection
* Seed Selection
* Model Selection
* Preprocessing Statistics

Maintain clear Train / Validation / Test boundaries.

Any leakage weakens conclusion validity.

---

## 6. Experiment Asset Traceability

Experiment names, configs, logs, checkpoints, output directories, and result files should reflect experiment meaning.

Record:

* Code Version
* Configuration
* Data Version
* Split
* Seed
* Commands
* Logs
* Metrics
* Checkpoints
* Output Paths

Record sources of:

* Pretrained Models
* Checkpoints
* Caches
* Processed Datasets
* Third-Party Implementations

Do not overwrite formal experiment results unless explicitly requested.

Failed experiments should also be recorded.

---

## 7. Fail Visibly

Do not hide failures through:

* Mock Data
* Dummy Modules
* Silent Fallbacks
* Broad Exception Handling
* Hidden Random Initialization
* Skipped Samples
* Unexplained NaN Fixes

If a fallback is used, explain:

* What failed
* Why fallback is allowed
* How behavior changed
* Whether the result remains valid

Experimental failure is also information.

---

## 8. Bind Conclusions to Evidence

Do not simply claim:

* Reproduction Success
* Performance Improvement
* Model Effectiveness
* Similarity to Paper Results

State:

* Which experiment
* Which configuration
* Which dataset version
* Which seed
* Which metric
* Which baseline
* Whether it is a Formal Experiment
* Existing caveats or deviations

Do not confuse:

* Observation
* Measurement
* Inference
* Hypothesis
* Recommendation

If evidence is insufficient, say so explicitly.

---

## 9. Review Plan vs Actual

At task completion, report:

* Original Plan
* Actual Work Completed
* Deviations
* Evidence Obtained
* Remaining Uncertainty
* Whether the evidence supports the conclusion

Partial completion must not be reported as full completion.
