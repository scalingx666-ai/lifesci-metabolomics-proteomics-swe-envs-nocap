# Issue

**Title:** Bump the python-dependencies group with 2 updates

## Description

Bumps the python-dependencies group with 2 updates: [fastjsonschema](https://github.com/horejsek/python-fastjsonschema) and [ruff](https://github.com/astral-sh/ruff).

Updates `fastjsonschema` from 2.21.2 to 2.22.1
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/horejsek/python-fastjsonschema/blob/master/CHANGELOG.txt">fastjsonschema's changelog</a>.</em></p>
<blockquote>
<p>=== 2.22.1 (2026-07-27)</p>
<ul>
<li>Fixed min Python version</li>
</ul>
<p>=== 2.22.0 (2026-07-25)</p>
<ul>
<li>Fixed IPv4 validation (rejecting leading zeros)</li>
<li>Fixed empty items and patternProperties</li>
<li>Fixed protection from deeply nested schemas potentially causing denial of service</li>
<li>Fixed comparing values for enum and const validations</li>
<li>Fixed resolving plain-name ref fragments</li>
<li>Fixed not throwing when unknown format is used</li>
<li>Fixed compilation of not, if/then/else, items, additionalItems, propertyNames and schema dependencies when a subschema generates no validation code</li>
<li>Added option to get all the errors (set <code>fast_fail</code> to <code>False</code>)</li>
<li>Added basic type hints</li>
<li>Added support of duration and uuid formats from draft-2019</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>8a7cde9</code></a> v2.22.1</li>
<li><a href=""><code>e1cf85b</code></a> Merge pull request <a href="">#213</a> from casperdcl/fix-pyver</li>
<li><a href=""><code>87960c8</code></a> fix min python version</li>
<li><a href=""><code>a2fb34c</code></a> v2.22.0</li>
<li><a href=""><code>1fa8834</code></a> Merge pull request <a href="">#209</a> from henryiii/fix-not-variable-leak</li>
<li><a href=""><code>606503d</code></a> Merge branch 'master' into fix-not-variable-leak</li>
<li><a href=""><code>9c385ea</code></a> Merge pull request <a href="">#207</a> from chuenchen309/fix/ipv4-format-reject-leading-zeros</li>
<li><a href=""><code>2a8955c</code></a> Merge pull request <a href="">#206</a> from gaoflow/fix-empty-body-codegen</li>
<li><a href=""><code>10e952b</code></a> fix: don't leak variables from not blocks into the outer scope</li>
<li><a href=""><code>5513da7</code></a> Reject IPv4 octets with leading zeros in the ipv4 format check</li>
<li>Additional commits viewable in <a href="https://github.com/horejsek/python-fastjsonschema/compare/v2.21.2...v2.22.1">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.15.22 to 0.16.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.0</h2>
<h2>Release Notes</h2>
<p>Released on 2026-07-23.</p>
<p>Check out the <a href="https://astral.sh/blog/ruff-v0.16.0">blog post</a> for a migration guide and overview of the changes!</p>
<h3>Breaking changes</h3>
<ul>
<li>
<p>Ruff now enables a much larger set of rules by default (413, up from 59). See the blog post for more details and the new <a href="https://docs.astral.sh/ruff/default-rules/">Default Rules</a> page for a full listing of the enabled rules. Note that this is primarily an expansion, but 18 of the more opinionated pycodestyle (<code>E</code>) and pyflakes (<code>F</code>) rules have been removed from the default set: <code>E401</code>, <code>E402</code>, <code>E701</code>, <code>E702</code>, <code>E703</code>, <code>E711</code>, <code>E712</code>, <code>E713</code>, <code>E714</code>, <code>E721</code>, <code>E731</code>, <code>E741</code>, <code>E742</code>, <code>E743</code>, <code>F403</code>, <code>F405</code>, <code>F406</code>, and <code>F722</code>.</p>
</li>
<li>
<p>Ruff can now format Python code blocks in Markdown files and will do this by default. See the <a href="https://docs.astral.sh/ruff/formatter/#markdown-code-formatting">documentation</a> for more details.</p>
</li>
<li>
<p>Ruff now supports <code>ruff: ignore</code> comments at the ends of lines, like <code>noqa</code> comments, or on the line preceding a diagnostic. For example, these both suppress an <a href="https://docs.astral.sh/ruff/rules/unused-import/"><code>unused-import</code></a> (<code>F401</code>) diagnostic:</p>
<pre lang="py"><code>import math  # ruff: ignore[F401]
<h1>ruff: ignore[F401]</h1>
<p>import os
</code></pre></p>
</li>
<li>
<p>Fixes are now shown in <code>check</code> and <code>format --check</code> output:</p>
<pre lang="console"><code>❯ ruff format --check .
unformatted: File would be reformatted
 --&gt; try.md:1:1
  |
1 | ```python
  - import   math
2 + import math
3 | ```
  |
<p>1 file would be reformatted
</code></pre></p>
<p>This example also shows off the Markdown formatting.</p>
</li>
<li>
<p><code>format --check</code> now supports the same output formats as the linter, including the <code>github</code> and <code>gitlab</code> outputs for rendering annotations in CI:</p>
<pre lang="console"><code>❯ ruff format --check --output-format github .
::error title=ruff (unformatted),file=try.md,line=2,col=8,endLine=2,endColumn=10::try.md:2:8: unformatted: File would be reformatted
</code></pre>
<p>See the CLI help or <a href="https://docs.astral.sh/ruff/settings/#output-format">documentation</a> for the full list of supported formats.</p>
</li>
<li>
<p>The <code>filename</code>, <code>location</code>, <code>end_location</code>, <code>fix.edits[].location</code>, and <code>fix.edits[].end_location</code> fields in the JSON output format may now be <code>null</code> rather than defaulting to the empty string and row 1, column 1, respectively.</p>
</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.0</h2>
<p>Released on 2026-07-23.</p>
<p>Check out the <a href="https://astral.sh/blog/ruff-v0.16.0">blog post</a> for a migration
guide and overview of the changes!</p>
<h3>Breaking changes</h3>
<ul>
<li>
<p>Ruff now enables a much larger set of rules by default (413, up from 59). See the blog post for
more details and the new <a href="https://docs.astral.sh/ruff/default-rules/">Default Rules</a> page for a
full listing of the enabled rules. Note that this is primarily an expansion, but 18 of the more
opinionated pycodestyle (<code>E</code>) and pyflakes (<code>F</code>) rules have been removed from the default set:
<code>E401</code>, <code>E402</code>, <code>E701</code>, <code>E702</code>, <code>E703</code>, <code>E711</code>, <code>E712</code>, <code>E713</code>, <code>E714</code>, <code>E721</code>, <code>E731</code>, <code>E741</code>,
<code>E742</code>, <code>E743</code>, <code>F403</code>, <code>F405</code>, <code>F406</code>, and <code>F722</code>.</p>
</li>
<li>
<p>Ruff can now format Python code blocks in Markdown files and will do this by default. See the
<a href="https://docs.astral.sh/ruff/formatter/#markdown-code-formatting">documentation</a> for more details.</p>
</li>
<li>
<p>Ruff now supports <code>ruff: ignore</code> comments at the ends of lines, like <code>noqa</code> comments, or on the line preceding a diagnostic. For example, these both suppress an <a href="https://docs.astral.sh/ruff/rules/unused-import/"><code>unused-import</code></a> (<code>F401</code>) diagnostic:</p>
<pre lang="py"><code>import math  # ruff: ignore[F401]
<h1>ruff: ignore[F401]</h1>
<p>import os
</code></pre></p>
</li>
<li>
<p>Fixes are now shown in <code>check</code> and <code>format --check</code> output:</p>
<pre lang="console"><code>❯ ruff format --check .
unformatted: File would be reformatted
 --&gt; try.md:1:1
  |
1 | ```python
  - import   math
2 + import math
3 | ```
  |
<p>1 file would be reformatted
</code></pre></p>
<p>This example also shows off the Markdown formatting.</p>
</li>
<li>
<p><code>format --check</code> now supports the same output formats as the linter, including the <code>github</code> and
<code>gitlab</code> outputs for rendering annotations in CI:</p>
<pre lang="console"><code></code></pre>
</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>a2635fd</code></a> Bump 0.16.0 (<a href="">#27136</a>)</li>
<li><a href=""><code>3433449</code></a> [ty] Reuse full call diagnostics for implicit setter calls (<a href="">#27115</a>)</li>
<li><a href=""><code>2240070</code></a> Reflect <code>ruff: ignore</code> and <code>--add-ignore</code> stabilization in documentation (<a href="">#27</a>...</li>
<li><a href=""><code>17ef711</code></a> Stabilize <code>--add-ignore</code> (<a href="">#27125</a>)</li>
<li><a href=""><code>ef912bb</code></a> Add newly stabilized rules to defaults (<a href="">#27055</a>)</li>
<li><a href=""><code>b30f040</code></a> Stabilize new default rules (<a href="">#27035</a>)</li>
<li><a href=""><code>bcd70c5</code></a> Exclude Markdown files from <code>format-dev</code> runs (<a href="">#27052</a>)</li>
<li><a href=""><code>87e51e2</code></a> Fix <code>format --check</code> spans for syntax errors (<a href="">#27045</a>)</li>
<li><a href=""><code>afe2723</code></a> [<code>flake8-gettext</code>] Stabilize qualified-name and built-in binding resolution (...</li>
<li><a href=""><code>a9702d8</code></a> [<code>flake8-bandit</code>] Stabilize string literal binding resolution (<code>S310</code>) (<a href="">#26944</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.15.22...0.16.0">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `3c91ae23e228`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.