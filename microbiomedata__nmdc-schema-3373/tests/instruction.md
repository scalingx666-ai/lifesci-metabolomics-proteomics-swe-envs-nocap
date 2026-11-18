# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [fastjsonschema](https://github.com/horejsek/python-fastjsonschema), [pylint](https://github.com/pylint-dev/pylint) and [ruff](https://github.com/astral-sh/ruff).

Updates `fastjsonschema` from 2.22.1 to 2.22.2
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/horejsek/python-fastjsonschema/blob/master/CHANGELOG.txt">fastjsonschema's changelog</a>.</em></p>
<blockquote>
<p>=== 2.22.2 (2026-08-15)</p>
<ul>
<li>Fixed wrong results of anyOf, oneOf, not, if/then/else, contains and propertyNames when <code>fast_fail</code> is off</li>
<li>Fixed collecting errors from subschemas behind <code>$ref</code> when <code>fast_fail</code> is off</li>
<li>Fixed escaping property name in boolean <code>dependencies</code> validation (prevents schema-controlled code injection)</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>b88fa37</code></a> v2.22.2</li>
<li><a href=""><code>a491757</code></a> Fixed escaping property name in boolean dependencies validation</li>
<li><a href=""><code>1224dc4</code></a> Merge pull request <a href="">#214</a> from gaoflow/fix-fast-fail-composition</li>
<li><a href=""><code>8332f11</code></a> Fixed compositions returning wrong results when fast_fail is off</li>
<li><a href=""><code>f8ea717</code></a> Merge pull request <a href="">#210</a> from Sanjays2402/fix/length-variable-scope-157</li>
<li><a href=""><code>c13e524</code></a> Merge pull request <a href="">#212</a> from Sanjays2402/fix/non-finite-float-defaults</li>
<li><a href=""><code>a4b963e</code></a> Generate non-finite float defaults as valid Python source</li>
<li><a href=""><code>a48364a</code></a> Fix UnboundLocalError from length variable defined in a sibling block</li>
<li>See full diff in <a href="https://github.com/horejsek/python-fastjsonschema/compare/v2.22.1...v2.22.2">compare view</a></li>
</ul>
</details>
<br />

