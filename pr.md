# docs(quickstarts): add PHP quickstarter and improve C++ quickstarter (fixes #3521)

## What has changed?

This PR adds a focused quick-starter for the PHP + PostgreSQL example and improves the existing C++ + MongoDB quickstart so both match the level of other sample quickstarts (e.g., PetClinic). Changes include clear prerequisites, exact endpoints, Docker/compose/service notes, Keploy record/replay commands, project structure, troubleshooting, and a quick commands cheat-sheet.

This PR Resolves #3521

## Type of change

Please delete options that are not relevant.

- [ ] Bug fix (non-breaking change which fixes an issue).
- [ ] New feature (non-breaking change which adds functionality).
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected).
- [x] Documentation update (if none of the other choices apply).

## How Has This Been Tested?

I verified the quickstart content against the upstream example README files for both repos (C++ and PHP) and ensured the endpoints and Keploy command flags match those READMEs.

To validate the docs render locally and to produce screenshots for the PR:
1. From the repo root:

```bash
npm install
npm run build
npm run serve
```
2. Open the built site (usually at http://localhost:3000) and navigate to the versioned quickstart pages:
   - `versioned_docs/version-4.0.0/quickstart/cpp-mongodb-quickstart.md`
   - `versioned_docs/version-4.0.0/quickstart/php-postgressql-quickstart.md`
3. Capture screenshots of the `npm run build` and `npm run serve` outputs and the rendered pages and attach them to this PR.

To validate the quickstart steps themselves (optional):
- Clone the referenced example repos and run:
  - `docker network create keploy-network || true`
  - `docker compose up --build`
  - Exercise the endpoints (curl examples in the docs)
  - Run Keploy record and Keploy test in a Linux environment (Codespaces recommended) to confirm recording and replay.

## Files changed

- `versioned_docs/version-4.0.0/quickstart/cpp-mongodb-quickstart.md` — cleaned and expanded C++ quickstart with prerequisites, endpoints (GET /health, POST /items, GET /items), Docker/Keploy notes, project structure, troubleshooting, and cheat-sheet.  
- `versioned_docs/version-4.0.0/quickstart/php-postgressql-quickstart.md` — new quick-starter for PHP + PostgreSQL example repo (https://github.com/mishraa-G/keploy-php-postgres-quickstart): clone → docker → test → keploy record/replay, project structure, DB init note, and cheat-sheet.

## Checklist:

- [x] My code follows the style guidelines of this project.
- [x] I have performed a self-review of my own code.

<!--- Thanks for opening this pull request! If the tests fail, please feel free to reach out to us by leaving a comment down below and we will be happy to take a look --->
