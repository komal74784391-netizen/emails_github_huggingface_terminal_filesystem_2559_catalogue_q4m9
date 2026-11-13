---
title: Whirl
slug: whirl
sku: FB-1003
family: separation
status: released
summary: Compact microcentrifuge with programmable ramp profiles and rotor-aware limits.
lead_time_days: 9
design_repo_url: https://github.com/komal74784391-netizen/bramblewick-whirl-q4m9
params:
- name: ramp_profile
  type: List[Tuple[int, int]]
  default:
  - - 0
    - 300
  - - 10
    - 6000
  unit: seconds_rpm
  description: Time/rpm points for the soft-start ramp.
- name: rotor_limits
  type: Dict[str, int]
  default:
    micro: 12000
    tube: 4000
  unit: rpm
  description: Speed ceiling for each supported rotor.
---

## Overview

Whirl is a direct-drive microcentrifuge for 1.5 mL tubes and 8-strip
PCR plates. The rotor is machined from a single aluminium billet, and the
lid interlock is a magnetic reed switch rather than a mechanical latch.

Firmware refuses to spin past the configured rotor ceiling; the bench planner
reads those limits from the parameter block above so a protocol cannot be
scheduled onto the wrong rotor.

The released package contains the driver board, the rotor chamber model and
the ramp firmware.
