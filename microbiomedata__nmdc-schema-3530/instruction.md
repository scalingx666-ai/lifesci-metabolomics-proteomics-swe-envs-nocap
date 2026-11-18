# Issue

**Title:** Bump the python-dependencies group with 5 updates

## Description

Bumps the python-dependencies group with 5 updates:

| Package | From | To |
| --- | --- | --- |
| linkml-runtime | `1.11.1` | `1.12.1` |
| [pymongo](https://github.com/mongodb/mongo-python-driver) | `4.18.2` | `4.18.3` |
| [pylint](https://github.com/pylint-dev/pylint) | `4.1.2` | `4.1.3` |
| [pymdown-extensions](https://github.com/facelessuser/pymdown-extensions) | `12.1` | `12.2` |
| [ruff](https://github.com/astral-sh/ruff) | `0.16.10` | `0.17.0` |

Updates `linkml-runtime` from 1.11.1 to 1.12.1

Updates `pymongo` from 4.18.2 to 4.18.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/releases">pymongo's releases</a>.</em></p>
<blockquote>
<h2>PyMongo 4.18.3</h2>
<p>Community notes: <a href="https://www.mongodb.com/community/forums/t/pymongo-4-18-3-released/344145">https://www.mongodb.com/community/forums/t/pymongo-4-18-3-released/344145</a></p>
<p><a href="https://www.cve.org/CVERecord?id=CVE-2026-106435">CVE-2026-106435</a></p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/blob/4.18.3/doc/changelog.rst">pymongo's changelog</a>.</em></p>
<blockquote>
<h2>Changes in Version 4.18.3 (2026/10/08)</h2>
<p>Version 4.18.3 is a bug fix release.</p>
<ul>
<li>Hardened BSON regex decoding against malformed documents (<code>PYTHON-6110</code>_).</li>
</ul>
<p>.. _PYTHON-6110: <a href="https://jira.mongodb.org/browse/PYTHON-6110">https://jira.mongodb.org/browse/PYTHON-6110</a></p>
<p>Issues Resolved
...............</p>
<p>See the <code>PyMongo 4.18.3 release notes in JIRA</code>_ for the list of resolved issues
in this release.</p>
<p>.. _PyMongo 4.18.3 release notes in JIRA: <a href="https://jira.mongodb.org/secure/ReleaseNote.jspa?projectId=10004&amp;version=52955">https://jira.mongodb.org/secure/ReleaseNote.jspa?projectId=10004&amp;version=52955</a></p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>5479af6</code></a> PYTHON-6155 Prep 4.18.3 release (<a href="">#3108</a>)</li>
<li><a href=""><code>bb8d4e1</code></a> PYTHON-6110 Bound Regex element scans to the remaining document bytes (<a href="">#3109</a>)</li>
<li><a href=""><code>98f444b</code></a> PYTHON-6140 [v4.18] [Build Failure] TestBSON.test_encode_size_limit MemoryErr...</li>
<li><a href=""><code>7376a3e</code></a> PYTHON-6104 [v4.18] Remove mod_wsgi testing from Evergreen (<a href="">#3091</a>)</li>
<li><a href=""><code>dac0e76</code></a> PYTHON-6083 [v4.18] Latest server binary downloads require private S3 (<a href="">#3080</a>)</li>
<li><a href=""><code>9ee37df</code></a> Update changelog to include CVEs (<a href="">#3067</a>)</li>
<li><a href=""><code>eda87d6</code></a> BUMP 4.18.3.dev0</li>
<li>See full diff in <a href="https://github.com/mongodb/mongo-python-driver/compare/4.18.2...4.18.3">compare view</a></li>
</ul>
</details>
<br />

Updates `pylint` from 4.1.2 to 4.1.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pylint-dev/pylint/releases">pylint's releases</a>.</em></p>
<blockquote>
<h2>v4.1.3</h2>
<h2>What's new in Pylint 4.1.3?</h2>
<p>Release date: 2026-10-11</p>
<h2>False Positives Fixed</h2>
<ul>
<li>
<p>Fixed a false positive for <code>attribute-defined-outside-init</code> when an
attribute is assigned inside the setter of an old-style, non-decorator
<code>property(fget, fset)</code> call. The decorator form (<code>@property</code> /
<code>@x.setter</code>) was already exempted by the fix for <a href="">#409</a>; the classic
call form was not.</p>
<p>Closes <a href="">#3325</a></p>
</li>
<li>
<p>Fix a false positive for <code>used-before-assignment</code> when a name bound by an earlier
target of the same assignment is used by a later target, as in <code>a = b[a] = 0</code>.</p>
<p>Closes <a href="">#5955</a></p>
</li>
<li>
<p>Fix a <code>no-member</code> false positive in a comprehension inside a branch that
cannot run, such as <code>if sys.platform == &quot;win32&quot;:</code> on Linux. Like the rest of
the branch, the comprehension is no longer checked for missing members.</p>
<p>Closes <a href="">#7240</a></p>
</li>
<li>
<p>Fix a false positive for <code>used-before-assignment</code> when a name bound by a tuple
or list target of a <code>with</code> item is used by a later item of the same <code>with</code> statement.</p>
<p>Closes <a href="">#7545</a></p>
</li>
<li>
<p>Fix false positives such as <code>not-callable</code>, <code>not-an-iterable</code>,
<code>unpacking-non-sequence</code> and <code>no-member</code> on the result of a function whose
body is only <code>...</code>, like <code>@overload</code> and <code>.pyi</code> stubs. Such calls were
inferred as returning <code>None</code>. This affected <code>sqlalchemy.func</code>,
<code>pydantic.Field</code>, and the <code>torch</code> functions wrapped by <code>_add_docstr</code>,
such as <code>torch.linalg.qr</code>.</p>
<p>Closes <a href="">#8138</a>
Closes <a href="">#9218</a>
Closes <a href="">#9354</a>
Closes <a href="">#10087</a></p>
</li>
<li>
<p>Fix a false positive for <code>protected-access</code> when a subclass of a subscripted
generic base, such as <code>class Child(Parent[T])</code>, accesses a protected member
through that base, such as <code>Parent._foo(self)</code>.</p>
<p>Closes <a href="">#8600</a></p>
</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>e75de10</code></a> Bump pylint to 4.1.3, update changelog (<a href="">#11637</a>)</li>
<li><a href=""><code>591f6e2</code></a> [Backport maintenance/4.1.x] Fix protected-access false positive through a su...</li>
<li><a href=""><code>a537920</code></a> [Backport maintenance/4.1.x] Ignore discard variable type redefinitions (<a href="">#11635</a>)</li>
<li><a href=""><code>4a8f61c</code></a> [Backport maintenance/4.1.x] Fix duplicate-code crash when min-similarity-lin...</li>
<li><a href=""><code>41fa1c4</code></a> [Backport maintenance/4.1.x] [pyreverse] Fix hang/RecursionError with --all-a...</li>
<li><a href=""><code>a05e2f3</code></a> [Backport maintenance/4.1.x] Fix <code>used-before-assignment</code> false positive for ...</li>
<li><a href=""><code>ea7996b</code></a> [Backport maintenance/4.1.x] Error when several output formats write to stdou...</li>
<li><a href=""><code>479c037</code></a> [Backport maintenance/4.1.x] Fix IndexError when Enum <strong>init</strong> has no argumen...</li>
<li><a href=""><code>e6aa780</code></a> [Backport maintenance/4.1.x] Fix unreachable false positive for raising gener...</li>
<li><a href=""><code>fc58d0b</code></a> [Backport maintenance/4.1.x] Fix pyreverse crash on classes with EmptyNode in...</li>
<li>Additional commits viewable in <a href="https://github.com/pylint-dev/pylint/compare/v4.1.2...v4.1.3">compare view</a></li>
</ul>
</details>
<br />

Updates `pymdown-extensions` from 12.1 to 12.2
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/facelessuser/pymdown-extensions/releases">pymdown-extensions's releases</a>.</em></p>
<blockquote>
<h2>12.2</h2>
<ul>
<li><strong>NEW</strong>: Add official support for Python 3.15.</li>
<li><strong>NEW</strong>: Tilde, Caret: For backwards compatibility, disable CommonMark punctuation rules by default. If subscript or
superscript is disabled in the respective extension, CommonMark rules will be honored again. A new <code>punctuation</code>
rule has been added to force CommonMark rules. When done, people will need to be aware of punctuation when subscript
or superscript is enabled and escape any that violates CommonMark rules.</li>
<li><strong>NEW</strong>: Highlight: Highlight now allows in the <code>auto_title_map</code> specifying the title as a simple string or a
dictionary containing the title and the title mode: either <code>text</code> or <code>html</code>, with <code>text</code> being the default. This
allows a title to be specified and treated as HTML when the mode is <code>html</code>.</li>
<li><strong>NEW</strong>: SuperFences: Add new <code>title_mode</code> option for Pygments fenced blocks that allows a user to specify a title
to be treated as HTML via <code>title_mode=&quot;html&quot;</code>.</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>a656909</code></a> Docs: Fix duplicate word</li>
<li><a href=""><code>0b90546</code></a> Revert &quot;Fix lint&quot;</li>
<li><a href=""><code>11fbe9f</code></a> Revert &quot;Drop Python 3.10 support&quot;</li>
<li><a href=""><code>3b5e585</code></a> Docs: Fix grammar</li>
<li><a href=""><code>91ec2a8</code></a> Docs: Fix default admonition/details styling</li>
<li><a href=""><code>5d7efe4</code></a> Docs: update js dependencies</li>
<li><a href=""><code>195228a</code></a> Fix lint</li>
<li><a href=""><code>ff07dc2</code></a> Drop Python 3.10 support</li>
<li><a href=""><code>848c502</code></a> Add title mode configuration to SuperFences and Highlight</li>
<li><a href=""><code>881c052</code></a> Tilde/Caret punctuation rule adjustments (<a href="">#2986</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/facelessuser/pymdown-extensions/compare/12.1...12.2">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.10 to 0.17.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.17.0</h2>
<h2>Release Notes</h2>
<p>Released on 2026-10-09.</p>
<p>The executables in our macOS and Windows release archives and <code>ruff</code> wheels are now code-signed. macOS executables are signed with an Apple Developer ID certificate and notarized by Apple. Windows executables have timestamped Authenticode signatures from Azure Artifact Signing. This enables verification of the release publisher and binary integrity, supports publisher-based allowlisting, and should reduce security warnings and antivirus false positives.</p>
<h3>Breaking changes</h3>
<ul>
<li>
<p>Update the default and latest Python versions for 3.15 (<a href="">#28792</a>)</p>
<p>Ruff now defaults to Python 3.11 instead of 3.10 when no Python version is configured through <a href="https://docs.astral.sh/ruff/settings/#target-version"><code>target-version</code></a> or <a href="https://docs.astral.sh/ruff/configuration/#inferring-the-python-version"><code>requires-python</code></a>. When checking for syntax errors without a configured Python version, Ruff now defaults to Python 3.15 instead of 3.14.</p>
</li>
<li>
<p>Update the default rule set (<a href="">#28786</a>)</p>
<p>Several of the <code>flake8-datetimez</code> rules (<a href="https://docs.astral.sh/ruff/rules/call-datetime-without-tzinfo/"><code>DTZ001</code></a>, <a href="https://docs.astral.sh/ruff/rules/call-datetime-now-without-tzinfo/"><code>DTZ005</code></a>, <a href="https://docs.astral.sh/ruff/rules/call-datetime-fromtimestamp/"><code>DTZ006</code></a>, <a href="https://docs.astral.sh/ruff/rules/call-datetime-strptime-without-zone/"><code>DTZ007</code></a>, <a href="https://docs.astral.sh/ruff/rules/call-date-today/"><code>DTZ011</code></a>, <a href="https://docs.astral.sh/ruff/rules/call-date-fromtimestamp/"><code>DTZ012</code></a>, and <a href="https://docs.astral.sh/ruff/rules/datetime-min-max/"><code>DTZ901</code></a>) are no longer enabled by default, while <a href="https://docs.astral.sh/ruff/rules/undefined-local-with-nested-import-star-usage/"><code>undefined-local-with-nested-import-star-usage</code></a> (<code>F406</code>), which corresponds to a syntax error, is now enabled by default.</p>
</li>
<li>
<p>Update Rust crate quick-junit to 0.8.0 (<a href="">#27295</a>)</p>
<p>JUnit output now uses a <code>skipped</code> attribute instead of <code>disabled</code> on <code>&lt;testsuite&gt;</code> elements and includes a <code>skipped</code> attribute on the root <code>&lt;testsuites&gt;</code> element.</p>
</li>
<li>
<p>[<code>flake8-import-conventions</code>] Add <code>datetime as dt</code> as a conventional alias (<code>ICN001</code>) (<a href="">#28790</a>)</p>
</li>
<li>
<p>Support Unicode dummy variable names (<a href="">#28722</a>)</p>
<p>The default <a href="https://docs.astral.sh/ruff/settings/#lint_dummy-variable-rgx"><code>lint.dummy-variable-rgx</code></a> now recognizes underscore-prefixed Unicode names, such as <code>_次</code>, as dummy variables.</p>
</li>
<li>
<p>Update to Unicode 17 (<a href="">#21229</a>, <a href="">#28784</a>)</p>
<p>Ruff now uses Unicode 17 data for identifier normalization and named character escapes (<code>&quot;\N{...}&quot;</code>).</p>
</li>
<li>
<p>Always show unsafe and display-only fixes in the CLI (<a href="">#27810</a>)</p>
<p>The default <code>full</code> output format now shows unsafe fixes and suggestions requiring manual review, regardless of the <a href="https://docs.astral.sh/ruff/settings/#unsafe-fixes"><code>unsafe-fixes</code></a> setting. Actually applying unsafe fixes still requires explicit opt-in.</p>
</li>
<li>
<p>Remove the Python dependency from conda-forge builds (<a href="">conda-forge/ruff-feedstock#361</a>)</p>
<p>The conda-forge build no longer depends on Python, now supports linux-riscv64, win-arm64, and linux-ppc64le platforms, and now includes shell completions. However, no longer depending on Python means that <code>python -m ruff</code> and <code>import ruff</code> will no longer work. Use <code>ruff</code> directly from <code>PATH</code> instead. PyPI installations and those from the standalone installer are unaffected.</p>
</li>
<li>
<p>Remove support for ruff-lsp (<a href="">#28750</a>)</p>
<p>Support for <code>ruff-lsp</code>, the legacy Python language server <a href="https://github.com/astral-sh/ruff/releases/tag/0.9.5">deprecated in Ruff v0.9.5</a>, has been removed. The Ruff VS Code extension now always uses the native language server; <code>ruff.nativeServer</code> is deprecated and ignored. See the <a href="https://docs.astral.sh/ruff/editors/migration/">migration guide</a>.</p>
</li>
</ul>
<h3>Stabilization</h3>
<p>The following rules have been stabilized and are no longer in preview:</p>
<ul>
<li><a href="https://docs.astral.sh/ruff/rules/lazy-import-mismatch"><code>lazy-import-mismatch</code></a> (<code>TID254</code>)</li>
<li><a href="https://docs.astral.sh/ruff/rules/lazy-import-immediately-resolved"><code>lazy-import-immediately-resolved</code></a> (<code>TID255</code>)</li>
<li><a href="https://docs.astral.sh/ruff/rules/os-path-commonprefix"><code>os-path-commonprefix</code></a> (<code>RUF071</code>)</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.17.0</h2>
<p>Released on 2026-10-09.</p>
<p>The executables in our macOS and Windows release archives and <code>ruff</code> wheels are now code-signed.
macOS executables are signed with an Apple Developer ID certificate and notarized by Apple. Windows
executables have timestamped Authenticode signatures from Azure Artifact Signing. This enables
verification of the release publisher and binary integrity, supports publisher-based allowlisting,
and should reduce security warnings and antivirus false positives.</p>
<h3>Breaking changes</h3>
<ul>
<li>
<p>Update the default and latest Python versions for 3.15 (<a href="">#28792</a>)</p>
<p>Ruff now defaults to Python 3.11 instead of 3.10 when no Python version is configured through
<a href="https://docs.astral.sh/ruff/settings/#target-version"><code>target-version</code></a> or
<a href="https://docs.astral.sh/ruff/configuration/#inferring-the-python-version"><code>requires-python</code></a>. When
checking for syntax errors without a configured Python version, Ruff now defaults to Python 3.15
instead of 3.14.</p>
</li>
<li>
<p>Update the default rule set (<a href="">#28786</a>)</p>
<p>Several of the <code>flake8-datetimez</code> rules
(<a href="https://docs.astral.sh/ruff/rules/call-datetime-without-tzinfo/"><code>DTZ001</code></a>,
<a href="https://docs.astral.sh/ruff/rules/call-datetime-now-without-tzinfo/"><code>DTZ005</code></a>,
<a href="https://docs.astral.sh/ruff/rules/call-datetime-fromtimestamp/"><code>DTZ006</code></a>,
<a href="https://docs.astral.sh/ruff/rules/call-datetime-strptime-without-zone/"><code>DTZ007</code></a>,
<a href="https://docs.astral.sh/ruff/rules/call-date-today/"><code>DTZ011</code></a>,
<a href="https://docs.astral.sh/ruff/rules/call-date-fromtimestamp/"><code>DTZ012</code></a>, and
<a href="https://docs.astral.sh/ruff/rules/datetime-min-max/"><code>DTZ901</code></a>) are no longer enabled by default,
while <a href="https://docs.astral.sh/ruff/rules/undefined-local-with-nested-import-star-usage/"><code>undefined-local-with-nested-import-star-usage</code></a>
(<code>F406</code>), which corresponds to a syntax error, is now enabled by default.</p>
</li>
<li>
<p>Update Rust crate quick-junit to 0.8.0 (<a href="">#27295</a>)</p>
<p>JUnit output now uses a <code>skipped</code> attribute instead of <code>disabled</code> on <code>&lt;testsuite&gt;</code> elements and
includes a <code>skipped</code> attribute on the root <code>&lt;testsuites&gt;</code> element.</p>
</li>
<li>
<p>[<code>flake8-import-conventions</code>] Add <code>datetime as dt</code> as a conventional alias (<code>ICN001</code>) (<a href="">#28790</a>)</p>
</li>
<li>
<p>Support Unicode dummy variable names (<a href="">#28722</a>)</p>
<p>The default <a href="https://docs.astral.sh/ruff/settings/#lint_dummy-variable-rgx"><code>lint.dummy-variable-rgx</code></a>
now recognizes underscore-prefixed Unicode names, such as <code>_次</code>, as dummy variables.</p>
</li>
<li>
<p>Update to Unicode 17 (<a href="">#21229</a>, <a href="">#28784</a>)</p>
<p>Ruff now uses Unicode 17 data for identifier normalization and named character escapes (<code>&quot;\N{...}&quot;</code>).</p>
</li>
<li>
<p>Always show unsafe and display-only fixes in the CLI (<a href="">#27810</a>)</p>
</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>5b27c1c</code></a> Bump version to 0.17.0 (<a href="">#29259</a>)</li>
<li><a href=""><code>8f362bf</code></a> Integrate vendored Unicode names into Ruff</li>
<li><a href=""><code>88a50d6</code></a> Revert upstream Unicode loose matching</li>
<li><a href=""><code>276832a</code></a> Revert upstream Unicode alias normalization</li>
<li><a href=""><code>26911ca</code></a> Vendor unicode_names2 from upstream</li>
<li><a href=""><code>27e3797</code></a> [<code>ruff</code>] Stabilize <code>os-path-commonprefix</code> (<code>RUF071</code>) (<a href="">#28764</a>)</li>
<li><a href=""><code>bbb52c1</code></a> [<code>flake8-tidy-imports</code>] Stabilize <code>lazy-import-immediately-resolved</code> (`TID255...</li>
<li><a href=""><code>5aa9cbd</code></a> [<code>flake8-tidy-imports</code>] Stabilize <code>lazy-import-mismatch</code> (<code>TID254</code>) (<a href="">#28760</a>)</li>
<li><a href=""><code>dba1bc8</code></a> [<code>flake8-import-conventions</code>] Add <code>datetime as dt</code> as a conventional alias (`...</li>
<li><a href=""><code>ef23c9c</code></a> Update default and latest Python versions for 3.15 (<a href="">#28792</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.10...0.17.0">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `4b2f8e6a4295`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.