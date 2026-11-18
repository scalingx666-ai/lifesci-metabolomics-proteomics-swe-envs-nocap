# Issue

**Title:** Bump ruff from 0.15.20 to 0.15.21 in the python-dependencies group

## Description

Bumps the python-dependencies group with 1 update: [ruff](https://github.com/astral-sh/ruff).

Updates `ruff` from 0.15.20 to 0.15.21
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.15.21</h2>
<h2>Release Notes</h2>
<p>Released on 2026-07-09.</p>
<h3>Preview features</h3>
<ul>
<li>Add <code>--add-ignore</code> for adding <code>ruff:ignore</code> comments (<a href="">#26346</a>)</li>
<li>[<code>flake8-comprehensions</code>] Drop <code>C409</code> tuple comprehension preview behavior (<a href="">#25707</a>)</li>
<li>Avoid whitespace normalization when formatting comments (<a href="">#26455</a>)</li>
<li>[<code>pyupgrade</code>] Lint and fix use of deprecated <code>abc</code> decorators (<code>UP051</code>) (<a href="">#26417</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Refine non-empty f-string detection (<a href="">#26526</a>)</li>
<li>Detect syntax errors in individual notebook cells (<a href="">#26419</a>)</li>
<li>[<code>flake8-implicit-str-concat</code>] Fix <code>ISC003</code> autofix incorrectly stripping <code>+</code> from comments (<a href="">#26554</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-executable</code>] Mark <code>EXE004</code> fix as unsafe (<a href="">#26033</a>)</li>
<li>[<code>flake8-pyi</code>] Mark <code>PYI061</code> fixes as unsafe in Python files (<a href="">#26533</a>)</li>
<li>[<code>pydocstyle</code>] Skip <code>overload-with-docstring</code> in stub files (<code>D418</code>) (<a href="">#26318</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Avoid per-token source index visitor calls (<a href="">#26506</a>)</li>
<li>Cache parenthesized expression boundaries in the formatter (<a href="">#26344</a>)</li>
<li>Improve performance of rendering edits in preview mode (<a href="">#26565</a>)</li>
<li>Inline <code>fits_element</code> in formatter (<a href="">#26429</a>)</li>
<li>Inline formatter printing hot paths (<a href="">#26504</a>)</li>
<li>Lazily create builtin bindings (<a href="">#26510</a>)</li>
<li>Skip empty trivia scans in the source indexer (<a href="">#26507</a>)</li>
<li>Use ICF for macOS release builds (<a href="">#25780</a>)</li>
</ul>
<h3>Formatter</h3>
<ul>
<li>Add <code>--extend-exclude</code> to <code>ruff format</code> (<a href="">#26372</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Add &quot;How does Ruff's import sorting compare to isort?&quot; link to README (<a href="">#26530</a>)</li>
<li>Fix Mozilla Firefox repository link in README (<a href="">#26537</a>)</li>
<li>[<code>flake8-bandit</code>] Fix misleading docstring for <code>mako-templates</code> (<code>S702</code>) (<a href="">#26432</a>)</li>
<li>[<code>ruff</code>] Fix non-triggering example for <code>if-key-in-dict-del</code> (<code>RUF051</code>) (<a href="">#26433</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/EkriirkE"><code>@​EkriirkE</code></a></li>
<li><a href="https://github.com/tingerrr"><code>@​tingerrr</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.15.21</h2>
<p>Released on 2026-07-09.</p>
<h3>Preview features</h3>
<ul>
<li>Add <code>--add-ignore</code> for adding <code>ruff:ignore</code> comments (<a href="">#26346</a>)</li>
<li>[<code>flake8-comprehensions</code>] Drop <code>C409</code> tuple comprehension preview behavior (<a href="">#25707</a>)</li>
<li>Avoid whitespace normalization when formatting comments (<a href="">#26455</a>)</li>
<li>[<code>pyupgrade</code>] Lint and fix use of deprecated <code>abc</code> decorators (<code>UP051</code>) (<a href="">#26417</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Refine non-empty f-string detection (<a href="">#26526</a>)</li>
<li>Detect syntax errors in individual notebook cells (<a href="">#26419</a>)</li>
<li>[<code>flake8-implicit-str-concat</code>] Fix <code>ISC003</code> autofix incorrectly stripping <code>+</code> from comments (<a href="">#26554</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-executable</code>] Mark <code>EXE004</code> fix as unsafe (<a href="">#26033</a>)</li>
<li>[<code>flake8-pyi</code>] Mark <code>PYI061</code> fixes as unsafe in Python files (<a href="">#26533</a>)</li>
<li>[<code>pydocstyle</code>] Skip <code>overload-with-docstring</code> in stub files (<code>D418</code>) (<a href="">#26318</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Avoid per-token source index visitor calls (<a href="">#26506</a>)</li>
<li>Cache parenthesized expression boundaries in the formatter (<a href="">#26344</a>)</li>
<li>Improve performance of rendering edits in preview mode (<a href="">#26565</a>)</li>
<li>Inline <code>fits_element</code> in formatter (<a href="">#26429</a>)</li>
<li>Inline formatter printing hot paths (<a href="">#26504</a>)</li>
<li>Lazily create builtin bindings (<a href="">#26510</a>)</li>
<li>Skip empty trivia scans in the source indexer (<a href="">#26507</a>)</li>
<li>Use ICF for macOS release builds (<a href="">#25780</a>)</li>
</ul>
<h3>Formatter</h3>
<ul>
<li>Add <code>--extend-exclude</code> to <code>ruff format</code> (<a href="">#26372</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Add &quot;How does Ruff's import sorting compare to isort?&quot; link to README (<a href="">#26530</a>)</li>
<li>Fix Mozilla Firefox repository link in README (<a href="">#26537</a>)</li>
<li>[<code>flake8-bandit</code>] Fix misleading docstring for <code>mako-templates</code> (<code>S702</code>) (<a href="">#26432</a>)</li>
<li>[<code>ruff</code>] Fix non-triggering example for <code>if-key-in-dict-del</code> (<code>RUF051</code>) (<a href="">#26433</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/EkriirkE"><code>@​EkriirkE</code></a></li>
<li><a href="https://github.com/tingerrr"><code>@​tingerrr</code></a></li>
<li><a href="https://github.com/s-rigaud"><code>@​s-rigaud</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>3e1f636</code></a> Bump 0.15.21 (<a href="">#26676</a>)</li>
<li><a href=""><code>4059807</code></a> [ty] Infer metaclass-declared attributes on class instances (<a href="">#26512</a>)</li>
<li><a href=""><code>013e5d0</code></a> [ty] Use a dedicated project name type (<a href="">#26665</a>)</li>
<li><a href=""><code>7ad39ad</code></a> [ty] Avoid allocating decorated parameter names (<a href="">#26666</a>)</li>
<li><a href=""><code>c36f662</code></a> Improve performance of rendering edits in preview mode (<a href="">#26565</a>)</li>
<li><a href=""><code>ad26408</code></a> [ty] Gate membership narrowing on <code>__contains__</code> semantics (<a href="">#25964</a>)</li>
<li><a href=""><code>4594ca7</code></a> [ty] Add variant discriminators for <code>CodeGeneratorKind</code> (<a href="">#26659</a>)</li>
<li><a href=""><code>1af03da</code></a> [ty] Pydantic: Fix float conversion in unions (<a href="">#26655</a>)</li>
<li><a href=""><code>a004a36</code></a> [ty] Handle callable classes in solver (<a href="">#26090</a>)</li>
<li><a href=""><code>d8ef3b0</code></a> [ty] Parse all supported Google docstring sections. (<a href="">#26653</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.15.20...0.15.21">compare view</a></li>
</ul>
</details>
<br />

[![Dependabot compatibility score](https://dependabot-badges.githubapp.com/badges/compatibility_score?dependency-name=ruff&package-manager=pip&previous-version=0.15.20&new-version=0.15.21)](https://docs.github.com/en/github/managing-security-vulnerabilities/about-dependabot-security-updates#about-compatibility-scores)

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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `96028b9b0bf2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.