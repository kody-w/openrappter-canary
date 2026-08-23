# OpenRappter canary ring

Canary follows an alpha only after a **successful real smoke test or limited
rollout** of the same source and bytes. This repository is a maintained pointer,
not a code copy.

The current [manifest](.ring/manifest.json) is `disabled`: the source archive is
real and checksummed, but there is no smoke/rollout receipt or installable
canary artifact. `--ring canary` must fail closed.

Train: `nightly -> alpha -> canary -> beta -> stable`.

Validate with `node scripts/validate-manifest.mjs .ring/manifest.json canary`.
