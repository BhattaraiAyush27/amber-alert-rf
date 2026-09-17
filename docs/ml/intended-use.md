# ML Intended Use Contract

## Purpose

The ML subsystem provides advisory decision support based on structured facts known at a defined point in the Case lifecycle.

## V1 research task

The initial research task is a missing-person case classification suggestion, contingent on a defensible source ontology and labels. The final target is not frozen until the dataset audit is complete.

Potential output classes may include categories such as endangered missing, runaway, family abduction, non-family abduction, lost/injured, or uncertain, but source-specific labels must not be silently treated as universal ground truth.

## Prohibited uses

ML may not:

- approve or publish an Alert;
- satisfy a Case verification requirement;
- override a jurisdiction/policy rule;
- automatically notify the public;
- automatically accuse or identify a suspect;
- convert model probability into a claim of factual certainty;
- block Case creation when the ML subsystem is unavailable.

## Production requirements

Every assessment records:

- assessment ULID;
- Case ULID;
- model/version;
- feature schema version;
- input hash;
- predicted class/probabilities as applicable;
- requested/completed timestamps;
- failure status without exposing sensitive internals.

## Evaluation principles

- compare against Dummy, logistic-regression and simple-tree baselines;
- use held-out data and prevent leakage;
- report per-class precision, recall, F1 and confusion matrix;
- investigate class imbalance and temporal/source drift;
- evaluate probability calibration if probabilities are shown to users;
- document known limitations and population/source bias;
- run initial production models in shadow mode.
