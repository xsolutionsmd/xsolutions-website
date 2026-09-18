# Website workflow

Read README.md and docs/VALIDATION.md before changes. The public website lives in xsolutions-site/. Use dev for development; main is the explicit release gate and deploys to Oracle automatically. Never merge dev into main without release authorization. Initial workflow release tests were completed on September 9, 2026; their authorization is not standing permission for future releases.

Keep credentials, machine-specific SSH paths, business research and private files out of this public repository and image. Use the explicit Docker context allowlist. Preserve existing Caddy certificate volumes and unrelated Docker resources. Production uses ARM64; release images support ARM64 and AMD64.

Run container checks for website/container changes. Server deployment changes require an integration check. Record actual tested revisions. Shell launchers and website.ps1 should offer equivalent local behavior.

## Source context

For dev/main source discovery, read docs/GRAFT.md and run scripts/graft.py with an explicit --ref matching this checkout. Production context requires clean main. Use the whole-repository graph plus bounded search/read for Docker, CI, deployment scripts, configuration and docs. Unsupported formats use text retrieval, not native graph edges. Explicit --feature enables attached development feature branches. Keep private/runtime/dependency files excluded; inspect status coverage and use rg/direct reads for gaps. Graphs are local hints; actual source and tests remain authoritative. Never run upstream init or install global hooks as part of this setup.

## Runtime verification

For browser behavior changes, use [Reticle](docs/RETICLE.md) when useful: start the intended local app/preview, select its exact URL session, perform a focused interaction and assert the resulting state/response. Treat unknown or partial observations honestly. Keep instrumentation local, preserve dev/main release gates, and use source/tests plus visual review for the gaps. This does not require Reticle for documentation-only edits.
