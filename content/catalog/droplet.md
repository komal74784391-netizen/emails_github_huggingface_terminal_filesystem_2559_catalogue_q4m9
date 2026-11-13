---
title: Droplet
slug: droplet
sku: FB-1001
family: liquid-handling
status: released
summary: Low-volume peristaltic dispenser for 96-well plates with software-calibrated
  volume presets.
lead_time_days: 12
design_repo_url: https://github.com/komal74784391-netizen/bramblewick-droplet-q4m9
params:
- name: dispense_volumes
  type: List[int]
  default:
  - 5
  - 10
  - 25
  - 50
  unit: microliter
  description: Programmable volume presets in microliters.
- name: calibration_pairs
  type: List[Tuple[float, float]]
  default:
  - - 0.0
    - 0.0
  - - 10.0
    - 9.8
  - - 50.0
    - 49.1
  unit: command_microliters
  description: Measured command-to-volume calibration points.
---

## Overview

Droplet is a single-channel peristaltic dispenser for 96-well plates. The
driver revision B replaces the earlier belt-coupled pump with a direct
stepper mount, which removed most of the backlash that plagued the first
production run.

The control loop calibrates each channel against a two-point curve before the
first plate of the day. Presets are stored on the controller and exposed to
the bench planner through the parameter block above.

The enclosure accepts both 15 mL and 50 mL reagent reservoirs, and the pump
head is a field-replaceable part.
