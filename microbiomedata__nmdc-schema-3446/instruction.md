# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [pymongo](https://github.com/mongodb/mongo-python-driver), [pylint](https://github.com/pylint-dev/pylint) and [ruff](https://github.com/astral-sh/ruff).

Updates `pymongo` from 4.18.1 to 4.18.2
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/releases">pymongo's releases</a>.</em></p>
<blockquote>
<h2>PyMongo 4.18.2</h2>
<p>Community notes: <a href="https://www.mongodb.com/community/forums/t/pymongo-4-18-2-released/343732">https://www.mongodb.com/community/forums/t/pymongo-4-18-2-released/343732</a></p>
<p><a href="https://www.cve.org/CVERecord?id=CVE-2026-96749">CVE-2026-96749</a>
<a href="https://www.cve.org/CVERecord?id=CVE-2026-96748">CVE-2026-96748</a>
<a href="https://www.cve.org/CVERecord?id=CVE-2026-96747">CVE-2026-96747</a></p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/blob/main/doc/changelog.rst">pymongo's changelog</a>.</em></p>
<blockquote>
<h2>Changes in Version 4.18.2 (2026/09/24)</h2>
<p>Version 4.18.2 is a bug fix release.</p>
<ul>
<li>Hardened the bson buffer size guard against signed integer overflow. (<code>CVE-2026-96749</code>_).</li>
<li>Fixed connection string parsing to percent-decode each host individually. (<code>CVE-2026-96748</code>_).</li>
<li>Client-side field level encryption now rejects a KMS endpoint ending in <code>.sock</code>. (<code>CVE-2026-96747</code>_).</li>
</ul>
<p>.. _CVE-2026-96749: <a href="https://www.cve.org/CVERecord?id=CVE-2026-96749">https://www.cve.org/CVERecord?id=CVE-2026-96749</a>
.. _CVE-2026-96748: <a href="https://www.cve.org/CVERecord?id=CVE-2026-96748">https://www.cve.org/CVERecord?id=CVE-2026-96748</a>
.. _CVE-2026-96747: <a href="https://www.cve.org/CVERecord?id=CVE-2026-96747">https://www.cve.org/CVERecord?id=CVE-2026-96747</a></p>
<p>Issues Resolved
...............</p>
<p>See the <code>PyMongo 4.18.2 release notes in JIRA</code>_ for the list of resolved issues
in this release.</p>
<p>.. _PyMongo 4.18.2 release notes in JIRA: <a href="https://jira.mongodb.org/secure/ReleaseNote.jspa?projectId=10004&amp;version=52896">https://jira.mongodb.org/secure/ReleaseNote.jspa?projectId=10004&amp;version=52896</a></p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>640dd23</code></a> Prep 4.18.2 release (<a href="">#3066</a>)</li>
<li><a href=""><code>6a0ec65</code></a> Update changelog for CVE-2026-88029 reference (<a href="">#3049</a>)</li>
<li><a href=""><code>44be553</code></a> BUMP 4.18.2.dev0</li>
<li>See full diff in <a href="https://github.com/mongodb/mongo-python-driver/compare/4.18.1...4.18.2">compare view</a></li>
</ul>
</details>
<br />

Updates `pylint` from 4.0.8 to 4.1.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pylint-dev/pylint/releases">pylint's releases</a>.</em></p>
<blockquote>
<h2>v4.1.1</h2>
<h2>What's new in Pylint 4.1.1?</h2>
<p>Release date: 2026-09-29</p>
<h2>Other Changes</h2>
<ul>
<li>
<p>Pylint 4.1.0 could not be uploaded to PyPI, because it required an unreleased
version of <code>dill</code> on Python 3.15, and PyPI refuses such a dependency. 4.1.1 is
the first 4.1 release available on PyPI, see the 4.1.0 changes below.</p>
<p>Refs <a href="">#11495</a></p>
</li>
</ul>
<h2>v4.1.0</h2>
<h2>What's new in Pylint 4.1.0?</h2>
<p>Release date: 2026-09-29</p>
<p>Startup is about 25% faster thanks to lazy imports. The import checker caches
its isort configuration, which makes pylint about 17% faster on ansible.
Finding the files to lint with <code>--recursive=y</code> no longer walks ignored
directories such as <code>.venv</code> or <code>node_modules</code>, which took seconds on large
trees. The duplicate-code checker and <code>symilar</code> also received optimizations
that result in considerable performance improvements and memory use reduction
on larger codebases. For example, pandas analysis went from 20 min to 55 s and
pylint does not get OOM-killed when analyzing cpython anymore.</p>
<p>Python 3.15 support progresses: the unpacking in comprehensions added by
PEP 798 no longer raises false positives, and the standard library
deprecations of Python 3.15 are followed.</p>
<p>For CI, there is a new built-in <code>junit</code> output format
(<code>--output-format=junit</code>), the <code>NO_COLOR</code> and <code>FORCE_COLOR</code> environment
variables are respected, and the files to lint can now be set with the
<code>files</code> option in the configuration file.</p>
<p>New checks: <code>looping-through-iterator</code>, <code>impossible-comparison</code>,
<code>chained-comparison-all-equal</code> and
<code>using-comprehension-unpacking-in-unsupported-version</code>.</p>
<p>Running with <code>--jobs</code> no longer duplicates the messages of extensions or
ignores extensions enabled in the configuration.</p>
<p>Plugin authors: the <code>confidence</code> parameter can no longer be <code>None</code>, except
in <code>is_message_enabled</code>, and the <code>MSG_STATE_*</code> constants are deprecated in
favor of the <code>MessageDisableReason</code> enum.</p>
<p>The required <code>astroid</code> version is now 4.3.2. See the <a href="https://pylint.readthedocs.io/projects/astroid/en/latest/changelog.html#what-s-new-in-astroid-4-3-2%3E">astroid changelog</a> for additional fixes, features, and performance improvements applicable to pylint.</p>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>8c6daca</code></a> Bump pylint to 4.1.1, update changelog (<a href="">#11499</a>)</li>
<li><a href=""><code>bdb17b3</code></a> [Backport maintenance/4.1.x] Only pin the unreleased dill for the tests (<a href="">#11498</a>)</li>
<li><a href=""><code>92bb7ba</code></a> Bump pylint to 4.1.0, update changelog</li>
<li><a href=""><code>9144956</code></a> Fix a crash in import-private-name on attribute access rooted at a non-Name n...</li>
<li><a href=""><code>68366cb</code></a> Fix false positive for <code>unnecessary-lambda</code> when variable is reassigned or de...</li>
<li><a href=""><code>c741677</code></a> [pre-commit.ci] pre-commit autoupdate (<a href="">#11488</a>)</li>
<li><a href=""><code>a9ebdf6</code></a> Add regression test for unsubscriptable-object FP on <strong>class_getitem</strong> (<a href="">#11487</a>)</li>
<li><a href=""><code>b877d3b</code></a> Do not flag ungrouped imports inside OS platform guards (<a href="">#11217</a>)</li>
<li><a href=""><code>87351be</code></a> Update OSS-Fuzz docs for Python 3.14 (<a href="">#11485</a>)</li>
<li><a href=""><code>4f263c1</code></a> Fix access checks through called methods (<a href="">#11456</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/pylint-dev/pylint/compare/v4.0.8...v4.1.1">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.8 to 0.16.9
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.9</h2>
<h2>Release Notes</h2>
<p>Released on 2026-09-24.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>ruff</code>] Avoid false positives for overloaded division (<code>RUF069</code>) (<a href="">#28309</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-bugbear</code>] Avoid false positives for calls with keyword arguments (<code>B009</code>, <code>B010</code>, <code>B043</code>) (<a href="">#28776</a>)</li>
<li>[<code>flake8-tidy-imports</code>] Allow lazy imports to be used in deferred annotations (<code>TID255</code>) (<a href="">#28767</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Update LibCST-based fixes for Python 3.15 (<a href="">#28616</a>)</li>
<li>[<code>flake8-pyi</code>] Mention stubs in the diagnostic message (<code>PYI002</code>) (<a href="">#28542</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Fix horizontal overflow on the rules documentation page (<a href="">#28699</a>)</li>
<li>Update rules table with category information (<a href="">#28651</a>)</li>
<li>[<code>flake8-annotations</code>] Clarify that <code>ANN401</code> checks return types in addition to arguments (<a href="">#28334</a>)</li>
<li>[<code>flake8-bugbear</code>] Document type-checker interaction (<code>B010</code>) (<a href="">#28509</a>)</li>
<li>[<code>flake8-comprehensions</code>] Document <code>map</code>/generator exception behavior (<code>C417</code>) (<a href="">#27794</a>)</li>
<li>[<code>ruff</code>] Mention related isort settings (<code>RUF022</code>) (<a href="">#28719</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/qinpei-dev"><code>@​qinpei-dev</code></a></li>
<li><a href="https://github.com/sanjayrohith"><code>@​sanjayrohith</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/webdevsamran"><code>@​webdevsamran</code></a></li>
<li><a href="https://github.com/zaniebot"><code>@​zaniebot</code></a></li>
<li><a href="https://github.com/ewdurbin"><code>@​ewdurbin</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/spaceone"><code>@​spaceone</code></a></li>
<li><a href="https://github.com/IbrahimKhan12"><code>@​IbrahimKhan12</code></a></li>
<li><a href="https://github.com/devtechedge"><code>@​devtechedge</code></a></li>
<li><a href="https://github.com/GruffElixir"><code>@​GruffElixir</code></a></li>
</ul>
<h2>Install ruff 0.16.9</h2>
<h3>Install prebuilt binaries via shell script</h3>
<pre lang="sh"><code>curl --proto '=https' --tlsv1.2 -LsSf https://releases.astral.sh/github/ruff/releases/download/0.16.9/ruff-installer.sh | sh
</code></pre>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.9</h2>
<p>Released on 2026-09-24.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>ruff</code>] Avoid false positives for overloaded division (<code>RUF069</code>) (<a href="">#28309</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-bugbear</code>] Avoid false positives for calls with keyword arguments (<code>B009</code>, <code>B010</code>, <code>B043</code>) (<a href="">#28776</a>)</li>
<li>[<code>flake8-tidy-imports</code>] Allow lazy imports to be used in deferred annotations (<code>TID255</code>) (<a href="">#28767</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Update LibCST-based fixes for Python 3.15 (<a href="">#28616</a>)</li>
<li>[<code>flake8-pyi</code>] Mention stubs in the diagnostic message (<code>PYI002</code>) (<a href="">#28542</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Fix horizontal overflow on the rules documentation page (<a href="">#28699</a>)</li>
<li>Update rules table with category information (<a href="">#28651</a>)</li>
<li>[<code>flake8-annotations</code>] Clarify that <code>ANN401</code> checks return types in addition to arguments (<a href="">#28334</a>)</li>
<li>[<code>flake8-bugbear</code>] Document type-checker interaction (<code>B010</code>) (<a href="">#28509</a>)</li>
<li>[<code>flake8-comprehensions</code>] Document <code>map</code>/generator exception behavior (<code>C417</code>) (<a href="">#27794</a>)</li>
<li>[<code>ruff</code>] Mention related isort settings (<code>RUF022</code>) (<a href="">#28719</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/qinpei-dev"><code>@​qinpei-dev</code></a></li>
<li><a href="https://github.com/sanjayrohith"><code>@​sanjayrohith</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/webdevsamran"><code>@​webdevsamran</code></a></li>
<li><a href="https://github.com/zaniebot"><code>@​zaniebot</code></a></li>
<li><a href="https://github.com/ewdurbin"><code>@​ewdurbin</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/spaceone"><code>@​spaceone</code></a></li>
<li><a href="https://github.com/IbrahimKhan12"><code>@​IbrahimKhan12</code></a></li>
<li><a href="https://github.com/devtechedge"><code>@​devtechedge</code></a></li>
<li><a href="https://github.com/GruffElixir"><code>@​GruffElixir</code></a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>0be08a2</code></a> Bump version to 0.16.9 (<a href="">#28882</a>)</li>
<li><a href=""><code>b4920b7</code></a> Rename <code>ruff_cli</code> to <code>ruff_command_line</code> (<a href="">#28881</a>)</li>
<li><a href=""><code>47c751b</code></a> Update dependency astral-sh/uv to v0.12.18 (<a href="">#28880</a>)</li>
<li><a href=""><code>8c244e5</code></a> [<code>flake8-comprehensions</code>] Document <code>map</code>/generator exception behavior (<code>C417</code>...</li>
<li><a href=""><code>5edf5a1</code></a> Use <code>target</code> form in <code>rooster.version_files</code> (<a href="">#28876</a>)</li>
<li><a href=""><code>915bb2b</code></a> [ty] Prefer existing @ paths over response files in Ruff and ty (<a href="">#28877</a>)</li>
<li><a href=""><code>4710e1a</code></a> ci(github): update version number in placeholder of issue template (<a href="">#28871</a>)</li>
<li><a href=""><code>eedfc62</code></a> [ty] Propagate outer type context through cast calls (<a href="">#28855</a>)</li>
<li><a href=""><code>ceaa6a0</code></a> [ty] Contain rendered code within Markdown fences (<a href="">#28869</a>)</li>
<li><a href=""><code>dba0f30</code></a> authorize ruff-pre-commit dispatch via OIDC (<a href="">#28867</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.8...0.16.9">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `6fea28e893a8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.