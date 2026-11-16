# Issue

**Title:** Bump pre-commit from 4.6.2 to 4.7.0

## Description

Bumps [pre-commit](https://github.com/pre-commit/pre-commit) from 4.6.2 to 4.7.0.
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pre-commit/pre-commit/releases">pre-commit's releases</a>.</em></p>
<blockquote>
<h2>pre-commit v4.7.0</h2>
<h3>Fixes</h3>
<ul>
<li>Fix <code>language: node</code> hooks during commit with <code>-a</code> or inside a submodule.
<ul>
<li>Regressed in 4.6.1.</li>
<li><a href="">#3773</a> issue by <a href="https://github.com/cbirkhold"><code>@​cbirkhold</code></a>.</li>
<li><a href="">#3774</a> PR by <a href="https://github.com/cbirkhold"><code>@​cbirkhold</code></a>.</li>
</ul>
</li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/pre-commit/pre-commit/blob/main/CHANGELOG.md">pre-commit's changelog</a>.</em></p>
<blockquote>
<h1>4.7.0 - 2026-10-12</h1>
<h3>Fixes</h3>
<ul>
<li>Fix <code>language: node</code> hooks during commit with <code>-a</code> or inside a submodule.
<ul>
<li>Regressed in 4.6.1.</li>
<li><a href="">#3773</a> issue by <a href="https://github.com/cbirkhold"><code>@​cbirkhold</code></a>.</li>
<li><a href="">#3774</a> PR by <a href="https://github.com/cbirkhold"><code>@​cbirkhold</code></a>.</li>
</ul>
</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>65bb884</code></a> v4.7.0</li>
<li><a href=""><code>73926c1</code></a> Merge pull request <a href="">#3774</a> from cbirkhold/node-no-git-env-npm-install</li>
<li><a href=""><code>860d07d</code></a> don't leak GIT_* env into <code>npm install</code> for <code>language: node</code></li>
<li><a href=""><code>9ad8a0a</code></a> Merge pull request <a href="">#3775</a> from pre-commit/contextlib-chdir</li>
<li><a href=""><code>9905e88</code></a> use contextlib.chdir</li>
<li><a href=""><code>59cb792</code></a> Merge pull request <a href="">#3771</a> from pre-commit/all-repos_autofix_py311-plus</li>
<li><a href=""><code>2be1701</code></a> remove triple-nested withs for 3.14 coverage</li>
<li><a href=""><code>4c8d22a</code></a> py311+</li>
<li><a href=""><code>c429238</code></a> Merge pull request <a href="">#3770</a> from pre-commit/pre-commit-ci-update-config</li>
<li><a href=""><code>f49e251</code></a> [pre-commit.ci] pre-commit autoupdate</li>
<li>Additional commits viewable in <a href="https://github.com/pre-commit/pre-commit/compare/v4.6.2...v4.7.0">compare view</a></li>
</ul>
</details>
<br />

[![Dependabot compatibility score](https://dependabot-badges.githubapp.com/badges/compatibility_score?dependency-name=pre-commit&package-manager=uv&previous-version=4.6.2&new-version=4.7.0)](https://docs.github.com/en/github/managing-security-vulnerabilities/about-dependabot-security-updates#about-compatibility-scores)

Dependabot will resolve any conflicts with this PR as long as you don't alter it yourself. You can also trigger a rebase manually by commenting `@dependabot rebase`.

[//]: # (dependabot-automerge-start)
[//]: # (dependabot-automerge-end)

---

<details>
<summary>Dependabot commands and options</summary>
<br />

You can trigger Dependabot actions by commenting on this PR:
- `@dependabot rebase` will rebase this PR
- `@dependabot recreate` will recreate this PR, overwriting any edits that have been made to it
- `@dependabot show <dependency name> ignore conditions` will show all of the ignore conditions of the specified dependency
- `@dependabot ignore this major version` will close this PR and stop Dependabot creating any more for this major version (unless you reopen the PR or upgrade to it yourself)
- `@dependabot ignore this minor version` will close this PR and stop Dependabot creating any more for this minor version (unless you reopen the PR or upgrade to it yourself)
- `@dependabot ignore this dependency` will close this PR and stop Dependabot creating any more for this dependency (unless you reopen the PR or upgrade to it yourself)

</details>

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f9cc919a5c5e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.