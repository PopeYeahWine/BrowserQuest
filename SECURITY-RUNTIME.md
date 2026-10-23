# Node.js security and required legacy port

The historical package manifest requires Node.js 0.10.x and npm 1.2.x. These are not acceptable runtimes for a new deployment. The October 2026 Node.js remediation targets maintained patched releases, including Node.js 22.23.4 and 24.22.1.

Changing only `engines.node` would not establish application compatibility. The current manifest includes Socket.IO 1.x and open-ended Redis/bcrypt requirements, without a dependency lockfile. The server/client protocol, Redis API calls and native-module compatibility need a dedicated port and fixed dependency resolution.

Before reactivating this project:

1. Select a maintained patched Node branch and compatible package manager.
2. Port and pin the Redis, Socket.IO/client and native-module contracts; preserve game data and protocol semantics.
3. Commit the resulting dependency lock and actual runtime constraints.
4. Qualify the completed port before deployment, documenting any verification not performed.

No service for this project was identified on the VPS audited on 2026-10-23, and no mapped local checkout was found. This documentation update neither starts a server nor claims that existing source code is corrected or operational on modern Node.js. No test, build or deployment was performed in the current remediation.

Official Node security release: https://nodejs.org/en/blog/vulnerability/october-2026-security-releases
