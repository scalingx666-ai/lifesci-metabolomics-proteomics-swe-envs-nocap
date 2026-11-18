# Issue

**Title:** Bump the python-dependencies group with 4 updates

## Description

Bumps the python-dependencies group with 4 updates: [curies](https://github.com/biopragmatics/curies), [pylint](https://github.com/pylint-dev/pylint), [pytest](https://github.com/pytest-dev/pytest) and [ruff](https://github.com/astral-sh/ruff).

Updates `curies` from 0.13.11 to 0.13.13
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>e629eec</code></a> Bump version: 0.13.13-dev → 0.13.13</li>
<li><a href=""><code>5e0b0d2</code></a> Add cross-species vocabulary (<a href="">#229</a>)</li>
<li><a href=""><code>8aa1302</code></a> Add missing exports</li>
<li><a href=""><code>6e337dc</code></a> Bump version: 0.13.12 → 0.13.13-dev</li>
<li><a href=""><code>1925805</code></a> Bump version: 0.13.12-dev → 0.13.12</li>
<li><a href=""><code>3847873</code></a> Add prefix check function</li>
<li><a href=""><code>0ab8bcd</code></a> Add additional typing extensions</li>
<li><a href=""><code>2732ecb</code></a> Update typing of inversions dictionary</li>
<li><a href=""><code>3b1255d</code></a> Extend semantic mapping predicates list</li>
<li><a href=""><code>a42c59b</code></a> Add pav:authoredBy to vocabulary</li>
<li>Additional commits viewable in <a href="https://github.com/biopragmatics/curies/compare/v0.13.11...v0.13.13">compare view</a></li>
</ul>
</details>
<br />

Updates `pylint` from 4.0.5 to 4.0.6
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>8a39635</code></a> Bump pylint to 4.0.6, update changelog (<a href="">#11105</a>)</li>
<li><a href=""><code>150f23c</code></a> [Backport maintenance/4.0.x] Allow digits in ParamSpec and TypeVarTuple names...</li>
<li><a href=""><code>8b6251e</code></a> [Backport maintenance/4.0.x] Fix crash when enum member inference fails (<a href="">#11093</a>)</li>
<li><a href=""><code>d57aadb</code></a> [Backport maintenance/4.0.x] Fix <code>implicit-str-concat</code> false positive for mix...</li>
<li><a href=""><code>d9ea8d9</code></a> [Backport maintenance/4.0.x] Fix <code>unnecessary-comprehension</code> suggestion when ...</li>
<li><a href=""><code>cb1792a</code></a> [Backport maintenance/4.0.x] Allow digits in TypeVar names for invalid-name c...</li>
<li><a href=""><code>ee2ab9a</code></a> Handle InferenceError in decorator return analysis</li>
<li><a href=""><code>5bb5498</code></a> [Backport maintenance/4.0.x] Fix crash in typecheck checker when metaclass ar...</li>
<li><a href=""><code>a940533</code></a> [Backport maintenance/4.0.x] Fix a crash in <code>consider-using-enumerate</code> for no...</li>
<li><a href=""><code>b7a873a</code></a> [Backport maintenance/4.0.x] Fix crash in deprecated checker for non-string `...</li>
<li>Additional commits viewable in <a href="https://github.com/pylint-dev/pylint/compare/v4.0.5...v4.0.6">compare view</a></li>
</ul>
</details>
<br />

Updates `pytest` from 9.0.3 to 9.1.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pytest-dev/pytest/releases">pytest's releases</a>.</em></p>
<blockquote>
<h2>9.1.0</h2>
<h1>pytest 9.1.0 (2026-06-13)</h1>
<h2>Removals and backward incompatible breaking changes</h2>
<ul>
<li>
<p><a href="">#14533</a>: When using <code>--doctest-modules</code>, autouse fixtures with <code>module</code>, <code>package</code> or <code>session</code> scope that are defined inline in Python test modules (not plugins or conftests) will now possibly execute twice.</p>
<p>If this is undesirable, move the fixture definition to a <code>conftest.py</code> file if possible.</p>
<p>Technical explanation for those interested:
When using <!-- raw HTML omitted -->--doctest-modules<!-- raw HTML omitted -->, pytest possibly collects Python modules twice, once as <code>pytest.Module</code> and once as a <code>DoctestModule</code> (depending on the configuration).
Due to improvements in pytest's fixture implementation, if e.g. the <code>DoctestModule</code> collects a fixture, it is now visible to it only, and not to the <code>Module</code>.
This means that both need to register the fixtures independently.</p>
</li>
</ul>
<h2>Deprecations (removal in next major release)</h2>
<ul>
<li>
<p><a href="">#10819</a>: Added a deprecation warning for class-scoped fixtures defined as instance methods (without <code>@classmethod</code>). Such fixtures set attributes on a different instance than the test methods use, leading to unexpected behavior. Use <code>@classmethod</code> decorator instead -- by <code>yastcher</code>.</p>
<p>See <code>10819</code> and <code>14011</code>.</p>
</li>
<li>
<p><a href="">#12882</a>: Calling <code>request.getfixturevalue() &lt;pytest.FixtureRequest.getfixturevalue&gt;</code> during teardown to request a fixture that was not already requested is now deprecated and will become an error in pytest 10.</p>
<p>See <code>dynamic-fixture-request-during-teardown</code> for details.</p>
</li>
<li>
<p><a href="">#13409</a>: Using non-<code>~collections.abc.Collection</code> iterables (such as generators, iterators, or custom iterable objects) for the <code>argvalues</code> parameter in <code>@pytest.mark.parametrize &lt;pytest.mark.parametrize ref&gt;</code> and <code>metafunc.parametrize &lt;pytest.Metafunc.parametrize&gt;</code> is now deprecated.</p>
<p>These iterables get exhausted after the first iteration,
leading to tests getting unexpectedly skipped in cases such as running <code>pytest.main()</code> multiple times,
using class-level parametrize decorators,
or collecting tests multiple times.</p>
<p>See <code>parametrize-iterators</code> for details and suggestions.</p>
</li>
<li>
<p><a href="">#13946</a>: The private <code>config.inicfg</code> attribute is now deprecated.
Use <code>config.getini() &lt;pytest.Config.getini&gt;</code> to access configuration values instead.</p>
<p>See <code>config-inicfg</code> for more details.</p>
</li>
<li>
<p><a href="">#14004</a>: Passing <code>baseid</code> to <code>~pytest.FixtureDef</code> or <code>nodeid</code> strings to fixture registration APIs is now deprecated. These are internal pytest APIs that are used by some plugins.</p>
<p>Use the <code>node</code> parameter instead for fixture scoping. This enables more robust node-based
matching instead of string prefix matching.
If you've used <code>nodeid=None</code>, pass <code>node=session</code> instead.</p>
<p>This will be removed in pytest 10.</p>
</li>
<li>
<p><a href="">#14335</a>: The method of configuring hooks using markers, deprecated since pytest 7.2, is now scheduled to be removed in pytest 10.
See <code>hook-markers</code> for more details.</p>
</li>
<li>
<p><a href="">#14434</a>: The <code>--pastebin</code> option is now deprecated.</p>
</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>b2522cf</code></a> Prepare release version 9.1.0</li>
<li><a href=""><code>368d2fc</code></a> [refactor] Tighten <code>SetComparisonFunction</code> to <code>Iterator[str]</code> (<a href="">#14587</a>)</li>
<li><a href=""><code>ff77cd8</code></a> [refactor] Make base assertion comparisons return an iterator instead of a li...</li>
<li><a href=""><code>0d8491a</code></a> build(deps): Bump actions/stale from 10.2.0 to 10.3.0</li>
<li><a href=""><code>4a809d9</code></a> Merge pull request <a href="">#14568</a> from pytest-dev/register-fixture</li>
<li><a href=""><code>5dfa385</code></a> Fix recursion traceback test to cover all styles (<a href="">#14582</a>)</li>
<li><a href=""><code>f52ff0c</code></a> Add <code>pytest.register_fixture</code></li>
<li><a href=""><code>a8ac094</code></a> Merge pull request <a href="">#14567</a> from pytest-dev/more-visibility-deprecate</li>
<li><a href=""><code>e5620cd</code></a> [pre-commit.ci] pre-commit autoupdate (<a href="">#14577</a>)</li>
<li><a href=""><code>2ce9c6d</code></a> Merge pull request <a href="">#14540</a> from minbang930/fix-14533-doctest-module-fixtures</li>
<li>Additional commits viewable in <a href="https://github.com/pytest-dev/pytest/compare/9.0.3...9.1.0">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.15.16 to 0.15.17
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.15.17</h2>
<h2>Release Notes</h2>
<p>Released on 2026-06-11.</p>
<h3>Preview features</h3>
<ul>
<li>Allow human-readable names in suppression comments (<a href="">#25614</a>)</li>
<li>Fix handling of <code>ignore</code> comments within a <code>disable</code>/<code>enable</code> pair (<a href="">#25845</a>)</li>
<li>Prioritize human-readable names in CLI output (<a href="">#25869</a>)</li>
<li>Respect diagnostic start and parent ranges and trailing comments in <code>ruff:ignore</code> suppressions (<a href="">#25673</a>)</li>
<li>[<code>flake8-async</code>] Add <code>trio.as_safe_channel</code> to safe decorators (<code>ASYNC119</code>) (<a href="">#25775</a>)</li>
<li>[<code>flake8-pytest-style</code>] Also check <code>pytest_asyncio</code> fixtures (<a href="">#25375</a>)</li>
<li>[<code>ruff</code>] Ban <code>pytest</code> autouse fixtures (<code>RUF076</code>) (<a href="">#25477</a>)</li>
<li>[<code>pyupgrade</code>] Add <code>from __future__ import annotations</code> automatically (<code>UP007</code>, <code>UP045</code>) (<a href="">#23259</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Fix diagnostic when <code>ruff:enable</code> or <code>ruff:disable</code> appears where <code>ruff:ignore</code> is expected (<a href="">#25700</a>)</li>
<li>[<code>pyupgrade</code>] Preserve leading empty literals to avoid syntax errors (<code>UP032</code>) (<a href="">#25491</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-pytest-style</code>] Clarify diagnostic message for single parameters (<code>PT007</code>) (<a href="">#25592</a>)</li>
<li>[<code>numpy</code>] Drop autofix for <code>np.in1d</code> (<code>NPY201</code>) (<a href="">#25612</a>)</li>
<li>[<code>pylint</code>] Exempt Python version comparisons (<code>PLR2004</code>) (<a href="">#25743</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Reserve AST <code>Vec</code>s with correct capacity for common cases (<a href="">#25451</a>)</li>
</ul>
<h3>Formatter</h3>
<ul>
<li>Preserve whitespace for Quarto cell option comments (<a href="">#25641</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Allow rule names in <code>ruff rule</code> (<a href="">#25640</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Fix playground diagnostics scrollbars (<a href="">#25642</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/SuryanshSS1011"><code>@​SuryanshSS1011</code></a></li>
<li><a href="https://github.com/anishgirianish"><code>@​anishgirianish</code></a></li>
<li><a href="https://github.com/romero-deshaw"><code>@​romero-deshaw</code></a></li>
<li><a href="https://github.com/karlhillx"><code>@​karlhillx</code></a></li>
<li><a href="https://github.com/carljm"><code>@​carljm</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.15.17</h2>
<p>Released on 2026-06-11.</p>
<h3>Preview features</h3>
<ul>
<li>Allow human-readable names in suppression comments (<a href="">#25614</a>)</li>
<li>Fix handling of <code>ignore</code> comments within a <code>disable</code>/<code>enable</code> pair (<a href="">#25845</a>)</li>
<li>Prioritize human-readable names in CLI output (<a href="">#25869</a>)</li>
<li>Respect diagnostic start and parent ranges and trailing comments in <code>ruff:ignore</code> suppressions (<a href="">#25673</a>)</li>
<li>[<code>flake8-async</code>] Add <code>trio.as_safe_channel</code> to safe decorators (<code>ASYNC119</code>) (<a href="">#25775</a>)</li>
<li>[<code>flake8-pytest-style</code>] Also check <code>pytest_asyncio</code> fixtures (<a href="">#25375</a>)</li>
<li>[<code>ruff</code>] Ban <code>pytest</code> autouse fixtures (<code>RUF076</code>) (<a href="">#25477</a>)</li>
<li>[<code>pyupgrade</code>] Add <code>from __future__ import annotations</code> automatically (<code>UP007</code>, <code>UP045</code>) (<a href="">#23259</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Fix diagnostic when <code>ruff:enable</code> or <code>ruff:disable</code> appears where <code>ruff:ignore</code> is expected (<a href="">#25700</a>)</li>
<li>[<code>pyupgrade</code>] Preserve leading empty literals to avoid syntax errors (<code>UP032</code>) (<a href="">#25491</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-pytest-style</code>] Clarify diagnostic message for single parameters (<code>PT007</code>) (<a href="">#25592</a>)</li>
<li>[<code>numpy</code>] Drop autofix for <code>np.in1d</code> (<code>NPY201</code>) (<a href="">#25612</a>)</li>
<li>[<code>pylint</code>] Exempt Python version comparisons (<code>PLR2004</code>) (<a href="">#25743</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Reserve AST <code>Vec</code>s with correct capacity for common cases (<a href="">#25451</a>)</li>
</ul>
<h3>Formatter</h3>
<ul>
<li>Preserve whitespace for Quarto cell option comments (<a href="">#25641</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Allow rule names in <code>ruff rule</code> (<a href="">#25640</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Fix playground diagnostics scrollbars (<a href="">#25642</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/SuryanshSS1011"><code>@​SuryanshSS1011</code></a></li>
<li><a href="https://github.com/anishgirianish"><code>@​anishgirianish</code></a></li>
<li><a href="https://github.com/romero-deshaw"><code>@​romero-deshaw</code></a></li>
<li><a href="https://github.com/karlhillx"><code>@​karlhillx</code></a></li>
<li><a href="https://github.com/carljm"><code>@​carljm</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>7c645a9</code></a> Bump 0.15.17 (<a href="">#25872</a>)</li>
<li><a href=""><code>f381eb1</code></a> Prioritize human-readable names in CLI output (<a href="">#25869</a>)</li>
<li><a href=""><code>b9b4546</code></a> Minor workflow simplification (<a href="">#25870</a>)</li>
<li><a href=""><code>1e77ba0</code></a> [ty] Move <code>PreformattedBlockScanner</code> to format-agnostic location. (<a href="">#25856</a>)</li>
<li><a href=""><code>6f2b772</code></a> [ty] Preserve nominal type of enum.property instances (<a href="">#25849</a>)</li>
<li><a href=""><code>be4777c</code></a> [ty] Fix site-package error when multiple versions of pythons are installed i...</li>
<li><a href=""><code>53f6ff7</code></a> Allow human-readable names in suppression comments (<a href="">#25614</a>)</li>
<li><a href=""><code>6740325</code></a> [ty] Restrict uncached raw signature access (<a href="">#25866</a>)</li>
<li><a href=""><code>970b1bf</code></a> Auto-update snapshots when syncing typeshed (<a href="">#25841</a>)</li>
<li><a href=""><code>0785793</code></a> Fix handling of <code>ignore</code> comments within a <code>disable</code>/<code>enable</code> pair (<a href="">#25845</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.15.16...0.15.17">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `58aee13e6bb1`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.