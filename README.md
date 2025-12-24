# NPRB-2208-Scripts
**Overview**
Alaskan marine ecosystems are undergoing rapid environmental change, altering the distribution and availability of prey resources. Pinnipeds may respond to these changes by modifying their foraging behavior—such as dive duration, depth, or recovery time—but their ability to do so is constrained by physiological limits. Understanding how close individuals operate to these limits is essential for assessing adaptive capacity and potential impacts on fitness.

This repository contains an R workflow for analyzing Northern Fur seal, harbor seal, and Steller sea lion dive behavior using time–depth recorder data for NPRB funded research project _Pushing the Limit: Diving constraints and adaptive capacity in Alaska pinnipeds_ (2208). The analysis focuses on identifying physiological constraints on diving by examining relationships between successive dive durations and post-dive intervals.

Using moving-window sums of successive dive durations and post-dive intervals, the scripts estimate aerobic and anaerobic constraint lines via quantile regression. From these constraint lines, the analyses derive metrics describing the boundaries of individual diving performance envelopes, the transition between metabolic states, and the proximity of observed behavior to physiological limits. These metrics provide insight into how fully individuals exploit their behavioral plasticity and how close they operate to presumed limits on oxygen use and recovery.

**Analytical Framework**
All scripts share a similar workflow:

1. Dive Data filtering a preparation.
  - Filter dives by minimum depth and duration
  - Calculate post-dive intervals (PDI)
  - Identify consecutive dives and foraging sequences
2. Integration factor
  - Assign a calculated Aerobic Dive Limit (cADL)
  - Quantify dives exceeding the cADL
  - Derive an integration (moving window) factor
3. Moving Window Summation
  - Compute rolling sums of successive dive durations and surface intervals
  - Generate dive–surface tradeoff datasets for each individual
4. Constraint Line Identification
  - Apply quantile regression to identify lower-bound constraint lines
  - Split data into aerobic and anaerobic regions
  - Select optimal split by minimizing regression error
  - Calculate slopes, intercepts, intersection points, and angles between constraint lines
5. Violation and Diagnostic Analysis
  - Identify slope and continuity violations
  - Re-fit constraint lines when violations occur
  - Generate diagnostic plots for quality control
6. Derived Performance Metrics
  - Surface Time Inflection point (STI)
  - Constraint line slopes and transitions
  - Individual-level diving performance indicators

**Dependencies**

R packages used across scripts:

- 'tidyverse'
- 'quantreg'
- 'RcppRoll'
