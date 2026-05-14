# Applying MELA to an Autopilot System: A Safety-Verification Case Study

### MachinE Learning-enhanced passive Automata learning approach (MELA)

## Overview
The MELA approach is a method for learning state machine models for autopilot systems using time-series inputs and outputs. It leverages machine learning (ML) to abstract raw numeric sensor data into discrete intervals. These intervals correlate with the system's safety output regarding flight safety categories.

## Testbed
Our testbed uses an autopilot module for flight safety monitoring. The goal is to model the safety behaviour of this module at a system level. We study various flight scenarios representing normal and safety-critical conditions across two flight regimes: ascending and descending.


## Tools
The following tools and resources are used in our experiments:
- Python 3.9 - [More Info](https://www.python.org/)
- AALpy - [More Info](https://des-lab.github.io/AALpy/)
- NuSMV - [More Info](https://nusmv.fbk.eu/)
- scikit-learn - [More Info](https://scikit-learn.org/)
- pandas - [More Info](https://pandas.pydata.org/)
- matplotlib - [More Info](https://matplotlib.org/)
- pydot - [More Info](https://pypi.org/project/pydot/)


## Testbed Configuration
Our setup is configured as follows:
- The autopilot module monitors two sensor inputs: pitchwheel and throttle.
- Input signals are studied in three configurations: pitchwheel only, throttle only, and pitchwheel\_throttle (both combined).
- Two flight directions are considered: ascend and descend.
- The safety output emitted at each time step is one of: Nominal (normal operating range), Caution (approaching unsafe boundary), or Critical (unsafe condition).


## Content Description
In this repository, we publish our implementations and experimental data.

### Repository Structure
- `Code`: Contains the MELA and Baseline abstraction implementations, automata learning routines, decision-tree learning, evaluation scripts, and the NuSMV model-checking pipeline.
- `Data`: Includes input data, learning sets, and abstractions with labels for numeric sensor data and symbolic traces.
- `Evaluation`: Includes evaluation scripts and the test set used to answer RQ1.
- `Figures`: Contains learned model figures (DOT-rendered PDFs for MELA, Baseline, and PTA models) and accuracy boxplot figures.
- `Results`: This directory is organised into several subfolders, each containing specific types of results:
  - `RQ1`: Includes the results of [test sequence](Evaluation/Autopilot) execution on the learned models addressing research question 1, related to accuracy and model comparison.
  - `RQ2`: Contains the outcomes of NuSMV model-checking for safety temporal properties. Verification summaries are available in [`Results/RQ2/Autopilot/summary/ag_not_target_gsm_pta_results.csv`](Results/RQ2/Autopilot/summary/ag_not_target_gsm_pta_results.csv).
  - `LearnedModel`: Contains [state machines](Results/LearnedModel/Autopilot) learned by MELA and the Baseline.

In the depicted state machines, system outputs are annotated on the states (Nominal, Caution, or Critical), and transitions are labelled by the abstracted sensor level ('L' for Low, 'M' for Medium, 'H' for High) for the pitchwheel and throttle signals.
