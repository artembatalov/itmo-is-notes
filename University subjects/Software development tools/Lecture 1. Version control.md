## Поколения version control
1. Локальное (RCS/SCCS),
2. Централизованное, клиент-серверное (CVS/SVN),
3. Распределенное (Git - от Линуса Торвальдса /Mercurial).
4. <развивается>

## Short introduction in Git
0. Don't forget to config:
```bash
git config --global user.email "example@mail.com"
git config --global user.name "Artem"
```
0. Start Git:
```bash
git init              # initialize a new repo
git clone <url>       # clone an existing repo
```
2. Adding files to Git (without that action Git won't work the file):
```bash
git add *
```
3. Commits (Never wright "ancd" or "Final commit"):
```bash
git commit -m "Write what was done!"
```
4. Want to develop new feature:
```bash
git branch feature-1
```
5. Switch to feature-1 branch:
```bash
git checkout feature-1
```
6. Added and committed new stuff in feature 1:
```bash
git add *
git commit -m "Feature-1 is developed!"
```
7. Merging:
```bash
git merge feature-1
```
## Gitflow

| Branch Type     | Purpose & Description                                                                                                                                 | Naming Convention                             | Branches From | Merges Into              |
| --------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------- | ------------- | ------------------------ |
| **`main`**      | **Production Ready Code.** Represents the official release history. Every commit on `main` is a tagable, production-ready release.                    | `main` or `master`                            | -             | -                        |
| **`develop`**   | **Integration Branch.** The main branch for integrating features. Contains the complete history of the project's "next release" development.          | `develop`                                     | `main`        | `main` & `release`       |
| **`feature/*`** | **New Feature Development.** Used to develop a new feature for an upcoming release. Isolated from other feature work.                                 | `feature/<name>` (e.g., `feature/user-login`) | `develop`     | `develop`                |
| **`release/*`** | **Release Preparation.** Used to prepare a new production release. Allows for final bug fixes, minor tweaks, and meta-data (version numbers) updates. | `release/<version>` (e.g., `release/1.3.0`)   | `develop`     | `develop` **and** `main` |
| **`hotfix/*`**  | **Critical Production Fix.** Used to quickly patch production releases. Avoids interrupting the `develop` branch, which may contain unstable code.    | `hotfix/<name>` (e.g.                         | `main`        | `develop` **and** `main` |
1. A `feature` branch is created from `develop`.
2. Work is completed on the `feature` branch.
3. The `feature` branch is merged back into `develop`.
4. When `develop` is stable for a release, a `release` branch is created from it.
5. Final testing and preparation happen on the `release` branch.
6. The `release` branch is merged into both `main` (and tagged for the release) and back into `develop`(to carry forward any fixes).
7. If a critical bug is found in `main` (production), a `hotfix` branch is created from `main`.
8. The fix is applied and the `hotfix` branch is merged into both `main` (and tagged) and `develop`
## Links
1. [Official Git site](https://git-scm.com)
