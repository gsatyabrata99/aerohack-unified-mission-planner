# AeroHack Unified Mission Planner

A single, unified mission planning + simulation framework that solves two linked tasks using the same planning concept (actions + constraints + objective + solver):

- **Aircraft (UAV / fixed-wing)**: waypoint mission planning under wind uncertainty, energy/endurance limits, turn constraints, and geofenced no-fly polygons.
- **Spacecraft (CubeSat LEO ops)**: 7-day observation + downlink scheduling under visibility/contact windows, slew feasibility proxy constraints, and battery/power proxy constraints.

## Key idea: Unified Architecture
Both domains use the same planning engine:
- common Plan/Action representation
- common Constraint interface
- common Objective interface
- one solver loop (local search + repair)

## Optional AI acceleration
- **Surrogate model** predicts score/feasibility to filter weak candidates.
- **Move ranker** prioritizes high-quality candidate edits.
This reduces expensive simulator calls and enables more Monte-Carlo validation.

## Quickstart
```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
python run_all.py
