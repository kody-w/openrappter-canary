# OpenRappter canary ring

<!-- rapp1:network-header:start -->
[![RAPP/1](https://kody-w.github.io/rapp-hive-public/portfolio/badges/openrappter-canary.svg)](https://github.com/kody-w/rapp-hive-public/blob/main/portfolio/repos/openrappter-canary.md) · **New to RAPP?** [Start here: get your Brainstem →](https://github.com/kody-w/rapp-installer#start-here)
<!-- rapp1:network-header:end -->

Canary follows an alpha only after a **successful real smoke test or limited
rollout** of the same source and bytes. This repository is a maintained pointer,
not a code copy.

The current [manifest](.ring/manifest.json) is `disabled`: the source archive is
real and checksummed, but there is no smoke/rollout receipt or installable
canary artifact. `--ring canary` must fail closed.

Train: `nightly -> alpha -> canary -> beta -> stable`.

Validate with `node scripts/validate-manifest.mjs .ring/manifest.json canary`.

Distribution invariant: canary must descend from finalized nightly and alpha
receipts after rollout evidence, as step 3 of nightly → alpha → canary → beta.
No stable/tag/registry/release/installer path may bypass the machine gate.

Target `main` files are informational. Latest canary is named only by the
monotonic release-train authority head, which binds an immutable receipt and
exact target manifest commit.

Per-sequence acknowledgements are immutable under `.ring/applied/`; applied and
finalized cursors remain separate so canary N+1 cannot outrun finalization N.
