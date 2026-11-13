---
title: Prism
slug: prism
sku: FB-1002
family: optics
status: released
summary: Absorbance plate reader with swappable LED cassettes and scripted exposure
  profiles.
lead_time_days: 18
params:
- name: wavelength_set
  type: List[int]
  default:
  - 405
  - 450
  - 630
  unit: nanometre
  description: LED cassettes installed in the reader at build time.
- name: gain_curve
  type: Callable[[float], float]
  default: linear
  unit: gain
  description: Photodiode gain response used when normalising readings.
- name: exposure_profile
  type: Dict[str, float]
  default:
    fast: 0.2
    standard: 0.8
  unit: seconds
  description: Named exposure times for fast and standard scans.
---

## Overview

Prism is a filter-free absorbance reader built around a TSL2591 light
sensor and three swappable LED cassettes. The reader head is deliberately
low-cost: the optical tunnel is printed, and the only machined parts are the
cassette detents.

Firmware exposes a simple serial protocol; the bench planner drives scans by
name using the exposure profile above. The gain curve can be replaced with a
calibrated polynomial when a lab needs tighter linearity.

The current release includes the reader board, the light tunnel model and the
serial driver.
