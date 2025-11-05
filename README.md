# Secure Claimable Dependency Demo 2

This repo intentionally **references** the scoped package `@example-business/utils`, but it is **secured** because the project uses a private registry for that scope.

Key points:

- `.npmrc` configures the `@example-business` scope to `https://npm.example-business.com/`
- CI (`.github/workflows/ci.yml`) sets registry-url to the private host and uses `NPM_TOKEN` secret
- The private registry will serve `@example-business/*` packages; thus the package is NOT claimable on the public npm registry

This demonstrates a secure setup where scoped/internal packages are protected from public namespace hijacking.
