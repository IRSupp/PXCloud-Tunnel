# PXCloud-Tunnel

Private distribution repository for PXCloud Tunnel and the Rakhsh engine.

## Source protection

Proprietary source code is kept offline and is not uploaded to this repository. Only release documentation and approved compiled artifacts belong here. Third-party license notices and applicable corresponding-source obligations remain in force.

## Current baseline

Version: **1.6.0-rc.1** (release candidate, not yet Stable).

- Rakhsh defaults to a 100 Mbps send cap for new installations; existing configurations are preserved.
- Rakhsh participates in quality monitoring, tests and automatic failover alongside the other installed transports.
- Licenses bind the Iran/foreign server pair and host identity; subscription grace and online check interval are six hours.
- 73 local manager tests and 18 isolated licensing API tests passed. Packaging smoke test passed with the bundled Rakhsh engine.

No compiled release is published yet. The final Nuitka artifact must pass isolated Linux installation, live licensing and failover validation before promotion to Stable. Native compilation makes inspection harder but does not guarantee resistance to reverse engineering or root-level license bypass.

Known limits: single-flow upload throughput remains below direct-path capacity; one impaired rawTCP/Gaming UDP startup test timed out before a successful repeat, with root cause unconfirmed.
