---
title: Brooder
slug: brooder
sku: FB-1004
family: incubation
status: released
summary: Bench incubator with programmable temperature cycles and humidity bands.
lead_time_days: 21
params:
- name: temp_cycle
  type: List[Tuple[float, int]]
  default:
  - - 37.0
    - 3600
  - - 42.0
    - 900
  unit: celsius_seconds
  description: Temperature setpoints and hold durations.
- name: humidity_bands
  type: List[List[int]]
  default:
  - - 40
    - 55
  - - 55
    - 70
  unit: percent
  description: Allowed humidity bands for each incubation phase.
---

## Overview

Brooder is a bench-scale incubator for agar plates and small culture
flasks. The chamber is heated with a printed heater sandwich and controlled by
a PI loop on a RP2040.

The first pilot batch is still being validated, so the hardware package has
not been published. The parameter block above is the interface the bench
planner will use once the device ships.

The chamber accepts up to twelve 90 mm plates.
