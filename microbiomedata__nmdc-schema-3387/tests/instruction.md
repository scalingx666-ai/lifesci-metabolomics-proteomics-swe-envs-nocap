# Issue

**Title:** Bump the python-dependencies group with 4 updates

## Description

Bumps the python-dependencies group with 4 updates: [idna](https://github.com/kjd/idna), [python-dotenv](https://github.com/theskumar/python-dotenv), [pymdown-extensions](https://github.com/facelessuser/pymdown-extensions) and [ruff](https://github.com/astral-sh/ruff).

Updates `idna` from 3.18 to 3.19
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/kjd/idna/releases">idna's releases</a>.</em></p>
<blockquote>
<h2>v3.19</h2>
<ul>
<li>Restore the <code>std3_rules</code> option, which had no effect since changes
to UTS <a href="">#46</a> processing in Unicode 16. Note that <code>uts46_remap()</code>
defaults to enabling STD3 rules, so direct callers will see input
containing non-LDH ASCII characters rejected again.</li>
<li>Performance improvements to UTS <a href="">#46</a> mapping, particularly for
ASCII-only domains.</li>
<li>Test on free-threaded CPython with the GIL disabled and document
thread safety.</li>
<li>Expose the Unicode version of the generated tables as
<code>idna.unicode_version</code>, and show it in <code>idna --version</code>.</li>
<li>Add <code>code</code>, <code>text</code>, <code>codepoint</code> and <code>position</code> attributes to
<code>IDNAError</code> so that the failed rule and the offending character can
be identified without parsing the exception message.</li>
<li>The deprecated <code>transitional</code> argument to <code>encode()</code> and
<code>uts46_remap()</code> is now completely ignored, and gives a deprecation warning
for the latter.</li>
<li>Reject A-labels that are not the canonical Punycode encoding of
their U-label.</li>
<li>Fix CONTEXTJ violations raising <code>IDNAError</code> instead of
<code>InvalidCodepointContext</code>.</li>
<li>Consistently raise <code>IDNAError</code> for empty labels and non-ASCII bytes
passed to label helper functions and the incremental codec.</li>
<li>Add property-based tests, extended fuzzing targets, coverage
measurement, and CI checks that the data tables match the generator
output.</li>
<li>Various code quality and tooling improvements.</li>
</ul>
<p>Thanks to stefan6419846, LouieLuNZ, and Salvatore Corvaglia for
contributions to this release.</p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/kjd/idna/blob/master/HISTORY.md">idna's changelog</a>.</em></p>
<blockquote>
<h2>3.19 (2026-08-18)</h2>
<ul>
<li>Restore the <code>std3_rules</code> option, which had no effect since changes
to UTS <a href="">#46</a> processing in Unicode 16. Note that <code>uts46_remap()</code>
defaults to enabling STD3 rules, so direct callers will see input
containing non-LDH ASCII characters rejected again.</li>
<li>Performance improvements to UTS <a href="">#46</a> mapping, particularly for
ASCII-only domains.</li>
<li>Test on free-threaded CPython with the GIL disabled and document
thread safety.</li>
<li>Expose the Unicode version of the generated tables as
<code>idna.unicode_version</code>, and show it in <code>idna --version</code>.</li>
<li>Add <code>code</code>, <code>text</code>, <code>codepoint</code> and <code>position</code> attributes to
<code>IDNAError</code> so that the failed rule and the offending character can
be identified without parsing the exception message.</li>
<li>The deprecated <code>transitional</code> argument to <code>encode()</code> and
<code>uts46_remap()</code> is now completely ignored, and gives a deprecation warning
for the latter.</li>
<li>Reject A-labels that are not the canonical Punycode encoding of
their U-label.</li>
<li>Fix CONTEXTJ violations raising <code>IDNAError</code> instead of
<code>InvalidCodepointContext</code>.</li>
<li>Consistently raise <code>IDNAError</code> for empty labels and non-ASCII bytes
passed to label helper functions and the incremental codec.</li>
<li>Add property-based tests, extended fuzzing targets, coverage
measurement, and CI checks that the data tables match the generator
output.</li>
<li>Various code quality and tooling improvements.</li>
</ul>
<p>Thanks to stefan6419846, LouieLuNZ, and Salvatore Corvaglia for
contributions to this release.</p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>03a9a11</code></a> Release 3.19</li>
<li><a href=""><code>2d2a7ef</code></a> Pre-release 3.19rc0</li>
<li><a href=""><code>5cce130</code></a> Merge pull request <a href="">#268</a> from kjd/fix-std3-regex-alert</li>
<li><a href=""><code>3914b75</code></a> Split the STD3 disallowed-character range so uppercase is explicit</li>
<li><a href=""><code>ce9fd98</code></a> Merge pull request <a href="">#267</a> from kjd/housekeeping</li>
<li><a href=""><code>809240c</code></a> Fail CI when the license copyright year is behind the current year</li>
<li><a href=""><code>d9e16c5</code></a> Consolidate test fixtures, prune stale gitignore entries, and fix doc typos</li>
<li><a href=""><code>ef30fee</code></a> Remove dead code and pare back superfluous comments</li>
<li><a href=""><code>b907913</code></a> Tighten the version support and Unicode notes in the README</li>
<li><a href=""><code>6204cbe</code></a> Ignore local build artifacts and stop packaging stray tooling config</li>
<li>Additional commits viewable in <a href="https://github.com/kjd/idna/compare/v3.18...v3.19">compare view</a></li>
</ul>
</details>
<br />

Updates `python-dotenv` from 1.2.2 to 1.2.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/theskumar/python-dotenv/releases">python-dotenv's releases</a>.</em></p>
<blockquote>
<h2>v1.2.3</h2>
<h3>Fixed</h3>
<ul>
<li>Strip a leading UTF-8 BOM from <code>.env</code> file contents so the first variable is no longer silently lost when the file is saved with BOM (e.g. by some JetBrains IDEs on Windows) by [<a href="https://github.com/h1whelan"><code>@​h1whelan</code></a>] in <a href="">#640</a></li>
<li><code>set_key</code> now escapes backslashes, so values containing them (Windows paths, regular expressions) survive a write/read round-trip. Quoted values ending in an escaped backslash are no longer mis-parsed as an escaped quote, which used to swallow the following lines by [<a href="https://github.com/dchaudhari7177"><code>@​dchaudhari7177</code></a>] in <a href="">#680</a></li>
<li><code>dotenv run</code> now prints a friendly error instead of a traceback when no command is given by [<a href="https://github.com/bbc2"><code>@​bbc2</code></a>] in <a href="">#606</a></li>
<li>Cache the parsed result for empty <code>.env</code> files so repeated <code>dotenv_values</code>/<code>load_dotenv</code> calls no longer re-read the file by [<a href="https://github.com/ReinerBRO"><code>@​ReinerBRO</code></a>] in <a href="">#638</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/theskumar/python-dotenv/blob/main/CHANGELOG.md">python-dotenv's changelog</a>.</em></p>
<blockquote>
<h2>[1.2.3] - 2026-08-16</h2>
<h3>Fixed</h3>
<ul>
<li>Strip a leading UTF-8 BOM from <code>.env</code> file contents so the first variable is no longer silently lost when the file is saved with BOM (e.g. by some JetBrains IDEs on Windows) by [<a href="https://github.com/h1whelan"><code>@​h1whelan</code></a>] in <a href="">#640</a></li>
<li><code>set_key</code> now escapes backslashes, so values containing them (Windows paths, regular expressions) survive a write/read round-trip. Quoted values ending in an escaped backslash are no longer mis-parsed as an escaped quote, which used to swallow the following lines by [<a href="https://github.com/dchaudhari7177"><code>@​dchaudhari7177</code></a>] in <a href="">#680</a></li>
<li><code>dotenv run</code> now prints a friendly error instead of a traceback when no command is given by [<a href="https://github.com/bbc2"><code>@​bbc2</code></a>] in <a href="">#606</a></li>
<li>Cache the parsed result for empty <code>.env</code> files so repeated <code>dotenv_values</code>/<code>load_dotenv</code> calls no longer re-read the file by [<a href="https://github.com/ReinerBRO"><code>@​ReinerBRO</code></a>] in <a href="">#638</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>49515af</code></a> Bump version: 1.2.2 → 1.2.3</li>
<li><a href=""><code>8ac846f</code></a> chore: add release runbook (RELEASING.md) and make release target</li>
<li><a href=""><code>bb31c94</code></a> docs: add 1.2.3 release notes (<a href="">#606</a>, <a href="">#638</a>, <a href="">#680</a>)</li>
<li><a href=""><code>f7b18d9</code></a> fix: round-trip backslashes through set_key (<a href="">#680</a>)</li>
<li><a href=""><code>751f8c1</code></a> ci(deps): bump actions/checkout from 6.0.2 to 6.0.3 in the github-actions gro...</li>
<li><a href=""><code>f1937b6</code></a> chore(deps): update mkdocs-include-markdown-plugin requirement from &gt;=6.0.0 t...</li>
<li><a href=""><code>45b9372</code></a> chore(deps): update pytest requirement from &gt;=3.9 to &gt;=9.0.3 (<a href="">#653</a>)</li>
<li><a href=""><code>72896e9</code></a> docs: fix broken mkdocs link in CONTRIBUTING.md (<a href="">#636</a>)</li>
<li><a href=""><code>72754a1</code></a> ci(deps): bump peaceiris/actions-gh-pages from 4.0.0 to 4.1.0 in the github-a...</li>
<li><a href=""><code>078325e</code></a> ci(security): harden CI/CD supply chain with SHA pinning and least-privilege ...</li>
<li>Additional commits viewable in <a href="https://github.com/theskumar/python-dotenv/compare/v1.2.2...v1.2.3">compare view</a></li>
</ul>
</details>
<br />

Updates `pymdown-extensions` from 11.0.1 to 11.0.2
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/facelessuser/pymdown-extensions/releases">pymdown-extensions's releases</a>.</em></p>
<blockquote>
<h2>11.0.2</h2>
<ul>
<li><strong>FIX</strong>: InlineHilite: Improve performance of inline code matching.</li>
<li><strong>FIX</strong>: Keys: Fix regex pattern inefficiencies.</li>
<li><strong>FIX</strong>: Blocks.HTML: Fix backtracking in HTML extension.</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>b8996d7</code></a> Docs: Update JS deps</li>
<li><a href=""><code>3a190d9</code></a> Fix backtracking in HTML blocks extension</li>
<li><a href=""><code>819f2f8</code></a> Keys: Fix regex pattern inefficiencies.</li>
<li><a href=""><code>34fc8e2</code></a> Improve InlineHilite pattern parsing</li>
<li><a href=""><code>5dfef3f</code></a> Fix lint</li>
<li><a href=""><code>f263972</code></a> Update tests to match latest Pygments</li>
<li><a href=""><code>6d3688e</code></a> Make a note about symlinks and snippets</li>
<li>See full diff in <a href="https://github.com/facelessuser/pymdown-extensions/compare/11.0.1...11.0.2">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.3 to 0.16.4
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.4</h2>
<h2>Release Notes</h2>
<p>Released on 2026-08-20.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>flake8-use-pathlib</code>] Add autofix for <code>PTH116</code> (<a href="">#26460</a>)</li>
<li>[<code>refurb</code>] Restrict <code>delete-full-slice</code> to lists (<code>FURB131</code>) (<a href="">#27711</a>)</li>
<li>[<code>refurb</code>] Skip <code>FURB101</code> and <code>FURB103</code> when the <code>open</code> argument is a file descriptor (<a href="">#27643</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Fix <code>InvalidInstruction</code> on Windows CPUs that do not support <code>POPCNT</code> (<a href="">#27803</a>)</li>
<li>[<code>pyflakes</code>] Emit semantic syntax errors in string type definitions as <code>F722</code> (<a href="">#27835</a>)</li>
<li>[<code>pylint</code>] Allow <code>os._exit</code> imports in <code>import-private-name</code> (<code>PLC2701</code>) (<a href="">#27738</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[syntax-errors] Align mixed t-string/bytes error message with CPython 3.14 (<a href="">#27766</a>)</li>
<li>[<code>ruff</code>] Add <code>ctypes.LittleEndianStructure</code> and related types to existing exception (<code>RUF012</code>) (<a href="">#27753</a>)</li>
<li>[syntax-errors] Detect duplicate keyword arguments (<a href="">#17804</a>)</li>
<li>[syntax-errors] Detect parameters declared <code>nonlocal</code> (<a href="">#27628</a>)</li>
</ul>
<h3>Server</h3>
<ul>
<li>Offer display-only fixes and mark safe fixes preferred (<a href="">#27807</a>)</li>
<li>Support pull diagnostics for notebook cells (<a href="">#27779</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Add default indicator to rules table (<a href="">#27724</a>)</li>
<li>Fix broken link to Python docs (<a href="">#27757</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Fix s390x stacker assembly in release builds (<a href="">#27776</a>)</li>
<li>Guarantee minimum stack size when parsing a module, standalone expression, and suites (<a href="">#25464</a>)</li>
<li>Reduce configuration deserialization code size (<a href="">#27924</a>)</li>
<li>Check packed AST index bounds (<a href="">#27849</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/AbhinavMir"><code>@​AbhinavMir</code></a></li>
<li><a href="https://github.com/eduardorittner"><code>@​eduardorittner</code></a></li>
<li><a href="https://github.com/royb3"><code>@​royb3</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/carljm"><code>@​carljm</code></a></li>
<li><a href="https://github.com/rosstitmarsh"><code>@​rosstitmarsh</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.4</h2>
<p>Released on 2026-08-20.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>flake8-use-pathlib</code>] Add autofix for <code>PTH116</code> (<a href="">#26460</a>)</li>
<li>[<code>refurb</code>] Restrict <code>delete-full-slice</code> to lists (<code>FURB131</code>) (<a href="">#27711</a>)</li>
<li>[<code>refurb</code>] Skip <code>FURB101</code> and <code>FURB103</code> when the <code>open</code> argument is a file descriptor (<a href="">#27643</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Fix <code>InvalidInstruction</code> on Windows CPUs that do not support <code>POPCNT</code> (<a href="">#27803</a>)</li>
<li>[<code>pyflakes</code>] Emit semantic syntax errors in string type definitions as <code>F722</code> (<a href="">#27835</a>)</li>
<li>[<code>pylint</code>] Allow <code>os._exit</code> imports in <code>import-private-name</code> (<code>PLC2701</code>) (<a href="">#27738</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[syntax-errors] Align mixed t-string/bytes error message with CPython 3.14 (<a href="">#27766</a>)</li>
<li>[<code>ruff</code>] Add <code>ctypes.LittleEndianStructure</code> and related types to existing exception (<code>RUF012</code>) (<a href="">#27753</a>)</li>
<li>[syntax-errors] Detect duplicate keyword arguments (<a href="">#17804</a>)</li>
<li>[syntax-errors] Detect parameters declared <code>nonlocal</code> (<a href="">#27628</a>)</li>
</ul>
<h3>Server</h3>
<ul>
<li>Offer display-only fixes and mark safe fixes preferred (<a href="">#27807</a>)</li>
<li>Support pull diagnostics for notebook cells (<a href="">#27779</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Add default indicator to rules table (<a href="">#27724</a>)</li>
<li>Fix broken link to Python docs (<a href="">#27757</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Fix s390x stacker assembly in release builds (<a href="">#27776</a>)</li>
<li>Guarantee minimum stack size when parsing a module, standalone expression, and suites (<a href="">#25464</a>)</li>
<li>Reduce configuration deserialization code size (<a href="">#27924</a>)</li>
<li>Check packed AST index bounds (<a href="">#27849</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/AbhinavMir"><code>@​AbhinavMir</code></a></li>
<li><a href="https://github.com/eduardorittner"><code>@​eduardorittner</code></a></li>
<li><a href="https://github.com/royb3"><code>@​royb3</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/carljm"><code>@​carljm</code></a></li>
<li><a href="https://github.com/rosstitmarsh"><code>@​rosstitmarsh</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/zaniebot"><code>@​zaniebot</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>11c76bf</code></a> Bump 0.16.4 (<a href="">#27937</a>)</li>
<li><a href=""><code>d53c8c5</code></a> Isolate playground builds from deployment credentials (<a href="">#27839</a>)</li>
<li><a href=""><code>cab001e</code></a> Disable uv preview for releases and pre-commit hooks (<a href="">#27939</a>)</li>
<li><a href=""><code>f8d575f</code></a> [ty] Clarify writing guidance for human readers (<a href="">#27912</a>)</li>
<li><a href=""><code>ca45fae</code></a> Set <code>--preview</code> and <code>--default-index</code> for the <code>uv-lock</code> hook (<a href="">#27935</a>)</li>
<li><a href=""><code>4827bf7</code></a> Export <code>UV_DEFAULT_INDEX</code> in <code>release.sh</code> (<a href="">#27934</a>)</li>
<li><a href=""><code>d1087a4</code></a> [ty] Handle assignment expressions in string annotations (<a href="">#27921</a>)</li>
<li><a href=""><code>680cce4</code></a> [ty] Optimize inherited recursive protocol comparisons (<a href="">#27922</a>)</li>
<li><a href=""><code>974d3cb</code></a> Upgrade ecosystem-analyzer and mypy_primer to the latest upstream pins (<a href="">#27932</a>)</li>
<li><a href=""><code>b169b40</code></a> Install cargo tools locked (<a href="">#27929</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.3...0.16.4">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `7242facbefc2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.