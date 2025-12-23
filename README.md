# NPRB-2208-Scripts
This repository contains an R workflow for analyzing Northern Fur seal, harbor seal, and Steller sea lion dive behavior using time–depth recorder data for NPRB funded research project _Pushing the Limit: Diving constraints and adaptive capacity in Alaska pinnipeds_ (2208). The analysis focuses on identifying physiological constraints on diving by examining relationships between successive dive durations and post-dive intervals.

**Overview**

The script processes individual seal dive records to:

1. Filter biologically relevant dives.
2. Calculate metrics related to dives beyond the calculated aerobic dive limit (cADL).
3. Apply moving-window summations of dive duration and post-dive interval.
4. Identify constraint lines using quantile regression.
5. Evaluate slope and continuity violations in constraint relationships.
6. Plot resulting moving-sum scatter plots

The outputs are used to infer transitions between aerobic and anaerobic diving behavior and to derive summary metrics.
