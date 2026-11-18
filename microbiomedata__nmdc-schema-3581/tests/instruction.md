# Issue

**Title:** Bump the github-actions group across 1 directory with 6 updates

## Description

Bumps the github-actions group with 6 updates in the / directory:

| Package | From | To |
| --- | --- | --- |
| [astral-sh/setup-uv](https://github.com/astral-sh/setup-uv) | `10.3.0` | `10.3.2` |
| [actions/setup-python](https://github.com/actions/setup-python) | `7.0.0` | `7.1.0` |
| [github/codeql-action/init](https://github.com/github/codeql-action) | `4.38.3` | `4.39.1` |
| [github/codeql-action/analyze](https://github.com/github/codeql-action) | `4.38.3` | `4.39.1` |
| [pypa/gh-action-pypi-publish](https://github.com/pypa/gh-action-pypi-publish) | `1.14.2` | `1.14.3` |
| [github/codeql-action/upload-sarif](https://github.com/github/codeql-action) | `4.38.3` | `4.39.1` |

Updates `astral-sh/setup-uv` from 10.3.0 to 10.3.2
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/setup-uv/releases">astral-sh/setup-uv's releases</a>.</em></p>
<blockquote>
<h2>v10.3.2 🌈 update known checksums for 0.13.5</h2>
<h2>Changes</h2>
<h2>🧰 Maintenance</h2>
<ul>
<li>chore: update known checksums for 0.13.5 @<a href="https://github.com/apps/github-actions">github-actions[bot]</a> (<a href="">#1103</a>)</li>
</ul>
<h2>📚 Documentation</h2>
<ul>
<li>docs: update version references to v10.3.1 @<a href="https://github.com/apps/github-actions">github-actions[bot]</a> (<a href="">#1102</a>)</li>
</ul>
<h2>v10.3.1 🌈 preserve cache error class names in save-cache bundle</h2>
<h2>Changes</h2>
<p>This release includes a fix so that multiple concurrent workflows trying to upload the same cache no longer warn</p>
<p><code>##[warning]Failed to save: Unable to reserve cache with key ..., another job may be creating this cache.</code></p>
<h2>🐛 Bug fixes</h2>
<ul>
<li>fix: preserve cache error class names in save-cache bundle <a href="https://github.com/dannyward630"><code>@​dannyward630</code></a> (<a href="">#1093</a>)</li>
</ul>
<h2>🧰 Maintenance</h2>
<ul>
<li>chore: update known checksums for 0.13.4 @<a href="https://github.com/apps/github-actions">github-actions[bot]</a> (<a href="">#1099</a>)</li>
<li>chore: update known checksums for 0.13.2/0.13.3 @<a href="https://github.com/apps/github-actions">github-actions[bot]</a> (<a href="">#1098</a>)</li>
<li>chore: update known checksums for 0.13.1 @<a href="https://github.com/apps/github-actions">github-actions[bot]</a> (<a href="">#1094</a>)</li>
<li>Verify npm dependency signatures before builds <a href="https://github.com/zaniebot"><code>@​zaniebot</code></a> (<a href="">#1027</a>)</li>
</ul>
<h2>📚 Documentation</h2>
<ul>
<li>docs: cache-dependency-glob matches relative to the working directory <a href="https://github.com/flange-ipb"><code>@​flange-ipb</code></a> (<a href="">#1092</a>)</li>
<li>docs: update version references to v10.3.0 @<a href="https://github.com/apps/github-actions">github-actions[bot]</a> (<a href="">#1090</a>)</li>
</ul>
<h2>⬆️ Dependency updates</h2>
<ul>
<li>chore(deps): roll up Dependabot updates <a href="https://github.com/eifinger"><code>@​eifinger</code></a> (<a href="">#1101</a>)</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>07a047e</code></a> chore: update known checksums for 0.13.5 (<a href="">#1103</a>)</li>
<li><a href=""><code>e1b8536</code></a> docs: update version references to v10.3.1 (<a href="">#1102</a>)</li>
<li><a href=""><code>18d369b</code></a> chore(deps): roll up Dependabot updates (<a href="">#1101</a>)</li>
<li><a href=""><code>4ad2329</code></a> chore: update known checksums for 0.13.4 (<a href="">#1099</a>)</li>
<li><a href=""><code>4bc6759</code></a> chore: update known checksums for 0.13.2/0.13.3 (<a href="">#1098</a>)</li>
<li><a href=""><code>c97f06e</code></a> fix: preserve cache error class names in save-cache bundle (<a href="">#1093</a>)</li>
<li><a href=""><code>8ca4be0</code></a> chore: update known checksums for 0.13.1 (<a href="">#1094</a>)</li>
<li><a href=""><code>b627d85</code></a> docs: cache-dependency-glob matches relative to the working directory (<a href="">#1092</a>)</li>
<li><a href=""><code>f8c8897</code></a> Verify npm dependency signatures before builds (<a href="">#1027</a>)</li>
<li><a href=""><code>f64d32b</code></a> docs: update version references to v10.3.0 (<a href="">#1090</a>)</li>
<li>See full diff in <a href="https://github.com/astral-sh/setup-uv/compare/1c37ad07a6a961277cf70c0d37d6f313000f5884...07a047e608db84b3d8c06cd9a7c7dcc9c355c18e">compare view</a></li>
</ul>
</details>
<br />

Updates `actions/setup-python` from 7.0.0 to 7.1.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/actions/setup-python/releases">actions/setup-python's releases</a>.</em></p>
<blockquote>
<h2>v7.1.0</h2>
<h2>What's Changed</h2>
<h3>Enhancements</h3>
<ul>
<li>Add <code>mirror</code> and <code>mirror-token</code> inputs for custom Python distribution sources by <a href="https://github.com/luhenry"><code>@​luhenry</code></a> in <a href="">actions/setup-python#1302</a></li>
<li>Improve error message clarity by <a href="https://github.com/v-lmvysakh"><code>@​v-lmvysakh</code></a> in <a href="">actions/setup-python#1351</a></li>
</ul>
<h3>Dependency Upgrade</h3>
<ul>
<li>Upgrade browserslist from 4.28.2 to 4.28.9 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1353</a></li>
<li>Upgrade <code>@​typescript-eslint/parser</code> from 8.62.0 to 8.70.0 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1343</a></li>
<li>Upgrade eslint-plugin-jest from 29.15.2 to 29.16.6 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1342</a></li>
<li>Upgrade <code>@​vercel/ncc</code> from 0.44.0 to 0.45.0 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1357</a></li>
<li>Upgrade <code>@​types/semver</code> from 7.7.1 to 7.8.0 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1359</a></li>
<li>Upgrade undici from 6.28.0 to 6.29.0 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1364</a></li>
<li>Upgrade ts-jest from 29.4.11 to 29.4.14 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1361</a></li>
<li>Upgrade brace-expansion from 5.0.9 to 5.0.12 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1365</a></li>
<li>Upgrade prettier from 3.8.4 to 3.9.9 and package.json from 7.0.0 to 7.1.0 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1363</a></li>
<li>Upgrade <code>@​typescript-eslint/eslint-plugin</code> from 8.62.0 to 8.71.1 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1369</a></li>
<li>Upgrade actions/checkout from 7.0.0 to 7.0.1 by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1345</a></li>
<li>Upgrade cache to 6.3.0 by <a href="https://github.com/v-HarithaVattikuti"><code>@​v-HarithaVattikuti</code></a> in <a href="">actions/setup-python#1370</a></li>
<li>Resolve Basic Validation audit failures by <a href="https://github.com/v-HarithaVattikuti"><code>@​v-HarithaVattikuti</code></a> in <a href="">actions/setup-python#1347</a></li>
<li>Resolve npm audit failures by <a href="https://github.com/v-HarithaVattikuti"><code>@​v-HarithaVattikuti</code></a> in <a href="">actions/setup-python#1350</a></li>
</ul>
<h2>New Contributors</h2>
<ul>
<li><a href="https://github.com/luhenry"><code>@​luhenry</code></a> made their first contribution in <a href="">actions/setup-python#1302</a></li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/actions/setup-python/compare/v7.0.0...v7.1.0">https://github.com/actions/setup-python/compare/v7.0.0...v7.1.0</a></p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>6d4fd22</code></a> Cache upgrade to 6.3.0 (<a href="">#1370</a>)</li>
<li><a href=""><code>ec52d0a</code></a> Bump <code>@​typescript-eslint/eslint-plugin</code> from 8.62.0 to 8.71.1 (<a href="">#1369</a>)</li>
<li><a href=""><code>ff73b24</code></a> Bump prettier from 3.8.4 to 3.9.9 and package.json from 7.0.0 to 7.1.0 (<a href="">#1363</a>)</li>
<li><a href=""><code>0e40890</code></a> Bump brace-expansion from 5.0.9 to 5.0.12 (<a href="">#1365</a>)</li>
<li><a href=""><code>3892123</code></a> Bump ts-jest from 29.4.11 to 29.4.14 (<a href="">#1361</a>)</li>
<li><a href=""><code>6609657</code></a> Bump undici from 6.28.0 to 6.29.0 (<a href="">#1364</a>)</li>
<li><a href=""><code>e1be392</code></a> Bump <code>@​types/semver</code> from 7.7.1 to 7.8.0 (<a href="">#1359</a>)</li>
<li><a href=""><code>06da627</code></a> Bump <code>@​vercel/ncc</code> from 0.44.0 to 0.45.0 (<a href="">#1357</a>)</li>
<li><a href=""><code>af9bcc7</code></a> Bump eslint-plugin-jest from 29.15.2 to 29.16.6 (<a href="">#1342</a>)</li>
<li><a href=""><code>7aeabeb</code></a> Bump <code>@​typescript-eslint/parser</code> from 8.62.0 to 8.70.0 (<a href="">#1343</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/actions/setup-python/compare/5fda3b95a4ea91299a34e894583c3862153e4b97...6d4fd22b20465ccc0f7354476588e8df7c9ca0e0">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/init` from 4.38.3 to 4.39.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/init's releases</a>.</em></p>
<blockquote>
<h2>v4.39.1</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>v4.39.0</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/blob/main/CHANGELOG.md">github/codeql-action/init's changelog</a>.</em></p>
<blockquote>
<h1>CodeQL Action Changelog</h1>
<p>See the <a href="https://github.com/github/codeql-action/releases">releases page</a> for the relevant changes to the CodeQL CLI and language packs.</p>
<h2>[UNRELEASED]</h2>
<p>No user facing changes.</p>
<h2>4.39.1 - 21 Oct 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>4.39.0 - 15 Oct 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
<h2>4.38.3 - 08 Oct 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: CodeQL version 2.21.2 and earlier were discontinued on 24 September 2026 alongside GitHub Enterprise Server 3.17, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4188</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.2">2.27.2</a>. <a href="">#4203</a></li>
<li>Fixed a bug where the decision of whether to use a per-language bundle did not account for custom configurations that reference queries outside of compiled CodeQL packs. This issue was caught during internal testing and did not affect any customer repositories. We will resume the roll out of per-language bundles in the coming weeks. <a href="">#4184</a></li>
</ul>
<h2>4.38.2 - 24 Sept 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.1">2.27.1</a>. <a href="">#4160</a></li>
</ul>
<h2>4.38.1 - 18 Sept 2026</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
</ul>
<h2>4.38.0 - 09 Sept 2026</h2>
<ul>
<li>On GitHub-hosted runners, the CodeQL Action now deletes unused CodeQL bundles from the toolcache before downloading a different bundle, which frees up disk space for the analysis. We expect to roll this change out to everyone in September. <a href="">#4124</a></li>
<li>The CodeQL Action now supports CodeQL releases that are compatible with Linux Arm64 and downloads the native <code>linux-arm64</code> CodeQL bundle when available. <a href="">#4072</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.0">2.27.0</a>. <a href="">#4129</a></li>
</ul>
<h2>4.37.9 - 26 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.4">2.26.4</a>. <a href="">#4106</a></li>
</ul>
<h2>4.37.8 - 21 Aug 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.7 - 13 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.3">2.26.3</a>. <a href="">#4085</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>9b32540</code></a> Merge pull request <a href="">#4257</a> from github/update-v4.39.1-c5a2f4b0f</li>
<li><a href=""><code>b5e1ed9</code></a> Trigger workflows</li>
<li><a href=""><code>20f5ec3</code></a> Update changelog for v4.39.1</li>
<li><a href=""><code>c5a2f4b</code></a> Merge pull request <a href="">#4245</a> from github/henrymercer/graduate-overlay-trap-caching</li>
<li><a href=""><code>61a5a80</code></a> Merge pull request <a href="">#4256</a> from github/update-bundle/codeql-bundle-v2.27.3</li>
<li><a href=""><code>3dd33f8</code></a> Merge pull request <a href="">#4249</a> from github/mbg/upload-improvements-for-4223</li>
<li><a href=""><code>b96e339</code></a> Change comment for <code>getConfig</code> call in <code>upload-sarif</code></li>
<li><a href=""><code>7fa4518</code></a> Use <code>shouldSkipSarifUpload</code> in <code>analyze-action.ts</code></li>
<li><a href=""><code>a69c7cb</code></a> Document that setting the env vars to <code>false</code> takes precedence</li>
<li><a href=""><code>74ddcd9</code></a> Fix typo in comment</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/24c54180a607b1449ed407dd24f251e4e9147c8d...9b3254085494b55a0f7c4c2b3d2d52cc712ce370">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/analyze` from 4.38.3 to 4.39.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/analyze's releases</a>.</em></p>
<blockquote>
<h2>v4.39.1</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>v4.39.0</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/blob/main/CHANGELOG.md">github/codeql-action/analyze's changelog</a>.</em></p>
<blockquote>
<h1>CodeQL Action Changelog</h1>
<p>See the <a href="https://github.com/github/codeql-action/releases">releases page</a> for the relevant changes to the CodeQL CLI and language packs.</p>
<h2>[UNRELEASED]</h2>
<p>No user facing changes.</p>
<h2>4.39.1 - 21 Oct 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>4.39.0 - 15 Oct 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
<h2>4.38.3 - 08 Oct 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: CodeQL version 2.21.2 and earlier were discontinued on 24 September 2026 alongside GitHub Enterprise Server 3.17, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4188</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.2">2.27.2</a>. <a href="">#4203</a></li>
<li>Fixed a bug where the decision of whether to use a per-language bundle did not account for custom configurations that reference queries outside of compiled CodeQL packs. This issue was caught during internal testing and did not affect any customer repositories. We will resume the roll out of per-language bundles in the coming weeks. <a href="">#4184</a></li>
</ul>
<h2>4.38.2 - 24 Sept 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.1">2.27.1</a>. <a href="">#4160</a></li>
</ul>
<h2>4.38.1 - 18 Sept 2026</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
</ul>
<h2>4.38.0 - 09 Sept 2026</h2>
<ul>
<li>On GitHub-hosted runners, the CodeQL Action now deletes unused CodeQL bundles from the toolcache before downloading a different bundle, which frees up disk space for the analysis. We expect to roll this change out to everyone in September. <a href="">#4124</a></li>
<li>The CodeQL Action now supports CodeQL releases that are compatible with Linux Arm64 and downloads the native <code>linux-arm64</code> CodeQL bundle when available. <a href="">#4072</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.0">2.27.0</a>. <a href="">#4129</a></li>
</ul>
<h2>4.37.9 - 26 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.4">2.26.4</a>. <a href="">#4106</a></li>
</ul>
<h2>4.37.8 - 21 Aug 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.7 - 13 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.3">2.26.3</a>. <a href="">#4085</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>9b32540</code></a> Merge pull request <a href="">#4257</a> from github/update-v4.39.1-c5a2f4b0f</li>
<li><a href=""><code>b5e1ed9</code></a> Trigger workflows</li>
<li><a href=""><code>20f5ec3</code></a> Update changelog for v4.39.1</li>
<li><a href=""><code>c5a2f4b</code></a> Merge pull request <a href="">#4245</a> from github/henrymercer/graduate-overlay-trap-caching</li>
<li><a href=""><code>61a5a80</code></a> Merge pull request <a href="">#4256</a> from github/update-bundle/codeql-bundle-v2.27.3</li>
<li><a href=""><code>3dd33f8</code></a> Merge pull request <a href="">#4249</a> from github/mbg/upload-improvements-for-4223</li>
<li><a href=""><code>b96e339</code></a> Change comment for <code>getConfig</code> call in <code>upload-sarif</code></li>
<li><a href=""><code>7fa4518</code></a> Use <code>shouldSkipSarifUpload</code> in <code>analyze-action.ts</code></li>
<li><a href=""><code>a69c7cb</code></a> Document that setting the env vars to <code>false</code> takes precedence</li>
<li><a href=""><code>74ddcd9</code></a> Fix typo in comment</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/24c54180a607b1449ed407dd24f251e4e9147c8d...9b3254085494b55a0f7c4c2b3d2d52cc712ce370">compare view</a></li>
</ul>
</details>
<br />

Updates `pypa/gh-action-pypi-publish` from 1.14.2 to 1.14.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pypa/gh-action-pypi-publish/releases">pypa/gh-action-pypi-publish's releases</a>.</em></p>
<blockquote>
<h2>v1.14.3</h2>
<!-- raw HTML omitted -->
<blockquote>
<p>[!important]
🚨 This release includes fixes for <a href="https://github.com/pypa/gh-action-pypi-publish/security/advisories/GHSA-5xjx-3w67-w9x9">GHSA-5xjx-3w67-w9x9</a> patched up by <a href="https://github.com/sethmlarson"><code>@​sethmlarson</code></a><a href="https://github.com/sponsors/sethmlarson">💰</a> in <a href="">#427</a> and in other places across the ecosystem.</p>
<p>Additional ecosystem and related mitigations beyond you might want to watch out for:</p>
<ul>
<li><a href="https://discuss.python.org/t/information-for-python-users-regarding-emudhra-emsign-ca-certificate-security-incident/109576">https://discuss.python.org/t/information-for-python-users-regarding-emudhra-emsign-ca-certificate-security-incident/109576</a></li>
<li><a href="https://emudhra.we-have-a-problem.com">https://emudhra.we-have-a-problem.com</a></li>
</ul>
</blockquote>
<h2>🛠️ Security Tightening</h2>
<p><a href="https://github.com/webknjaz"><code>@​webknjaz</code></a><a href="https://github.com/sponsors/webknjaz">💰</a> made sure the dependency tree within the action runtime uses hash-checking from now on via <a href="">pypa/gh-action-pypi-publish#420</a>.</p>
<p><strong>🪞 Full Diff</strong>: <a href="https://github.com/pypa/gh-action-pypi-publish/compare/v1.14.2...v1.14.3">https://github.com/pypa/gh-action-pypi-publish/compare/v1.14.2...v1.14.3</a></p>
<p><strong>🧔‍♂️ Release Manager:</strong> <a href="https://github.com/sponsors/webknjaz"><code>@​webknjaz</code></a> <a href="https://stand-with-ukraine.pp.ua">🇺🇦</a></p>
<p><strong>💬 Discuss</strong> <a href="https://bsky.app/profile/webknjaz.me/post/3mydcjweyak2f">on Bluesky 🦋</a>, <a href="https://mastodon.social/@webknjaz/117474743338290807">on Mastodon 🐘</a> and <a href="https://github.com/pypa/gh-action-pypi-publish/discussions/429">on GitHub</a>.</p>
<p><a href="https://github.com/sponsors/webknjaz"><img src="https://img.shields.io/badge/%40webknjaz-transparent?logo=githubsponsors&amp;logoColor=%23EA4AAA&amp;label=Sponsor&amp;color=2a313c" alt="GH Sponsors badge" /></a></p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>7245906</code></a> Merge pull request <a href="">#427</a> from sethmlarson/certifi-sigstore</li>
<li><a href=""><code>331eccb</code></a> Upgrade certifi and sigstore</li>
<li><a href=""><code>f68fee4</code></a> 💰 Sync the FUNDING config</li>
<li><a href=""><code>c0d6f8e</code></a> Merge branch 'integrity/runtime/deptree' into unstable/v1</li>
<li><a href=""><code>9090099</code></a> 🧪 Make smoke test deps hash-pinned in CI</li>
<li><a href=""><code>34e40c2</code></a> 📌 Bump pip-tools managed transitive deptrees</li>
<li><a href=""><code>e800ed5</code></a> 👷 Enable hash-checking in the runtime deptree 🔗</li>
<li><a href=""><code>dd8c5f4</code></a> 🔧 Make pip-tools config available in container</li>
<li>See full diff in <a href="https://github.com/pypa/gh-action-pypi-publish/compare/dc37677b2e1c63e2034f94d8a5b11f265b73ba33...7245906fb61fa33a13554f9d5fb856fe61758086">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/upload-sarif` from 4.38.3 to 4.39.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/upload-sarif's releases</a>.</em></p>
<blockquote>
<h2>v4.39.1</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>v4.39.0</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/blob/main/CHANGELOG.md">github/codeql-action/upload-sarif's changelog</a>.</em></p>
<blockquote>
<h1>CodeQL Action Changelog</h1>
<p>See the <a href="https://github.com/github/codeql-action/releases">releases page</a> for the relevant changes to the CodeQL CLI and language packs.</p>
<h2>[UNRELEASED]</h2>
<p>No user facing changes.</p>
<h2>4.39.1 - 21 Oct 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>4.39.0 - 15 Oct 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
<h2>4.38.3 - 08 Oct 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: CodeQL version 2.21.2 and earlier were discontinued on 24 September 2026 alongside GitHub Enterprise Server 3.17, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4188</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.2">2.27.2</a>. <a href="">#4203</a></li>
<li>Fixed a bug where the decision of whether to use a per-language bundle did not account for custom configurations that reference queries outside of compiled CodeQL packs. This issue was caught during internal testing and did not affect any customer repositories. We will resume the roll out of per-language bundles in the coming weeks. <a href="">#4184</a></li>
</ul>
<h2>4.38.2 - 24 Sept 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.1">2.27.1</a>. <a href="">#4160</a></li>
</ul>
<h2>4.38.1 - 18 Sept 2026</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
</ul>
<h2>4.38.0 - 09 Sept 2026</h2>
<ul>
<li>On GitHub-hosted runners, the CodeQL Action now deletes unused CodeQL bundles from the toolcache before downloading a different bundle, which frees up disk space for the analysis. We expect to roll this change out to everyone in September. <a href="">#4124</a></li>
<li>The CodeQL Action now supports CodeQL releases that are compatible with Linux Arm64 and downloads the native <code>linux-arm64</code> CodeQL bundle when available. <a href="">#4072</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.0">2.27.0</a>. <a href="">#4129</a></li>
</ul>
<h2>4.37.9 - 26 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.4">2.26.4</a>. <a href="">#4106</a></li>
</ul>
<h2>4.37.8 - 21 Aug 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.7 - 13 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.3">2.26.3</a>. <a href="">#4085</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>9b32540</code></a> Merge pull request <a href="">#4257</a> from github/update-v4.39.1-c5a2f4b0f</li>
<li><a href=""><code>b5e1ed9</code></a> Trigger workflows</li>
<li><a href=""><code>20f5ec3</code></a> Update changelog for v4.39.1</li>
<li><a href=""><code>c5a2f4b</code></a> Merge pull request <a href="">#4245</a> from github/henrymercer/graduate-overlay-trap-caching</li>
<li><a href=""><code>61a5a80</code></a> Merge pull request <a href="">#4256</a> from github/update-bundle/codeql-bundle-v2.27.3</li>
<li><a href=""><code>3dd33f8</code></a> Merge pull request <a href="">#4249</a> from github/mbg/upload-improvements-for-4223</li>
<li><a href=""><code>b96e339</code></a> Change comment for <code>getConfig</code> call in <code>upload-sarif</code></li>
<li><a href=""><code>7fa4518</code></a> Use <code>shouldSkipSarifUpload</code> in <code>analyze-action.ts</code></li>
<li><a href=""><code>a69c7cb</code></a> Document that setting the env vars to <code>false</code> takes precedence</li>
<li><a href=""><code>74ddcd9</code></a> Fix typo in comment</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/24c54180a607b1449ed407dd24f251e4e9147c8d...9b3254085494b55a0f7c4c2b3d2d52cc712ce370">compare view</a></li>
</ul>
</details>
<br />

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
- `@dependabot ignore <dependency name> major version` will close this group update PR and stop Dependabot creating any more for the specific dependency's major version (unless you unignore this specific dependency's major version or upgrade to it yourself)
- `@dependabot ignore <dependency name> minor version` will close this group update PR and stop Dependabot creating any more for the specific dependency's minor version (unless you unignore this specific dependency's minor version or upgrade to it yourself)
- `@dependabot ignore <dependency name>` will close this group update PR and stop Dependabot creating any more for the specific dependency (unless you unignore this specific dependency or upgrade to it yourself)
- `@dependabot unignore <dependency name>` will remove all of the ignore conditions of the specified dependency
- `@dependabot unignore <dependency name> <ignore condition>` will remove the ignore condition of the specified dependency and ignore conditions

</details>

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `64360acb2900`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.