---
title: Vortex
slug: vortex
sku: FB-1005
family: mixing
status: released
summary: Orbital vortex mixer with preset speed aliases and flexible duty cycles.
lead_time_days: 7
params:
- name: shake_patterns
  type: List[List[int]]
  default:
  - - 1000
    - 5
  - - 2000
    - 3
  unit: rpm_seconds
  description: Speed/duration pairs for the two default patterns.
- name: duty_cycle
  type: Union[int, float]
  default: 0.5
  unit: fraction
  description: Motor duty cycle as a fraction or integer percent.
- name: speed_aliases
  type: set
  default:
  - gentle
  - standard
  - vigorous
  unit: names
  description: Accepted symbolic names for the speed dial.
---

## Overview

Vortex is an orbital mixer for single tubes and small racks. The
mechanism is a eccentric cam on a brushless motor, with a printed elastomer
cup that accepts both 1.5 mL tubes and 50 mL Falcon tubes.

The project is in the design phase. No design repository has been published
yet; the parameter block records the interface agreed with the bench planner
so protocol files can be authored ahead of the release.

The mixer is expected to cover 200-3000 rpm.
