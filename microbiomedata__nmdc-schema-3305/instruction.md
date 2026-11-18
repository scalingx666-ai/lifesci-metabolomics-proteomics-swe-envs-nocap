# Issue

**Title:** Bump httplib2 from 0.31.2 to 0.32.0

## Description

Bumps [httplib2](https://github.com/httplib2/httplib2) from 0.31.2 to 0.32.0.
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/httplib2/httplib2/blob/master/CHANGELOG">httplib2's changelog</a>.</em></p>
<blockquote>
<p>0.32.0</p>
<p>Python support 3.8+ only</p>
<p>decompression limited by size and ratio</p>
<p>decoder foundation to support more compression algorithms</p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>ba9bf50</code></a> v0.32.0 release</li>
<li><a href=""><code>87581ad</code></a> decompression limited by size and ratio; require python 3.8+</li>
<li>See full diff in <a href="https://github.com/httplib2/httplib2/compare/v0.31.2...v0.32.0">compare view</a></li>
</ul>
</details>
<br />

[![Dependabot compatibility score](https://dependabot-badges.githubapp.com/badges/compatibility_score?dependency-name=httplib2&package-manager=pip&previous-version=0.31.2&new-version=0.32.0)](https://docs.github.com/en/github/managing-security-vulnerabilities/about-dependabot-security-updates#about-compatibility-scores)

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
You can disable automated security fix PRs for this repo from the [Security Alerts page](https://github.com/microbiomedata/nmdc-schema/network/alerts).

</details>

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c907fb57bc6e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.