# oidc-probe

A throwaway probe of GitHub Actions behaviour for Topout's CI integration. It isn't a product, and
nothing should depend on it.

`.github/workflows/oidc-probe.yml` is a reusable workflow. Called from another repo, it records the
OIDC token's claim names and non-secret values (IDs, refs, SHAs and times), the calling context, and
whether a Node 24 and pnpm toolchain and an artifact between two jobs work, in the run summary and the
job log. It never prints, stores or uploads a token.

The other workflows are its callers. They are skipped in this repo and run in repos made from it as a
template.