Updates `pylint` from 4.0.6 to 4.0.7
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>c6768d3</code></a> Bump pylint to 4.0.7, update changelog (<a href="">#11246</a>)</li>
<li><a href=""><code>e96ce2b</code></a> Stop invalid-name from treating TypedDict instances as classes</li>
<li><a href=""><code>893294e</code></a> [Backport maintenance/4.0.x] Fix crash in comparison-with-callable on a proxi...</li>
<li><a href=""><code>8cd74d4</code></a> Fix a crash on calls unpacking dicts with non-string keys</li>
<li><a href=""><code>bc618ad</code></a> Fix too-many-lines being reported at another module's pragma line</li>
<li><a href=""><code>3e1ee47</code></a> [Backport maintenance/4.0.x] Fix <code>bad-string-format-type</code> false positives for...</li>
<li><a href=""><code>7ca8116</code></a> [Backport maintenance/4.0.x] Fix <code>useless-parent-delegation</code> false positive o...</li>
<li><a href=""><code>14275a1</code></a> [Backport maintenance/4.0.x] Fix <code>literal-comparison</code> suggestion corrupting i...</li>
<li><a href=""><code>a87eaa6</code></a> [Backport maintenance/4.0.x] Fix <code>nested-min-max</code> dropping arguments after th...</li>
<li><a href=""><code>bdd017f</code></a> [Backport maintenance/4.0.x] Fix <code>too-many-locals</code> counting PEP 695 type para...</li>
<li>Additional commits viewable in <a href="https://github.com/pylint-dev/pylint/compare/v4.0.6...v4.0.7">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.2 to 0.16.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.3</h2>
<h2>Release Notes</h2>
<p>Released on 2026-08-13.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>pylint</code>] Fix false negatives on negative numbers (<code>PLR6104</code>) (<a href="">#27251</a>)</li>
<li>[<code>pyupgrade</code>] Add rule to replace <code>while 1</code> with <code>while True</code> (<code>UP048</code>) (<a href="">#27190</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-bandit</code>] Also check keyword arguments (<code>S602</code>, <code>S603</code>, <code>S607</code>, <code>S609</code>) (<a href="">#27687</a>)</li>
<li>[<code>pylint</code>] Allow <code>continue</code> in <code>finally</code> on Python 3.8 (<a href="">#27626</a>)</li>
<li>[<code>pylint</code>] Fix <code>PLE1307</code> false positive with bools (<a href="">#27651</a>)</li>
<li>[<code>pylint</code>] Fix false positives and negatives with <code>%b</code> format character (<code>PLE1300</code>, <code>PLE1307</code>) (<a href="">#27560</a>)</li>
<li>[<code>pylint</code>] Improve handling of concatenated strings (<code>PLE1300</code>) (<a href="">#27659</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>numpy</code>] Make <code>np.chararray</code> autofix backwards-compatible (<code>NPY201</code>) (<a href="">#27527</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Enable PGO for Linux x86-64 Ruff releases (<a href="">#27570</a>)</li>
<li>Enable PGO for Linux ARM64 Ruff releases (<a href="">#27574</a>)</li>
<li>Enable PGO for Windows x86-64 Ruff releases (<a href="">#27573</a>)</li>
<li>Enable PGO for macOS ARM64 Ruff releases (<a href="">#27572</a>)</li>
<li>Reduce <code>Expr</code> size to 64 bytes (<a href="">#27591</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Hyperlink rule codes in <code>ruff check --statistics</code> output (<a href="">#27646</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>[<code>ruff</code>] Also suggest <code>asyncio.TaskGroup</code> (<code>RUF006</code>) (<a href="">#27461</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Use mimalloc v3 (<a href="">#27586</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/Andrej730"><code>@​Andrej730</code></a></li>
<li><a href="https://github.com/alonfaraj"><code>@​alonfaraj</code></a></li>
<li><a href="https://github.com/romero-deshaw"><code>@​romero-deshaw</code></a></li>
<li><a href="https://github.com/Avasam"><code>@​Avasam</code></a></li>
<li><a href="https://github.com/tjkuson"><code>@​tjkuson</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.3</h2>
<p>Released on 2026-08-13.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>pylint</code>] Fix false negatives on negative numbers (<code>PLR6104</code>) (<a href="">#27251</a>)</li>
<li>[<code>pyupgrade</code>] Add rule to replace <code>while 1</code> with <code>while True</code> (<code>UP048</code>) (<a href="">#27190</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-bandit</code>] Also check keyword arguments (<code>S602</code>, <code>S603</code>, <code>S607</code>, <code>S609</code>) (<a href="">#27687</a>)</li>
<li>[<code>pylint</code>] Allow <code>continue</code> in <code>finally</code> on Python 3.8 (<a href="">#27626</a>)</li>
<li>[<code>pylint</code>] Fix <code>PLE1307</code> false positive with bools (<a href="">#27651</a>)</li>
<li>[<code>pylint</code>] Fix false positives and negatives with <code>%b</code> format character (<code>PLE1300</code>, <code>PLE1307</code>) (<a href="">#27560</a>)</li>
<li>[<code>pylint</code>] Improve handling of concatenated strings (<code>PLE1300</code>) (<a href="">#27659</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>numpy</code>] Make <code>np.chararray</code> autofix backwards-compatible (<code>NPY201</code>) (<a href="">#27527</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Enable PGO for Linux x86-64 Ruff releases (<a href="">#27570</a>)</li>
<li>Enable PGO for Linux ARM64 Ruff releases (<a href="">#27574</a>)</li>
<li>Enable PGO for Windows x86-64 Ruff releases (<a href="">#27573</a>)</li>
<li>Enable PGO for macOS ARM64 Ruff releases (<a href="">#27572</a>)</li>
<li>Reduce <code>Expr</code> size to 64 bytes (<a href="">#27591</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Hyperlink rule codes in <code>ruff check --statistics</code> output (<a href="">#27646</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>[<code>ruff</code>] Also suggest <code>asyncio.TaskGroup</code> (<code>RUF006</code>) (<a href="">#27461</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Use mimalloc v3 (<a href="">#27586</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/Andrej730"><code>@​Andrej730</code></a></li>
<li><a href="https://github.com/alonfaraj"><code>@​alonfaraj</code></a></li>
<li><a href="https://github.com/romero-deshaw"><code>@​romero-deshaw</code></a></li>
<li><a href="https://github.com/Avasam"><code>@​Avasam</code></a></li>
<li><a href="https://github.com/tjkuson"><code>@​tjkuson</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/chirizxc"><code>@​chirizxc</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>b0e4702</code></a> Bump 0.16.3 (<a href="">#27723</a>)</li>
<li><a href=""><code>ecdd401</code></a> [ty] Separate script and uv modules from project metadata (<a href="">#27720</a>)</li>
<li><a href=""><code>1263524</code></a> [ty] Simplify display implementations with std::fmt::from_fn (<a href="">#27718</a>)</li>
<li><a href=""><code>59196ba</code></a> [ty] Unify polarity-aware relation construction (<a href="">#27707</a>)</li>
<li><a href=""><code>b8c5e73</code></a> [ty] Disable CodSpeed cycle estimation for instrumented benchmarks (<a href="">#27706</a>)</li>
<li><a href=""><code>2b0d210</code></a> [ty] Centralize matched argument relations (<a href="">#27705</a>)</li>
<li><a href=""><code>a9130f3</code></a> [<code>pyupgrade</code>] Add rule to replace <code>while 1</code> with <code>while True</code> (<code>while-one</code>, `...</li>
<li><a href=""><code>c64c7d6</code></a> [ty] Model try exception flow with operation checkpoints (<a href="">#27471</a>)</li>
<li><a href=""><code>9dea5ef</code></a> [ty] Avoid deriving sequents for typevars with concrete bounds (<a href="">#27587</a>)</li>
<li><a href=""><code>9798e88</code></a> [ty] Preserve enum exhaustiveness with custom <em>missing</em> methods (<a href="">#27700</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.2...0.16.3">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `9baec25a167e`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.