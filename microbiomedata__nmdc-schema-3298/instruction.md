# Issue

**Title:** Bump the python-dependencies group with 2 updates

## Description

Bumps the python-dependencies group with 2 updates: [mkdocs-material](https://github.com/squidfunk/mkdocs-material) and [ruff](https://github.com/astral-sh/ruff).

Updates `mkdocs-material` from 9.7.6 to 9.7.7
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/squidfunk/mkdocs-material/releases">mkdocs-material's releases</a>.</em></p>
<blockquote>
<h2>mkdocs-material-9.7.7</h2>
<blockquote>
<p>[!WARNING]</p>
<p><strong>Material for MkDocs is approaching end of life</strong></p>
<p>Material for MkDocs is scheduled to reach end of life on November 5, 2026. Until then, maintenance is limited to critical bug fixes and security updates.</p>
<p>The path forward is <a href="https://zensical.org">Zensical</a>, our next-generation static site generator built from first principles. If you’re planning a new documentation project or thinking about your long-term setup, we encourage you to start exploring Zensical.</p>
<p>Organizations requiring support beyond this date can <a href="https://github.com/squidfunk/mkdocs-material/blob/HEAD/mailto:hello@zensical.org">get in touch</a> to discuss options.</p>
<p><a href="https://squidfunk.github.io/mkdocs-material/blog/2025/11/05/zensical/">Read the full announcement on our blog</a></p>
</blockquote>
<h2>Changes</h2>
<ul>
<li>Fixed a DOM-based XSS vulnerability in search suggestions</li>
</ul>
<blockquote>
<p>Thanks to <a href="https://github.com/p"><code>@​p</code></a>- for responsibly reporting this issue.</p>
</blockquote>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/squidfunk/mkdocs-material/blob/master/CHANGELOG">mkdocs-material's changelog</a>.</em></p>
<blockquote>
<p>mkdocs-material-9.7.7 (2026-07-17)</p>
<ul>
<li>Fixed DOM-based XSS vulnerability in search suggestions</li>
</ul>
<p>mkdocs-material-9.7.6 (2026-03-19)</p>
<ul>
<li>Automatically disable MkDocs 2.0 warning for forks of MkDocs</li>
</ul>
<p>mkdocs-material-9.7.5 (2026-03-10)</p>
<ul>
<li>Limited version range of mkdocs to &lt;2</li>
<li>Updated MkDocs 2.0 incompatibility warning (clarify relation with MkDocs)</li>
</ul>
<p>mkdocs-material-9.7.4 (2026-03-03)</p>
<ul>
<li>Hardened social cards plugin by switching to sandboxed environment</li>
<li>Updated MkDocs 2.0 incompatibility warning</li>
</ul>
<p>mkdocs-material-9.7.3 (2026-02-24)</p>
<ul>
<li>Fixed <a href="">#8567</a>: Print MkDocs 2.0 incompatibility warning to stderr</li>
</ul>
<p>mkdocs-material-9.7.2 (2026-02-18)</p>
<ul>
<li>Opened up version ranges of optional dependencies for forward-compatibility</li>
<li>Added warning to 'mkdocs build' about impending MkDocs 2.0 incompatibility</li>
</ul>
<p>mkdocs-material-9.7.1 (2025-12-18)</p>
<ul>
<li>Updated requests to 2.30+ to mitigate CVE in urllib</li>
<li>Fixed privacy plugin not picking up protocol-relative URLs</li>
<li>Fixed <a href="">#8542</a>: false positives and negatives captured in privacy plugin</li>
</ul>
<p>mkdocs-material-9.7.0 (2025-11-11)</p>
<p>⚠️ Material for MkDocs is now in maintenance mode</p>
<p>This is the last release of Material for MkDocs that will receive new features.
Going forward, the Material for MkDocs team focuses on Zensical, a next-gen
static site generator built from first principles. We will provide critical
bug fixes and security updates for Material for MkDocs for 12 months at least.</p>
<p>Read the full announcement on our blog:
<a href="https://squidfunk.github.io/mkdocs-material/blog/2025/11/05/zensical/">https://squidfunk.github.io/mkdocs-material/blog/2025/11/05/zensical/</a></p>
<p>This release includes all features that were previously exclusive to the
Insiders edition. These features are now freely available to everyone.</p>
<p>Note on deprecated plugins: The projects and typeset plugins are included in
this release, but must be considered deprecated. Both plugins proved</p>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>b3e6dd8</code></a> Prepare 9.7.7 release</li>
<li><a href=""><code>52fb6be</code></a> Merge commit from fork</li>
<li><a href=""><code>901e633</code></a> Added <code>SECURITY.md</code> with EOL notice</li>
<li><a href=""><code>5b36f2a</code></a> Bump js-yaml from 4.1.1 to 4.2.0 (<a href="">#8598</a>)</li>
<li><a href=""><code>2d11e7b</code></a> Bump form-data from 3.0.4 to 3.0.5 (<a href="">#8597</a>)</li>
<li><a href=""><code>ae05a53</code></a> Bump esbuild from 0.27.2 to 0.28.1 (<a href="">#8596</a>)</li>
<li><a href=""><code>434af93</code></a> Bump shell-quote from 1.7.3 to 1.8.4 (<a href="">#8593</a>)</li>
<li><a href=""><code>4447cda</code></a> Documentation (<a href="">#8590</a>)</li>
<li><a href=""><code>8f8d551</code></a> Updated copyright year (<a href="">#8588</a>)</li>
<li><a href=""><code>08d8514</code></a> Bump fast-uri from 3.0.3 to 3.1.2 (<a href="">#8587</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/squidfunk/mkdocs-material/compare/9.7.6...9.7.7">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.15.21 to 0.15.22
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.15.22</h2>
<h2>Release Notes</h2>
<p>Released on 2026-07-16.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>pycodestyle</code>] Add an autofix for <code>E402</code> (<a href="">#22212</a>)</li>
<li>[<code>refurb</code>] Allow subclassing builtins in stub files (<code>FURB189</code>) (<a href="">#26812</a>)</li>
<li>[<code>ruff</code>] Add rule to replace <code>noqa</code> comments with <code>ruff:ignore</code> (<code>RUF105</code>) (<a href="">#26423</a>)</li>
<li>[<code>ruff</code>] Add rule to use human-readable names in <code>ruff:ignore</code> comments (<code>RUF106</code>) (<a href="">#26682</a>)</li>
<li>[<code>ruff</code>] Add rule to use human-readable names in configuration selectors (<code>RUF201</code>) (<a href="">#26772</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-pyi</code>] Fix false positive in <code>__all__</code> (<code>PYI053</code>) (<a href="">#26872</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>pylint</code>] Ignore mutable type updates in <code>redefined-loop-name</code> (<code>PLW2901</code>) (<a href="">#25733</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Avoid redundant lexer token bookkeeping (<a href="">#26765</a>)</li>
<li>Avoid redundant pending-indentation writes (<a href="">#26774</a>)</li>
<li>Avoid unnecessary identifier lookahead (<a href="">#26525</a>)</li>
<li>Reuse parser scratch buffers (<a href="">#26798</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Document argfile support (<a href="">#26803</a>)</li>
<li>[<code>flake8-datetimez</code>] Clarify naming guidance for <code>datetime.today</code> (<code>DTZ002</code>) (<a href="">#26658</a>)</li>
<li>[<code>pycodestyle</code>] Document <code>E731</code> fix safety (<a href="">#26847</a>)</li>
<li>[<code>ruff</code>] Clarify intentional async contexts for <code>unused-async</code> (<code>RUF029</code>) (<a href="">#26641</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/dwego"><code>@​dwego</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/Joosboy"><code>@​Joosboy</code></a></li>
<li><a href="https://github.com/KaufmanDmitriy"><code>@​KaufmanDmitriy</code></a></li>
<li><a href="https://github.com/PeterJCLaw"><code>@​PeterJCLaw</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
</ul>
<h2>Install ruff 0.15.22</h2>
<h3>Install prebuilt binaries via shell script</h3>
<pre lang="sh"><code>&lt;/tr&gt;&lt;/table&gt;
</code></pre>
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.15.22</h2>
<p>Released on 2026-07-16.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>pycodestyle</code>] Add an autofix for <code>E402</code> (<a href="">#22212</a>)</li>
<li>[<code>refurb</code>] Allow subclassing builtins in stub files (<code>FURB189</code>) (<a href="">#26812</a>)</li>
<li>[<code>ruff</code>] Add rule to replace <code>noqa</code> comments with <code>ruff:ignore</code> (<code>RUF105</code>) (<a href="">#26423</a>)</li>
<li>[<code>ruff</code>] Add rule to use human-readable names in <code>ruff:ignore</code> comments (<code>RUF106</code>) (<a href="">#26682</a>)</li>
<li>[<code>ruff</code>] Add rule to use human-readable names in configuration selectors (<code>RUF201</code>) (<a href="">#26772</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-pyi</code>] Fix false positive in <code>__all__</code> (<code>PYI053</code>) (<a href="">#26872</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>pylint</code>] Ignore mutable type updates in <code>redefined-loop-name</code> (<code>PLW2901</code>) (<a href="">#25733</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Avoid redundant lexer token bookkeeping (<a href="">#26765</a>)</li>
<li>Avoid redundant pending-indentation writes (<a href="">#26774</a>)</li>
<li>Avoid unnecessary identifier lookahead (<a href="">#26525</a>)</li>
<li>Reuse parser scratch buffers (<a href="">#26798</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Document argfile support (<a href="">#26803</a>)</li>
<li>[<code>flake8-datetimez</code>] Clarify naming guidance for <code>datetime.today</code> (<code>DTZ002</code>) (<a href="">#26658</a>)</li>
<li>[<code>pycodestyle</code>] Document <code>E731</code> fix safety (<a href="">#26847</a>)</li>
<li>[<code>ruff</code>] Clarify intentional async contexts for <code>unused-async</code> (<code>RUF029</code>) (<a href="">#26641</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/dwego"><code>@​dwego</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/Joosboy"><code>@​Joosboy</code></a></li>
<li><a href="https://github.com/KaufmanDmitriy"><code>@​KaufmanDmitriy</code></a></li>
<li><a href="https://github.com/PeterJCLaw"><code>@​PeterJCLaw</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>0177a7e</code></a> Bump 0.15.22 (<a href="">#26884</a>)</li>
<li><a href=""><code>fe8ba85</code></a> [<code>pycodestyle</code>] Document <code>E731</code> fix safety (<a href="">#26847</a>)</li>
<li><a href=""><code>f3cf7c8</code></a> [<code>ruff</code>] Add <code>rule-codes-in-selectors</code> (<code>RUF201</code>) (<a href="">#26772</a>)</li>
<li><a href=""><code>d244fd7</code></a> Document argfile support (<a href="">#26803</a>)</li>
<li><a href=""><code>f239758</code></a> [<code>flake8-pyi</code>] Fix false positive in <code>__all__</code> (<code>PYI053</code>) (<a href="">#26872</a>)</li>
<li><a href=""><code>54acbcd</code></a> [ty] Support <code>TypeVarTuple</code> and <code>Unpack</code> (<a href="">#25240</a>)</li>
<li><a href=""><code>87fc38c</code></a> [ty] Parallelize subtype hierarchy search (<a href="">#26875</a>)</li>
<li><a href=""><code>e454f91</code></a> [ty] Share interned query keys across Salsa queries (<a href="">#26794</a>)</li>
<li><a href=""><code>6f361a7</code></a> [ty] only collect expected types for files open in the editor (<a href="">#25546</a>)</li>
<li><a href=""><code>6d6b2b3</code></a> [ty] Avoid allocations during Salsa interned lookups (<a href="">#26877</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.15.21...0.15.22">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `258b0aa79663`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.