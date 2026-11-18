# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [click](https://github.com/pallets/click), [fastjsonschema](https://github.com/horejsek/python-fastjsonschema) and [ruff](https://github.com/astral-sh/ruff).

Updates `click` from 8.5.0 to 8.5.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pallets/click/releases">click's releases</a>.</em></p>
<blockquote>
<h2>8.5.1</h2>
<p>This is the Click 8.5.1 fix release, which fixes bugs but does not otherwise change behavior and should not result in breaking changes compared to the latest feature release.</p>
<p>PyPI: <a href="https://pypi.org/project/click/8.5.1/">https://pypi.org/project/click/8.5.1/</a>
Changes: <a href="https://click.palletsprojects.com/page/changes/#version-8-5-1">https://click.palletsprojects.com/page/changes/#version-8-5-1</a>
Milestone: <a href="https://github.com/pallets/click/milestone/66">https://github.com/pallets/click/milestone/66</a></p>
<ul>
<li>Fix <code>copy.deepcopy()</code> and <code>pickle</code> on a <code>Parameter</code>, <code>Option</code> or <code>Command</code>. <a href="">#3805</a></li>
<li>A <code>KeyboardInterrupt</code> arriving while <code>Command.main()</code> reports an abort or an error,
or while it exits, no longer escapes as an unhandled traceback. The command still
exits with the intended code; only the message may be lost. <a href="">#3802</a></li>
<li>Add <code>Option.get_help_spec()</code>, which returns the option's left help
column even when the option is hidden. <code>Option.get_help_record()</code> still
returns <code>None</code> for hidden options, so help screens are unchanged. <a href="">#3821</a></li>
<li>The <code>Positional arguments</code> help section lists every argument of the command,
not only the documented ones. An argument with no <code>help</code> gets an empty
description, the same way an option with no <code>help</code> does. <a href="">#3860</a></li>
<li><code>Argument.get_help_record()</code> always returns a tuple. It used to return
<code>None</code> for an argument with no <code>help</code>. <a href="">#3860</a></li>
<li>Document which types are inferred from <code>default</code>, and what an unrecognized
<code>type</code> callable does to a command-line value. <a href="">#3036</a> <a href="">#3808</a></li>
<li><code>path_type</code> narrows the converted value's type for <code>convert</code> and <code>prompt</code>.
<a href="">#3822</a> <a href="">#3858</a></li>
<li><code>Parameter</code> accepts a new <code>help</code> argument, and <code>Option</code> and <code>Argument</code>
inherit it. <code>Parameter.to_info_dict()</code> now reports <code>help</code> for every kind of parameter.
<a href="">#3861</a></li>
<li>A command's short help no longer stops at an abbreviation such as <code>vs.</code> or <code>e.g.</code>
inside the first sentence. A period ends the sentence only when it closes the text
or the next word does not start in lowercase. <a href="">#3865</a></li>
<li>With <code>show_envvar=True</code>, an option's error message now prints all variables of an
<code>envvar</code> sequence instead of the <code>repr</code> of the sequence. <a href="">#3884</a></li>
<li>An empty <code>envvar</code>, such as <code>[]</code> or <code>&quot;&quot;</code>, shows the same help and error message as
no <code>envvar</code> when <code>show_envvar=True</code>. The help screen used to show <code>[env var: ]</code>.
<a href="">#3884</a></li>
<li>Align command's deprecated help text to options and arguments: do not translate the
command's own help text, only the <code>(DEPRECATED)</code> label. <a href="">#3901</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/pallets/click/blob/main/CHANGES.md">click's changelog</a>.</em></p>
<blockquote>
<h2>Version 8.5.1</h2>
<p>Released 2026-11-09</p>
<ul>
<li>Fix <code>copy.deepcopy()</code> and <code>pickle</code> on a <code>Parameter</code>, <code>Option</code> or <code>Command</code>. {pr}<code>3805</code></li>
<li>A <code>KeyboardInterrupt</code> arriving while <code>Command.main()</code> reports an abort or an error,
or while it exits, no longer escapes as an unhandled traceback. The command still
exits with the intended code; only the message may be lost. {issue}<code>3802</code></li>
<li>Add {meth}<code>Option.get_help_spec</code>, which returns the option's left help
column even when the option is hidden. {meth}<code>Option.get_help_record</code> still
returns <code>None</code> for hidden options, so help screens are unchanged. {pr}<code>3821</code></li>
<li>The <code>Positional arguments</code> help section lists every argument of the command,
not only the documented ones. An argument with no <code>help</code> gets an empty
description, the same way an option with no <code>help</code> does. {pr}<code>3860</code></li>
<li>{meth}<code>Argument.get_help_record</code> always returns a tuple. It used to return
<code>None</code> for an argument with no <code>help</code>. {pr}<code>3860</code></li>
<li>Document which types are inferred from <code>default</code>, and what an unrecognized
<code>type</code> callable does to a command-line value. {issue}<code>3036</code> {pr}<code>3808</code></li>
<li><code>path_type</code> narrows the converted value's type for <code>convert</code> and <code>prompt</code>.
{issue}<code>3822</code> {pr}<code>3858</code></li>
<li>{class}<code>Parameter</code> accepts a new <code>help</code> argument and {class}<code>Option</code> and {class}<code>Argument</code>
inherits it. {meth}<code>Parameter.to_info_dict</code> now reports <code>help</code> for every kind of parameter.
{pr}<code>3861</code></li>
<li>A command's short help no longer stops at an abbreviation such as <code>vs.</code> or <code>e.g.</code>
inside the first sentence. A period ends the sentence only when it closes the text
or the next word does not start in lowercase. {pr}<code>3865</code></li>
<li>With <code>show_envvar=True</code>, an option's error message now prints all variables of an
<code>envvar</code> sequence instead of the <code>repr</code> of the sequence. {pr}<code>3884</code></li>
<li>An empty <code>envvar</code>, such as <code>[]</code> or <code>&quot;&quot;</code>, shows the same help and error message as
no <code>envvar</code> when <code>show_envvar=True</code>. The help screen used to show <code>[env var: ]</code>.
{pr}<code>3884</code></li>
<li>Align command's deprecated help text to options and arguments: do not translate the
command's own help text, only the <code>(DEPRECATED)</code> label. {pr}<code>3901</code></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>cf19179</code></a> Release version 8.5.1</li>
<li><a href=""><code>1ff766d</code></a> Remove documentation changelog entry.</li>
<li><a href=""><code>16da191</code></a> Add a standalone application guide for Nuitka (<a href="">#3897</a>)</li>
<li><a href=""><code>473f652</code></a> Remove issue and PR references outside the changelog (<a href="">#3905</a>)</li>
<li><a href=""><code>df7fe0b</code></a> Remove issue and PR references outside the changelog</li>
<li><a href=""><code>4fd4206</code></a> Bump <code>pypa/gh-action-pypi-publish</code> to <code>v1.14.3</code> (<a href="">#3906</a>)</li>
<li><a href=""><code>9048ab0</code></a> Bump <code>pypa/gh-action-pypi-publish</code> to <code>v1.14.3</code></li>
<li><a href=""><code>ff0c369</code></a> Add a standalone application guide for Nuitka</li>
<li><a href=""><code>5125851</code></a> Stop passing a deprecated command's help text through <code>gettext</code> (<a href="">#3901</a>)</li>
<li><a href=""><code>6d34602</code></a> Additional round-trip tests for <code>unstyle()</code> (<a href="">#3899</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/pallets/click/compare/8.5.0...8.5.1">compare view</a></li>
</ul>
</details>
<br />

Updates `fastjsonschema` from 2.22.2 to 2.22.3
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/horejsek/python-fastjsonschema/blob/master/CHANGELOG.txt">fastjsonschema's changelog</a>.</em></p>
<blockquote>
<p>=== 2.22.3 (2026-11-01)</p>
<ul>
<li>Fixed property names with <code>{</code> or <code>}</code> being evaluated as format string in error messages</li>
<li>Fixed numeric keywords (minimum, maximum, multipleOf, exclusiveMinimum, exclusiveMaximum) being applied to booleans</li>
<li>Fixed <code>propertyNames: false</code> crashing on non-object values</li>
<li>Fixed the <code>date-time</code> format accepting months, days and hours out of range (such as <code>2020-19-39T29:00:00Z</code>) and rejecting a leap second (<code>23:59:60Z</code>)</li>
<li>Fixed the <code>date</code> and <code>date-time</code> formats accepting days that do not exist in their month, such as <code>2021-02-29</code> and <code>2021-04-31</code></li>
<li>Fixed the <code>time</code> format accepting hours, minutes, seconds and offsets out of range (such as <code>29:99:99</code>)</li>
<li>Fixed <code>minimum</code> and <code>maximum</code> being exclusive in draft 06 and later when <code>exclusiveMinimum</code> or <code>exclusiveMaximum</code> is set to a number other than zero</li>
<li>Fixed bools in <code>uniqueItems</code></li>
<li>Added type annotations for public API and <code>py.typed</code> marker (PEP 561)</li>
<li>Added <code>message</code> to <code>JsonSchemaValuesException</code> joining messages of all collected errors</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>9d3f5ee</code></a> v2.22.3</li>
<li><a href=""><code>f00179d</code></a> update changelog</li>
<li><a href=""><code>17dd13c</code></a> Merge pull request <a href="">#222</a> from muneikh/fix-boolean-string-unique-items</li>
<li><a href=""><code>001080d</code></a> Merge pull request <a href="">#231</a> from wleeaf/fix-draft06-inclusive-min-max</li>
<li><a href=""><code>ecbc530</code></a> Merge pull request <a href="">#229</a> from mayankdhingra02/fix-integer-multiple-of</li>
<li><a href=""><code>b4fe2b9</code></a> Merge pull request <a href="">#226</a> from Doyoubelieveinfate/fix/null-character-pattern</li>
<li><a href=""><code>ba3354a</code></a> Merge pull request <a href="">#228</a> from pcbeingused333/fix/calendar-days-date-formats</li>
<li><a href=""><code>0854b5b</code></a> Merge upstream master into fix/calendar-days-date-formats</li>
<li><a href=""><code>bddce5c</code></a> Keep minimum and maximum inclusive in draft 06 and later</li>
<li><a href=""><code>aa322b6</code></a> Preserve exact integer arithmetic for multipleOf</li>
<li>Additional commits viewable in <a href="https://github.com/horejsek/python-fastjsonschema/compare/v2.22.2...v2.22.3">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.17.3 to 0.17.4
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.17.4</h2>
<h2>Release Notes</h2>
<p>Released on 2026-11-05.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>flake8-logging-format</code>] Avoid behavior changes and syntax errors in fixes (<code>G004</code>) (<a href="">#27419</a>)</li>
<li>[<code>security</code>] Implement <code>tarfile-ignore-zeros-true</code> (<a href="">#28680</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Accept a bare raise before a semicolon (<a href="">#29761</a>)</li>
<li>Allow match identifiers after a semicolon (<a href="">#29760</a>)</li>
<li>Fix panic on BOM-prefixed files in diagnostic renderer (<a href="">#30017</a>)</li>
<li>[<code>flake8-simplify</code>] Report collapsible <code>elif</code> clauses after a multi-statement <code>if</code> branch (<code>SIM102</code>) (<a href="">#29814</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Show more nonprinting characters in diagnostic fix diffs (<a href="">#30062</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Coalesce source slices when formatting attributes (<a href="">#29841</a>)</li>
<li>Collect return statements with a statement-only visitor (<a href="">#29911</a>)</li>
<li>[<code>pyflakes</code>] Defer value comparisons for repeated dictionary keys (<code>F601</code>, <code>F602</code>) (<a href="">#29739</a>)</li>
<li>Format node fields directly when comment handling is unnecessary (<a href="">#29853</a>)</li>
<li>Reduce formatter source-slice overhead (<a href="">#29855</a>)</li>
<li>Reuse a callee's qualified name across lint rules (<a href="">#29916</a>)</li>
<li>Skip invalid string character checks when the source contains none (<a href="">#29883</a>)</li>
<li>Use a Bloom filter for formatter comment lookups (<a href="">#29852</a>)</li>
<li>Use a concrete buffer for ordinary writes (<a href="">#29819</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Give <code>NO_COLOR</code> precedence in Ruff and ty diagnostics (<a href="">#29898</a>)</li>
<li>Honor <code>CLICOLOR=0</code> in Ruff and ty diagnostics (<a href="">#29910</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Correct the documented <code>version</code> and <code>src</code> defaults for <code>ruff-action</code> (<a href="">#29880</a>)</li>
<li>[<code>flake8-bugbear</code>] Make <code>B014</code> example error out-of-the-box (<a href="">#29941</a>)</li>
<li>[<code>flake8-no-pep420</code>] Document preview behavior (<code>INP001</code>) (<a href="">#29764</a>)</li>
<li>[<code>isort</code>] Expand <code>I001</code> documentation (<a href="">#29843</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>[syntax-errors] Extend <code>__debug__</code> write check to attribute targets (<a href="">#27908</a>)</li>
</ul>
<h3>Contributors</h3>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.17.4</h2>
<p>Released on 2026-11-05.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>flake8-logging-format</code>] Avoid behavior changes and syntax errors in fixes (<code>G004</code>) (<a href="">#27419</a>)</li>
<li>[<code>security</code>] Implement <code>tarfile-ignore-zeros-true</code> (<a href="">#28680</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Accept a bare raise before a semicolon (<a href="">#29761</a>)</li>
<li>Allow match identifiers after a semicolon (<a href="">#29760</a>)</li>
<li>Fix panic on BOM-prefixed files in diagnostic renderer (<a href="">#30017</a>)</li>
<li>[<code>flake8-simplify</code>] Report collapsible <code>elif</code> clauses after a multi-statement <code>if</code> branch (<code>SIM102</code>) (<a href="">#29814</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Show more nonprinting characters in diagnostic fix diffs (<a href="">#30062</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Coalesce source slices when formatting attributes (<a href="">#29841</a>)</li>
<li>Collect return statements with a statement-only visitor (<a href="">#29911</a>)</li>
<li>[<code>pyflakes</code>] Defer value comparisons for repeated dictionary keys (<code>F601</code>, <code>F602</code>) (<a href="">#29739</a>)</li>
<li>Format node fields directly when comment handling is unnecessary (<a href="">#29853</a>)</li>
<li>Reduce formatter source-slice overhead (<a href="">#29855</a>)</li>
<li>Reuse a callee's qualified name across lint rules (<a href="">#29916</a>)</li>
<li>Skip invalid string character checks when the source contains none (<a href="">#29883</a>)</li>
<li>Use a Bloom filter for formatter comment lookups (<a href="">#29852</a>)</li>
<li>Use a concrete buffer for ordinary writes (<a href="">#29819</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Give <code>NO_COLOR</code> precedence in Ruff and ty diagnostics (<a href="">#29898</a>)</li>
<li>Honor <code>CLICOLOR=0</code> in Ruff and ty diagnostics (<a href="">#29910</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Correct the documented <code>version</code> and <code>src</code> defaults for <code>ruff-action</code> (<a href="">#29880</a>)</li>
<li>[<code>flake8-bugbear</code>] Make <code>B014</code> example error out-of-the-box (<a href="">#29941</a>)</li>
<li>[<code>flake8-no-pep420</code>] Document preview behavior (<code>INP001</code>) (<a href="">#29764</a>)</li>
<li>[<code>isort</code>] Expand <code>I001</code> documentation (<a href="">#29843</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>[syntax-errors] Extend <code>__debug__</code> write check to attribute targets (<a href="">#27908</a>)</li>
</ul>
<h3>Contributors</h3>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>05cdc36</code></a> Bump version to 0.17.4 (<a href="">#30073</a>)</li>
<li><a href=""><code>c6b17c2</code></a> [ty] Freshen method typevars before owner specialization (<a href="">#29543</a>)</li>
<li><a href=""><code>4b0b407</code></a> [ty] Preserve unions inferred during fixpoint iteration (<a href="">#29927</a>)</li>
<li><a href=""><code>1dd3e9e</code></a> Show more nonprinting characters in diagnostic fix diffs (<a href="">#30062</a>)</li>
<li><a href=""><code>32be8e7</code></a> [ty] Skip fixpoint iteration for simple generic calls (<a href="">#30054</a>)</li>
<li><a href=""><code>926ccc8</code></a> [ty] Handle output errors when generating shell completions (<a href="">#29997</a>)</li>
<li><a href=""><code>c86652a</code></a> [ty] Skip active Conda and Pixi environments during discovery if the environm...</li>
<li><a href=""><code>c9150f0</code></a> Add project walltime benchmarks for Ruff (<a href="">#30061</a>)</li>
<li><a href=""><code>64989ec</code></a> [ty] Report invalid module globs once per override pattern (<a href="">#30031</a>)</li>
<li><a href=""><code>367a563</code></a> [ty] Fix conditional type and tuple annotations (<a href="">#29987</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.17.3...0.17.4">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e8f72d0ab404`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.