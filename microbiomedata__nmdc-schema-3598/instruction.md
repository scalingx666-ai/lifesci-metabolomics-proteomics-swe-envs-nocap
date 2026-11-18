# Issue

**Title:** Bump oauthlib from 4.0.0 to 4.0.1

## Description

Bumps [oauthlib](https://github.com/oauthlib/oauthlib) from 4.0.0 to 4.0.1.
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/oauthlib/oauthlib/releases">oauthlib's releases</a>.</em></p>
<blockquote>
<h2>4.0.1</h2>
<h2>Security</h2>
<ul>
<li><strong>CVE-2026-49272</strong> / GHSA-3jp2-3mrg-2vxc: The device code flow token endpoint did not validate the <code>device_code</code> parameter. A request with a known <code>client_id</code> and a bogus <code>device_code</code> could obtain a bearer token. <code>DeviceCodeGrant.validate_token_request</code> now calls <code>DeviceCodeGrant.validate_device_code()</code>, which rejects missing or unknown device codes (<code>invalid_request</code> / <code>invalid_grant</code>) and delegates the code's authorization status to the new <code>RequestValidator.validate_device_code()</code> hook, per RFC 8628 Section 3.5. (cherry-picked from <a href="">#954</a>)</li>
</ul>
<h2>Upgrade note for device flow integrators</h2>
<p>Custom <code>RequestValidator</code> implementations using the device flow must now implement <code>validate_device_code(client_id, code, request)</code>. Return one of the <code>DeviceCodeGrant.DEVICE_CODE_*</code> statuses for known codes, or <code>None</code> for an unknown code. When returning <code>AUTHORIZED</code>, the validator must also populate <code>request.user</code> and <code>request.scopes</code> from the stored authorization.</p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/oauthlib/oauthlib/blob/v4.0.1/CHANGELOG.rst">oauthlib's changelog</a>.</em></p>
<blockquote>
<h2>4.0.1 (2026-11-04):</h2>
<p>OAuth2.0 Provider (Security):</p>
<ul>
<li>
<p><strong>Security</strong>: CVE-2026-49272 / GHSA-3jp2-3mrg-2vxc: The device code flow
token endpoint did not validate the <code>device_code</code> parameter. A request
with a known <code>client_id</code> and a bogus <code>device_code</code> could obtain a
bearer token. <code>DeviceCodeGrant.validate_token_request</code> now calls a new
<code>DeviceCodeGrant.validate_device_code()</code> which rejects missing or
unknown device codes (<code>400 invalid_request</code> / <code>400 invalid_grant</code>)
and delegates the code's authorization status to a new required
<code>RequestValidator.validate_device_code()</code> hook, per RFC 8628
Section 3.5. (cherry-picked from <a href="">#954</a>, merged as 1c91d64)</p>
<p><strong>Upgrade note for device flow integrators</strong>: custom
<code>RequestValidator</code> implementations using the device flow must now
implement <code>validate_device_code(client_id, code, request)</code>. Return one
of the <code>DeviceCodeGrant.DEVICE_CODE_*</code> statuses (<code>AUTHORIZED</code>,
<code>PENDING</code>, <code>SLOW_DOWN</code> or <code>EXPIRED</code>) for known codes, or <code>None</code>
for an unknown code. When returning <code>AUTHORIZED</code>, the validator must
also populate <code>request.user</code> and <code>request.scopes</code> from the stored
authorization.</p>
</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>6e3aa05</code></a> Release 4.0.1: fix CVE-2026-49272 (device_code validation in device flow)</li>
<li><a href=""><code>77a5f1c</code></a> Merge pull request <a href="">#954</a> from hekhuisk/improve-device-workflow</li>
<li>See full diff in <a href="https://github.com/oauthlib/oauthlib/compare/v4.0.0...v4.0.1">compare view</a></li>
</ul>
</details>
<br />

[![Dependabot compatibility score](https://dependabot-badges.githubapp.com/badges/compatibility_score?dependency-name=oauthlib&package-manager=uv&previous-version=4.0.0&new-version=4.0.1)](https://docs.github.com/en/github/managing-security-vulnerabilities/about-dependabot-security-updates#about-compatibility-scores)

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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `270aefeda914`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.