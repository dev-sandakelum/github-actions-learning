# Advanced Badge Submission - Hasitha Sandakelum

**Date:** April 2026
**GitHub Username:** @dev-sandakelum
**Branch:** working-advanced-hasitha
**Status:** Submitted for Review

---

## Tasks Completed

- [x] Task 8: Upload and Download Artifacts
- [x] Task 9: Conditional Execution
- [x] Task 10: Create a PR and Use Issue Templates

---

## Evidence

### Task 8: Artifacts
- Added artifact creation and upload steps to `build-test.yml`
- Artifact named `build-output` uploaded from Node 18.x job
- Added new `download-and-verify` job that depends on
  `build-and-test` and downloads the artifact
- Artifact content verified in job logs
- Artifact visible and downloadable from Actions UI

Screenshot 1 - Artifact uploaded in job logs:
<p align="center">
    <img src="img/01.png" />
</p>

Screenshot 2 - Artifact downloaded and verified:
<p align="center">
    <img src="img/02.png" />
</p>

### Task 9: Conditional Execution
- Created `.github/workflows/conditional.yml`
- Workflow triggers on push to both `main` and `develop` branches
- `Deploy to production` step runs only on `main` branch
- `Deploy to staging` step runs only on `develop` branch
- `Notify success` step uses `if: success()` condition
- `Notify failure` step uses `if: failure()` condition
- Tested on both branches and confirmed correct skipping behavior

Screenshot 1 - Main branch run (production step ran, staging skipped):
<p align="center">
    <img src="img/04.png" />
</p>

Screenshot 2 - Develop branch run (staging step ran, production skipped):
<p align="center">
    <img src="img/03.png" />
</p>



## Advanced Implementation Details

**Artifacts:**
- Artifact file: `output.txt`
- Artifact name: `build-output`
- Uploaded from: `build-and-test (18.x)` job
- Retention days: 5
- Download job: `download-and-verify`
- Job dependency: `needs: [build-and-test]`
- Download successful: ✅

**Conditions used:**
- `if: github.ref == 'refs/heads/main'` → production deploy
- `if: github.ref == 'refs/heads/develop'` → staging deploy
- `if: success()` → notify success step
- `if: failure()` → notify failure step
- Branch-based conditions verified: ✅
- Status-based conditions verified: ✅

**Community Participation:**
- Issue created using Feature Request template: ✅
- PR created using PR template: ✅

---

## Notes
All advanced tasks completed successfully.
Conditional execution tested and verified on
both main and develop branches with correct
step skipping behavior confirmed in logs.

---
Submitted & ready for review! ✅