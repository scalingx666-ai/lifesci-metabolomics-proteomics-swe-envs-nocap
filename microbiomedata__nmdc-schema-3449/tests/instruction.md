# Issue

**Title:** Bump oauthlib from 3.3.1 to 4.0.0

## Description

Bumps [oauthlib](https://github.com/oauthlib/oauthlib) from 3.3.1 to 4.0.0.
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/oauthlib/oauthlib/releases">oauthlib's releases</a>.</em></p>
<blockquote>
<h2>4.0.0</h2>
<h2>Introduction</h2>
<p>The release 4.0.0 defines the foundation that enables AI contributions and will improve the maintenance of oauthlib by using AI agents, skills, code for both contributors and maintainers. It includes devcontainer, skills and cleanup of instructions.</p>
<h2>What's Changed</h2>
<p><strong>Important</strong>: this release contains 2 breaking changes. See CHANGELOG.rst for details:</p>
<ul>
<li>Removed JSONP support from token revocation endpoint (<a href="">#951</a>)</li>
<li>Client authentication validation reorganized across grants (<a href="">#919</a>, <a href="">#920</a>):
the <code>grant_type</code> parameter is now validated before client authentication.</li>
</ul>
<ul>
<li>Replace pyenv with uv in documentation and tooling by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#910</a></li>
<li>Improve github action to publish package by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#915</a></li>
<li>Add pre-commit to run linters, formatters, etc. on code changes by <a href="https://github.com/cclauss"><code>@​cclauss</code></a> in <a href="">oauthlib/oauthlib#918</a></li>
<li>Fix client authentication for DeviceCodeGrant when getting a token by <a href="https://github.com/hekhuisk"><code>@​hekhuisk</code></a> in <a href="">oauthlib/oauthlib#920</a></li>
<li>Add project URLs to this project's PyPI page by <a href="https://github.com/Flimm"><code>@​Flimm</code></a> in <a href="">oauthlib/oauthlib#921</a></li>
<li>Fix a typo in ServiceApplicationClient docstring. by <a href="https://github.com/rafalkrupinski"><code>@​rafalkrupinski</code></a> in <a href="">oauthlib/oauthlib#923</a></li>
<li>Correct grammar in function help by <a href="https://github.com/verhovsky"><code>@​verhovsky</code></a> in <a href="">oauthlib/oauthlib#924</a></li>
<li>Add Python 3.14 to the testing by <a href="https://github.com/cclauss"><code>@​cclauss</code></a> in <a href="">oauthlib/oauthlib#925</a></li>
<li>Initial python/uv/tox devcontainer by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#930</a></li>
<li>Fix ruff checks about unused variables by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#931</a></li>
<li>Drop EOL Python 3.8 from CI by <a href="https://github.com/auvipy"><code>@​auvipy</code></a> in <a href="">oauthlib/oauthlib#932</a></li>
<li>Set Open Collective username to 'oauthlib' by <a href="https://github.com/auvipy"><code>@​auvipy</code></a> in <a href="">oauthlib/oauthlib#933</a></li>
<li>pre-commit autoupdate 2026_02_21 by <a href="https://github.com/cclauss"><code>@​cclauss</code></a> in <a href="">oauthlib/oauthlib#934</a></li>
<li>Remove a trailing whitespace fo fix failing pre-commit by <a href="https://github.com/cclauss"><code>@​cclauss</code></a> in <a href="">oauthlib/oauthlib#935</a></li>
<li>Fix typos discovered by typos by <a href="https://github.com/cclauss"><code>@​cclauss</code></a> in <a href="">oauthlib/oauthlib#938</a></li>
<li>Add <code>resource</code> to Request._params by <a href="https://github.com/juannyG"><code>@​juannyG</code></a> in <a href="">oauthlib/oauthlib#942</a></li>
<li>Release 3.4.0: Add OAuthLib Maintainer agent by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#950</a></li>
<li>Remove JSONP support from token revocation by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#951</a></li>
<li>Improve PKCE code comparison by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#963</a></li>
<li>Release 4.0.0: bump and update changelog by <a href="https://github.com/JonathanHuot"><code>@​JonathanHuot</code></a> in <a href="">oauthlib/oauthlib#976</a></li>
</ul>
<h2>New Contributors</h2>
<ul>
<li><a href="https://github.com/hekhuisk"><code>@​hekhuisk</code></a> made their first contribution in <a href="">oauthlib/oauthlib#920</a></li>
<li><a href="https://github.com/Flimm"><code>@​Flimm</code></a> made their first contribution in <a href="">oauthlib/oauthlib#921</a></li>
<li><a href="https://github.com/verhovsky"><code>@​verhovsky</code></a> made their first contribution in <a href="">oauthlib/oauthlib#924</a></li>
<li><a href="https://github.com/juannyG"><code>@​juannyG</code></a> made their first contribution in <a href="">oauthlib/oauthlib#942</a></li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/oauthlib/oauthlib/compare/v3.3.1...v4.0.0">https://github.com/oauthlib/oauthlib/compare/v3.3.1...v4.0.0</a></p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/oauthlib/oauthlib/blob/master/CHANGELOG.rst">oauthlib's changelog</a>.</em></p>
<blockquote>
<h2>4.0.0 (2026-09-28):</h2>
<p>OAuth2.0 Provider:</p>
<ul>
<li><strong>Breaking</strong>: <a href="">#951</a>: Removed JSONP support from token revocation endpoint.
JSONP has been superseded by CORS for cross-origin requests.
The <code>enable_jsonp</code> parameter has been removed from <code>RevocationEndpoint</code>
and the <code>callback</code> parameter has been removed from
<code>prepare_token_revocation_request</code>.</li>
<li><strong>Breaking</strong>: <a href="">#919</a>, <a href="">#920</a>: Fixed <code>DeviceCodeGrant.validate_token_request</code>
trying to authenticate public clients.
Client authentication validation has been reorganized and is now shared
across <code>AuthorizationCodeGrant</code>, <code>DeviceCodeGrant</code>, <code>RefreshTokenGrant</code>
and <code>ResourceOwnerPasswordCredentialsGrant</code>: the <code>grant_type</code> parameter
is validated before client authentication, so requests missing
<code>grant_type</code> now return <code>400 invalid_request</code> instead of
<code>401 invalid_client</code>.</li>
<li><a href="">#963</a>: Improved PKCE code comparison</li>
</ul>
<p>Misc:</p>
<ul>
<li><a href="">#904</a>: Stop installing <code>examples</code> into <code>site-packages</code>.</li>
<li><a href="">#930</a>: Add devcontainer, Add Python3.14, Python3.14t.</li>
<li><a href="">#931</a>: Fix ruff checks about unused variables.</li>
<li><a href="">#932</a>: Dropped EOL Python 3.8 from CI.</li>
<li><a href="">#934</a>: Pre-commit hooks autoupdate.</li>
<li><a href="">#938</a>: Fix typos discovered by typos.</li>
<li>Add OAuthLib Maintainer agent for automated issue/PR triage and release
management.</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>145a9a4</code></a> Release 4.0.0: clarify changelog breaking changes and reformat entries</li>
<li><a href=""><code>c8344d6</code></a> Update CHANGELOG.rst</li>
<li><a href=""><code>e172830</code></a> Release 4.0.0: bump version to 4.0.0 and update changelog</li>
<li><a href=""><code>40b0ab5</code></a> Merge pull request <a href="">#963</a> from oauthlib/ft/pkcecode</li>
<li><a href=""><code>1b68cea</code></a> Merge pull request <a href="">#920</a> from hekhuisk/validate-client-authentication</li>
<li><a href=""><code>c951a1d</code></a> Organized validate_client functions for all grant to avoid mistake in grnat i...</li>
<li><a href=""><code>74664d3</code></a> Improve PKCE code comparison</li>
<li><a href=""><code>9859b05</code></a> Merge pull request <a href="">#950</a> from oauthlib/feature/3.4.0-maintainer-agent</li>
<li><a href=""><code>9bf9b97</code></a> Merge branch 'master' into feature/3.4.0-maintainer-agent</li>
<li><a href=""><code>1ba7429</code></a> Clarify agent instructions</li>
<li>Additional commits viewable in <a href="https://github.com/oauthlib/oauthlib/compare/v3.3.1...v4.0.0">compare view</a></li>
</ul>
</details>
<br />

[![Dependabot compatibility score](https://dependabot-badges.githubapp.com/badges/compatibility_score?dependency-name=oauthlib&package-manager=pip&previous-version=3.3.1&new-version=4.0.0)](https://docs.github.com/en/github/managing-security-vulnerabilities/about-dependabot-security-updates#about-compatibility-scores)

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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6fea28e893a8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.