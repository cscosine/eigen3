# eigen3: the cscosine fork of Eigen

Eigen, as built and released by [third_party_base_libs](https://github.com/cscosine/third_party_base_libs) for the
cscosine projects: the upstream release plus a few commits of ours on top. This folder is ours; the rest of the
repository is upstream.

| | |
|---|---|
| Upstream | <https://gitlab.com/libeigen/eigen> (GitLab: GitHub does not show it as a fork) |
| Base | upstream tag `5.0.1` (also in this repository) |
| Our changes | `git log 5.0.1..dev` |
| Our releases | tags `v<upstream>-cs.<n>`, see [CHANGELOG.md](CHANGELOG.md) |
| License | upstream's (`COPYING.*`, MPL2 for most of Eigen) |

## Our changes

| Commit | What | Why |
|---|---|---|
| `e70fe6e` csCMake presets | `CMakePresets.json`, `csCMakeProjectSetup.json` (csCMake presets, level 2): tests, BLAS, LAPACK, demos, docs off | Built with the csCMake presets on every platform of the matrix; the package is the headers, `Eigen3Config.cmake`, `eigen3.pc` |
| `73a4457` .gitignore | Back to upstream | A dead entry of an old tool |
| this folder | `cscosine/README.md`, `CHANGELOG.md` | Where the fork comes from, what we change, why |

Header-only: no macOS deployment target to record.

## Syncing with a new upstream release

The procedure is the same for every fork (organisation rules: forks, `-cs.N` tags): fetch the new upstream tag
(`git fetch https://gitlab.com/libeigen/eigen.git refs/tags/<new>:refs/tags/<new>`), rebase our commits on it
(`git rebase --onto <new> <old> dev`), drop those upstream has absorbed, build through third_party_base_libs, then tag
`v<new>-cs.1`.
