# Issue

**Title:** Bump pyasn1 from 0.6.4 to 0.6.5

## Description

Bumps [pyasn1](https://github.com/pyasn1/pyasn1) from 0.6.4 to 0.6.5.
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pyasn1/pyasn1/releases">pyasn1's releases</a>.</em></p>
<blockquote>
<h2>Release 0.6.5</h2>
<h2>Revision 0.6.5, released 26-10-2026</h2>
<ul>
<li>GHSA-mm57-4v3p-rchx: Decoded binary REAL mantissas in linear time
instead of repeatedly shifting a growing integer and slicing the
remaining bytes (thanks for reporting, manus-use, manus-pi, ucsurf,
adriank31)</li>
<li>GHSA-2qm8-x737-gmw5: Reassembled constructed BIT STRING fragments
in linear time while preserving their decoded bit values, including
intermediate fragment padding (thanks for reporting, manus-use)</li>
<li>GHSA-9m75-vc3g-4x39: Reassembled constructed OCTET STRING and
character-string fragments and indefinite-length ANY content in
linear time. Nested constructed OCTET STRING fragments now contribute
their decoded octets (thanks for reporting, alimony, manus-pi, adriank31)</li>
<li>GHSA-fm9c-5rcf-2q5p: Bounded schemaless container type tracking
after two distinct tag sets to prevent quadratic CPU use from
colliding long tag IDs (thanks for reporting, droideck)</li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/pyasn1/pyasn1/blob/main/CHANGES.rst">pyasn1's changelog</a>.</em></p>
<blockquote>
<h2>Revision 0.6.5, released 26-10-2026</h2>
<ul>
<li>GHSA-mm57-4v3p-rchx: Decoded binary REAL mantissas in linear time
instead of repeatedly shifting a growing integer and slicing the
remaining bytes (thanks for reporting, manus-use, manus-pi, ucsurf,
adriank31)</li>
<li>GHSA-2qm8-x737-gmw5: Reassembled constructed BIT STRING fragments
in linear time while preserving their decoded bit values, including
intermediate fragment padding (thanks for reporting, manus-use)</li>
<li>GHSA-9m75-vc3g-4x39: Reassembled constructed OCTET STRING and
character-string fragments and indefinite-length ANY content in
linear time. Nested constructed OCTET STRING fragments now contribute
their decoded octets (thanks for reporting, alimony, manus-pi, adriank31)</li>
<li>GHSA-fm9c-5rcf-2q5p: Bounded schemaless container type tracking
after two distinct tag sets to prevent quadratic CPU use from
colliding long tag IDs (thanks for reporting, droideck)</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>5d16736</code></a> Prepare release 0.6.5</li>
<li><a href=""><code>a36e3a3</code></a> Fix quadratic CPU use in schemaless container decoding</li>
<li><a href=""><code>4ce0079</code></a> Remove quadratic constructed OCTET STRING and ANY reassembly</li>
<li><a href=""><code>73ba7b0</code></a> Remove quadratic constructed BIT STRING reassembly</li>
<li><a href=""><code>ce3ec33</code></a> Remove quadratic binary REAL mantissa decoding</li>
<li>See full diff in <a href="https://github.com/pyasn1/pyasn1/compare/v0.6.4...v0.6.5">compare view</a></li>
</ul>
</details>
<br />

[![Dependabot compatibility score](https://dependabot-badges.githubapp.com/badges/compatibility_score?dependency-name=pyasn1&package-manager=uv&previous-version=0.6.4&new-version=0.6.5)](https://docs.github.com/en/github/managing-security-vulnerabilities/about-dependabot-security-updates#about-compatibility-scores)

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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `839576593a8e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.