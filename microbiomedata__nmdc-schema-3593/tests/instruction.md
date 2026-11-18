# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [mypy](https://github.com/python/mypy), [pytest](https://github.com/pytest-dev/pytest) and [ruff](https://github.com/astral-sh/ruff).

Updates `mypy` from 2.4.0 to 2.4.1
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/python/mypy/blob/master/CHANGELOG.md">mypy's changelog</a>.</em></p>
<blockquote>
<h3>Mypy 2.4.1</h3>
<ul>
<li>Process overloads as a whole in two-phase type checking (Ivan Levkivskyi, PR <a href="">22231</a>)</li>
<li>Skip recursive setup for frame-private nested functions in mypyc (Piotr Sawicki, PR <a href="">22187</a>)</li>
</ul>
<h3>Acknowledgements</h3>
<p>Thanks to all mypy contributors who contributed to this release:</p>
<ul>
<li>A5rocks</li>
<li>Adam Dangoor</li>
<li>Alex Waygood</li>
<li>Ali Hamdan</li>
<li>Brian Helba</li>
<li>Chad Dombrova</li>
<li>David Foster</li>
<li>dnwpark</li>
<li>Edgar Ramírez Mondragón</li>
<li>Giorgos Michas</li>
<li>Ivan Levkivskyi</li>
<li>Jelle Zijlstra</li>
<li>Jukka Lehtosalo</li>
<li>Marc Mueller</li>
<li>Michael R. Crusoe</li>
<li>NIYONSHUTI Emmanuel</li>
<li>Piotr Sawicki</li>
<li>Shantanu</li>
<li>themylogin</li>
<li>Vaggelis Danias</li>
<li>Willy Bruns</li>
</ul>
<p>I'd also like to thank my employer, Dropbox, for supporting mypy development.</p>
<h2>Mypy 2.3</h2>
<p>We've just uploaded mypy 2.3.0 to the Python Package Index (<a href="https://pypi.org/project/mypy/">PyPI</a>).
Mypy is a static type checker for Python. This release includes new features, performance
improvements and bug fixes. You can install it as follows:</p>
<pre><code>python3 -m pip install -U mypy
</code></pre>
<p>You can read the full documentation for this release on <a href="http://mypy.readthedocs.io">Read the Docs</a>.</p>
<h3>The Upcoming Switch to the New Native Parser</h3>
<p>We are planning to enable the new native parser (<code>--native-parser</code>) by
default soon. We recommend that you test the native parser in your projects and report
any issues in the <a href="https://github.com/python/mypy/issues">mypy issue tracker</a>.</p>
<h3>Mypyc Free-threading Memory Safety</h3>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>ad02a35</code></a> Skip test for 2.4.1</li>
<li><a href=""><code>cad7794</code></a> Finalize version to 2.4.1</li>
<li><a href=""><code>d9cbcbc</code></a> Add changelog for Mypy 2.4.1 (<a href="">#22310</a>)</li>
<li><a href=""><code>2860baa</code></a> Process overloads as a whole in two-phase type-checking (<a href="">#22231</a>)</li>
<li><a href=""><code>9b3e307</code></a> [mypyc] Skip recursive setup for frame-private nested functions (<a href="">#22187</a>)</li>
<li><a href=""><code>10ad5f6</code></a> Bump ast-serialize to 0.12.1 (<a href="">#22093</a>)</li>
<li><a href=""><code>350052f</code></a> Bump ast-serialize to 0.12.0 (<a href="">#22087</a>)</li>
<li><a href=""><code>f7d08cf</code></a> Bump version to 2.4.1+dev</li>
<li>See full diff in <a href="https://github.com/python/mypy/compare/v2.4.0...v2.4.1">compare view</a></li>
</ul>
</details>
<br />

Updates `pytest` from 9.1.1 to 9.2.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pytest-dev/pytest/releases">pytest's releases</a>.</em></p>
<blockquote>
<h2>9.2.0</h2>
<h1>pytest 9.2.0 (2026-10-27)</h1>
<h2>Removals and backward incompatible breaking changes</h2>
<ul>
<li>
<p><a href="">#14716</a>: <code>-c</code> now raises a usage error for a path that does not exist, is a directory, or is in a format pytest has no loader for. Such paths were previously either ignored or reported as an unhandled <code>FileNotFoundError</code>.</p>
</li>
<li>
<p><a href="">#8593</a>: The <code>indirect</code>, <code>ids</code> and <code>scope</code> arguments of <code>Metafunc.parametrize() &lt;pytest.Metafunc.parametrize&gt;</code> -- and therefore of <code>@pytest.mark.parametrize &lt;pytest.mark.parametrize ref&gt;</code> -- are now keyword-only.</p>
<p>Passing them positionally was a common source of confusing errors, e.g. <code>parametrize(&quot;arg1&quot;, &quot;arg2&quot;, [(1, 2)])</code> made the argvalues land in <code>indirect</code> and failed with <code>indirect fixture '(1, 2)' doesn't exist</code>; such mistakes now fail with an understandable <code>TypeError</code>. The type annotations have always declared these arguments as keyword-only.</p>
</li>
<li>
<p><a href="">#993</a>: Plugin import failures at startup are now reported and classified instead of escaping as a raw traceback with the accidental exit code <code>1</code>:</p>
<ul>
<li>a plugin that cannot be found -- via <code>-p</code>, <code>pytest_plugins</code> or <code>PYTEST_PLUGINS</code> -- exits with <code>pytest.ExitCode</code> <code>USAGE_ERROR</code> (<code>4</code>), like a <code>conftest.py</code> that fails to import;</li>
<li>a plugin that is found but raises while importing -- including a broken <code>pytest11</code> entry point or a missing plugin dependency -- exits with <code>pytest.ExitCode</code> <code>INTERNAL_ERROR</code> (<code>3</code>), with the traceback preserved.</li>
</ul>
<p><code>pytest.main</code> now returns these codes instead of raising <code>ImportError</code>. Also fixed an <code>IndexError</code> from pytest's own internals when the plugin raised an exception with no arguments.</p>
</li>
</ul>
<h2>Deprecations (removal in next major release)</h2>
<ul>
<li>
<p><a href="">#14742</a>: The private <code>_pytest.python.CallSpec2</code> name has been renamed to <code>CallSpec</code>.
The old <code>CallSpec2</code> alias remains available for now and will be removed in pytest 10 or 11.</p>
</li>
<li>
<p><a href="">#14755</a>: Schedule <em>yield_fixture</em> decorator for removal in pytest 10 or 11.</p>
</li>
<li>
<p><a href="">#14774</a>: Similarly to the deprecation of class-scoped fixtures defined as instance methods in pytest 9.1,
<em>all</em> higher-scoped fixtures (<code>module</code>, <code>package</code>, and <code>session</code>) defined
as instance methods are now deprecated.</p>
<p>They suffer from the same issue the original deprecation only fixed for
class-scoped fixtures, see <code>10819</code> and <code>14011</code>.</p>
</li>
<li>
<p><a href="">#14808</a>: Passing a non-string value to a <code>string</code>-typed ini option now emits a <code>pytest.PytestRemovedIn10Warning</code>. This affects <code>[tool.pytest.ini_options]</code> in <code>pyproject.toml</code>. In pytest 10 this will raise a <code>TypeError</code>, matching the behavior of the corresponding TOML config path.</p>
</li>
<li>
<p><a href="">#7323</a>: Passing <code>bytes</code> to <code>TerminalReporter.write_line()</code> is now deprecated, pass a <code>str</code> instead.</p>
</li>
</ul>
<h2>New features</h2>
<ul>
<li><a href="">#14743</a>: <!-- raw HTML omitted -->Full diff:<!-- raw HTML omitted --> now contains a legend explaining the <!-- raw HTML omitted -->+<!-- raw HTML omitted --> &amp; <!-- raw HTML omitted -->-<!-- raw HTML omitted --> symbols in diff output.</li>
<li><a href="">#2781</a>: When <code>strict_markers</code> is enabled, marker names used in <code>-m</code> expressions are now validated against registered markers.</li>
<li><a href="">#6881</a>: Added the <code>parametrize_long_str_id_strategy</code> configuration option to control how long <code>str</code>/<code>bytes</code> parameter values are handled in auto-generated test IDs. Explicit IDs set via <code>ids=[...]</code> or <code>pytest.param(..., id=...)</code> are not affected. Available strategies: <code>short</code> (default, values over 100 chars fall back to <code>argname+index</code>), <code>sha256</code> (SHA-256 hex digest), <code>legacy</code> (keep full value), and <code>disallow</code> (error requesting explicit IDs).</li>
</ul>
<h2>Improvements in existing functionality</h2>
<ul>
<li><a href="">#10745</a>: A <code>RecursionError</code> whose recursion origin cannot be located now shows only the
first and last 10 stack frames, matching what pytest already did when locating
the origin failed outright. Previously the full traceback -- often around a
thousand near-identical frames -- was rendered, which was both slow and
unreadable. Pass <code>--full-trace</code> to see every frame.</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>ae1d0ff</code></a> Prepare release version 9.2.0</li>
<li><a href=""><code>143ce31</code></a> pre-commit: exclude codespell on generated release announcements</li>
<li><a href=""><code>532dc5f</code></a> tox: add attrs dependency to regen, needed in reportingdemo.rst</li>
<li><a href=""><code>a7b2446</code></a> Merge pull request <a href="">#15245</a> from pytest-dev/claude/project-thread-9jcf91</li>
<li><a href=""><code>679d09c</code></a> [pre-commit.ci] pre-commit autoupdate (<a href="">#15266</a>)</li>
<li><a href=""><code>41d12cd</code></a> docs: clarify typing for yield fixtures</li>
<li><a href=""><code>b9022ba</code></a> Merge pull request <a href="">#15182</a> from 1871698/docs/improve-getting-started-description</li>
<li><a href=""><code>16f87a7</code></a> docs: improve getting-started.rst test execution description</li>
<li><a href=""><code>082ed70</code></a> Merge pull request <a href="">#15255</a> from pytest-dev/claude/project-thread-eoi3d6</li>
<li><a href=""><code>ae37a01</code></a> Merge pull request <a href="">#15227</a> from pytest-dev/claude/project-thread-4etye4</li>
<li>Additional commits viewable in <a href="https://github.com/pytest-dev/pytest/compare/9.1.1...9.2.0">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.17.2 to 0.17.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.17.3</h2>
<h2>Release Notes</h2>
<p>Released on 2026-10-26.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>suspicious</code>] Add <code>shared-clock-mock</code> (<a href="">#29074</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>pyupgrade</code>] Avoid incorrect conversions to f-strings (<code>UP032</code>) (<a href="">#25485</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Buffer stdout in <code>ruff format</code> (<a href="">#29631</a>)</li>
<li>Specialize ASCII identifier lexing (<a href="">#29503</a>)</li>
<li>Speed up identifier and keyword lexing (<a href="">#29463</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>[<code>flake8-bandit</code>] Describe what the rule actually checks for <code>httpx</code> (<code>S113</code>) (<a href="">#27936</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/itsvedantkumar"><code>@​itsvedantkumar</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/anishgirianish"><code>@​anishgirianish</code></a></li>
</ul>
<h2>Install ruff 0.17.3</h2>
<h3>Install prebuilt binaries via shell script</h3>
<pre lang="sh"><code>curl --proto '=https' --tlsv1.2 -LsSf https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-installer.sh | sh
</code></pre>
<h3>Install prebuilt binaries via powershell script</h3>
<pre lang="sh"><code>powershell -ExecutionPolicy Bypass -c &quot;irm https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-installer.ps1 | iex&quot;
</code></pre>
<h2>Download ruff 0.17.3</h2>
<table>
<thead>
<tr>
<th>File</th>
<th>Platform</th>
<th>Checksum</th>
</tr>
</thead>
<tbody>
<tr>
<td><a href="https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-aarch64-apple-darwin.tar.gz">ruff-aarch64-apple-darwin.tar.gz</a></td>
<td>Apple Silicon macOS</td>
<td><a href="https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-aarch64-apple-darwin.tar.gz.sha256">checksum</a></td>
</tr>
<tr>
<td><a href="https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-x86_64-apple-darwin.tar.gz">ruff-x86_64-apple-darwin.tar.gz</a></td>
<td>Intel macOS</td>
<td><a href="https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-x86_64-apple-darwin.tar.gz.sha256">checksum</a></td>
</tr>
<tr>
<td><a href="https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-aarch64-pc-windows-msvc.zip">ruff-aarch64-pc-windows-msvc.zip</a></td>
<td>ARM64 Windows</td>
<td><a href="https://releases.astral.sh/github/ruff/releases/download/0.17.3/ruff-aarch64-pc-windows-msvc.zip.sha256">checksum</a></td>
</tr>
</tbody>
</table>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.17.3</h2>
<p>Released on 2026-10-26.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>suspicious</code>] Add <code>shared-clock-mock</code> (<a href="">#29074</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>pyupgrade</code>] Avoid incorrect conversions to f-strings (<code>UP032</code>) (<a href="">#25485</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Buffer stdout in <code>ruff format</code> (<a href="">#29631</a>)</li>
<li>Specialize ASCII identifier lexing (<a href="">#29503</a>)</li>
<li>Speed up identifier and keyword lexing (<a href="">#29463</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>[<code>flake8-bandit</code>] Describe what the rule actually checks for <code>httpx</code> (<code>S113</code>) (<a href="">#27936</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/itsvedantkumar"><code>@​itsvedantkumar</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/anishgirianish"><code>@​anishgirianish</code></a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>ba65abf</code></a> Bump version to 0.17.3 (<a href="">#29745</a>)</li>
<li><a href=""><code>fb2f921</code></a> [ty] Fix narrowing of strings and integers compared with enum members (<a href="">#29743</a>)</li>
<li><a href=""><code>d181287</code></a> [ty] Index nominal union alternatives (<a href="">#29196</a>)</li>
<li><a href=""><code>07872ad</code></a> [ty] Preserve string literals in comparisons with <code>LiteralString</code> (<a href="">#29741</a>)</li>
<li><a href=""><code>95888b2</code></a> [ty] Preserve narrowing after guarded match subject captures (<a href="">#29558</a>)</li>
<li><a href=""><code>3c8166b</code></a> [ty] Fix hang when negating recursive unions of instance types (<a href="">#29652</a>)</li>
<li><a href=""><code>3fd20e0</code></a> [ty] Preserve generic callback specializations during return refinement (<a href="">#29667</a>)</li>
<li><a href=""><code>2f0a29e</code></a> [ty] Record predicate truthiness alongside expression inference (<a href="">#29706</a>)</li>
<li><a href=""><code>60f104a</code></a> [ty] Honor <a href="https://github.com/override"><code>@​override</code></a> on overload implementations in stubs (<a href="">#29470</a>)</li>
<li><a href=""><code>207ec3a</code></a> [ty] Add diagnostic baseline support (<a href="">#27636</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.17.2...0.17.3">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a7f2dfaec37c`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.