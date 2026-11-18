# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [click](https://github.com/pallets/click), [pylint](https://github.com/pylint-dev/pylint) and [ruff](https://github.com/astral-sh/ruff).

Updates `click` from 8.4.2 to 8.5.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pallets/click/releases">click's releases</a>.</em></p>
<blockquote>
<h2>8.5.0</h2>
<p>This is the Click 8.5.0 feature release. A feature release may include new features, remove previously deprecated code, add new deprecation, or introduce potentially breaking changes.</p>
<p>We encourage everyone to upgrade. You can read more about our <a href="https://palletsprojects.com/versions">Version Support Policy</a> on our website.</p>
<p>PyPI: <a href="https://pypi.org/project/click/8.5.0/">https://pypi.org/project/click/8.5.0/</a>
Changes:  <a href="https://click.palletsprojects.com/page/changes/#version-8-5-0">https://click.palletsprojects.com/page/changes/#version-8-5-0</a>
Milestone <a href="https://github.com/pallets/click/milestone/33">https://github.com/pallets/click/milestone/33</a></p>
<ul>
<li>Add built-in shell completion support for PowerShell (Windows PowerShell
5.1+ and pwsh 7+) alongside the existing <code>bash</code>, <code>zsh</code>, and <code>fish</code>
completers. Use <code>_FOO_BAR_COMPLETE=powershell_source foo-bar</code> to generate
the completion script. <a href="">#2672</a> <a href="">#3637</a></li>
<li>Supported versions of Windows enable ANSI terminal styles by default.
Colorama is no longer a dependency and is not used. <a href="">#2986</a> <a href="">#3505</a></li>
<li>{class}<code>Argument</code> accepts a <code>help</code> parameter, and help output includes
a <code>Positional arguments</code> section when argument help is available. <a href="">#2983</a> <a href="">#3473</a></li>
<li><code>confirm()</code> and <code>prompt()</code> strip ANSI color and style codes from the
prompt when the output stream does not support them, matching <code>echo()</code>.
This stripping was lost in <code>8.4.0</code> when <a href="">#2969</a> began writing the
prompt with <code>input()</code> directly. <a href="">#3572</a> <a href="">#3653</a></li>
<li>{class}<code>Path</code> with <code>allow_dash=True</code> no longer triggers a <code>BytesWarning</code>,
an error under <code>python -bb</code>, when checking a value against the <code>-</code>
convention. <a href="">#2877</a> <a href="">#3642</a></li>
<li>Add {func}<code>custom_version_option</code>, a <code>--version</code> option whose output is
produced by a callback, covering cases {func}<code>version_option</code> intentionally
does not. The feature set of {func}<code>version_option</code> is now frozen; see
[discussion <a href="">#3527</a>](<a href="https://github.com/pallets/click/discussions/3527">https://github.com/pallets/click/discussions/3527</a>). <a href="">#3581</a></li>
<li><code>style()</code> and <code>secho()</code> no longer silently drop the 256-color index <code>0</code>
(black) passed as <code>fg</code> or <code>bg</code>, and now validate color arguments. Invalid
colors raise a <code>ValueError</code> instead of a <code>TypeError</code>. <a href="">#3677</a></li>
<li>The automatic help option stores its value under the reserved name
<code>_click_default_help</code> instead of <code>help</code>, so a parameter named <code>help</code> no
longer breaks parsing. The new name is visible in
{meth}<code>Command.to_info_dict</code> output. Parameters that overwrite each other's
value trigger a warning: an argument sharing its name with another
parameter, or any parameter claiming the reserved name. Options may still
share a name to compete for the same value (feature switches).
<a href="">#2819</a> <a href="">#3678</a></li>
<li><code>unstyle</code> and the ANSI handling behind help-text wrapping now strip the full
CSI escape-sequence grammar. <a href="">#3681</a></li>
<li>Streamline <code>Option</code> flag handling: the flag-kind, type, lazy-default and
validation steps in <code>Option.__init__</code> move into focused helpers, and
<code>flag_value</code> and <code>default</code> keep their unset sentinel at construction
(resolved lazily on read) so <code>is UNSET</code> reliably tells a user-supplied value
from an auto-derived one. Runtime behavior is unchanged, but
{meth}<code>Parameter.to_info_dict</code> now resolves <code>default=True</code> on a feature
switch to its <code>flag_value</code>, matching what the function receives at call</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/pallets/click/blob/main/CHANGES.md">click's changelog</a>.</em></p>
<blockquote>
<h2>Version 8.5.0</h2>
<p>Released 2026-08-24</p>
<ul>
<li>Add built-in shell completion support for PowerShell (Windows PowerShell
5.1+ and pwsh 7+) alongside the existing <code>bash</code>, <code>zsh</code>, and <code>fish</code>
completers. Use <code>_FOO_BAR_COMPLETE=powershell_source foo-bar</code> to generate
the completion script. {issue}<code>2672</code> {pr}<code>3637</code></li>
<li>Supported versions of Windows enable ANSI terminal styles by default.
Colorama is no longer a dependency and is not used. {issue}<code>2986</code> {pr}<code>3505</code></li>
<li>{class}<code>Argument</code> accepts a <code>help</code> parameter, and help output includes
a <code>Positional arguments</code> section when argument help is available. {issue}<code>2983</code> {pr}<code>3473</code></li>
<li><code>confirm()</code> and <code>prompt()</code> strip ANSI color and style codes from the
prompt when the output stream does not support them, matching <code>echo()</code>.
This stripping was lost in <code>8.4.0</code> when {pr}<code>2969</code> began writing the
prompt with <code>input()</code> directly. {issue}<code>3572</code> {pr}<code>3653</code></li>
<li>Fix test failures when using pytest &gt;= 9.1. {pr}<code>3656</code></li>
<li>{class}<code>Path</code> with <code>allow_dash=True</code> no longer triggers a <code>BytesWarning</code>,
an error under <code>python -bb</code>, when checking a value against the <code>-</code>
convention. {issue}<code>2877</code> {pr}<code>3642</code></li>
<li>Add {func}<code>custom_version_option</code>, a <code>--version</code> option whose output is
produced by a callback, covering cases {func}<code>version_option</code> intentionally
does not. The feature set of {func}<code>version_option</code> is now frozen; see
[discussion <a href="">#3527</a>](<a href="https://github.com/pallets/click/discussions/3527">https://github.com/pallets/click/discussions/3527</a>). {pr}<code>3581</code></li>
<li><code>style()</code> and <code>secho()</code> no longer silently drop the 256-color index <code>0</code>
(black) passed as <code>fg</code> or <code>bg</code>, and now validate color arguments. Invalid
colors raise a <code>ValueError</code> instead of a <code>TypeError</code>. {pr}<code>3677</code></li>
<li>The automatic help option stores its value under the reserved name
<code>_click_default_help</code> instead of <code>help</code>, so a parameter named <code>help</code> no
longer breaks parsing. The new name is visible in
{meth}<code>Command.to_info_dict</code> output. Parameters that overwrite each other's
value trigger a warning: an argument sharing its name with another
parameter, or any parameter claiming the reserved name. Options may still
share a name to compete for the same value (feature switches).
{issue}<code>2819</code> {pr}<code>3678</code></li>
<li><code>unstyle</code> and the ANSI handling behind help-text wrapping now strip the full
CSI escape-sequence grammar. {pr}<code>3681</code></li>
<li>Streamline <code>Option</code> flag handling: the flag-kind, type, lazy-default and
validation steps in <code>Option.__init__</code> move into focused helpers, and
<code>flag_value</code> and <code>default</code> keep their unset sentinel at construction
(resolved lazily on read) so <code>is UNSET</code> reliably tells a user-supplied value
from an auto-derived one. Runtime behavior is unchanged, but
{meth}<code>Parameter.to_info_dict</code> now resolves <code>default=True</code> on a feature
switch to its <code>flag_value</code>, matching what the function receives at call
time. {pr}<code>3641</code></li>
<li>{func}<code>get_binary_stream</code> and {func}<code>get_text_stream</code> are deprecated and
will be removed in Click 9.0. {issue}<code>3481</code> {pr}<code>3695</code></li>
<li>The following <code>click.utils</code> names were never intentionally public and are
now private (<code>_</code>-prefixed). The old names remain available with a
<code>DeprecationWarning</code> until Click 9.0: <code>LazyFile</code>, <code>KeepOpenFile</code>,</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>8b19813</code></a> Release version 8.5.0</li>
<li><a href=""><code>2c8cd3a</code></a> Add FAQ entry about <code>UnicodeEncodeError</code> on Windows (<a href="">#3778</a>)</li>
<li><a href=""><code>131c86a</code></a> Add FAQ entry about <code>UnicodeEncodeError</code> on Windows</li>
<li><a href=""><code>e1fd594</code></a> Add support of <code>pathlib.Path</code> to <code>edit</code> (<a href="">#3781</a>)</li>
<li><a href=""><code>a1d8785</code></a> Add support of <code>pathlib.Path</code> to <code>edit</code></li>
<li><a href=""><code>2103e15</code></a> Forward all user's parameters set in <code>PAGER</code> and improve flag detection (<a href="">#3777</a>)</li>
<li><a href=""><code>a6256bf</code></a> Forwards all user's parameters set in <code>PAGER</code></li>
<li><a href=""><code>61b69e9</code></a> Resolve the pager command once, in <code>_pager_contextmanager</code> (<a href="">#3776</a>)</li>
<li><a href=""><code>9835b0f</code></a> Resolve the pager command once, in <code>_pager_contextmanager</code></li>
<li><a href=""><code>f36d58b</code></a> Refactor pager stream handling (<a href="">#3767</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/pallets/click/compare/8.4.2...8.5.0">compare view</a></li>
</ul>
</details>
<br />

Updates `pylint` from 4.0.7 to 4.0.8
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pylint-dev/pylint/releases">pylint's releases</a>.</em></p>
<blockquote>
<h2>v4.0.8</h2>
<h2>What's new in Pylint 4.0.8?</h2>
<p>Release date: 2026-08-29</p>
<h2>False Positives Fixed</h2>
<ul>
<li>
<p>Fix a false positive for :ref:<code>unspecified-encoding</code> when an <code>open</code> call uses a mode
argument that cannot be inferred.</p>
<p>Closes <a href="">#10201</a></p>
</li>
<li>
<p>Fix a false positive for <code>invalid-name</code> (C0103) on names assigned in an
<code>if __name__ == &quot;__main__&quot;:</code> block. Such a block reads like a script body, so
a name there is now accepted if it matches either the constant or the variable
naming style.</p>
<p>Closes <a href="">#10766</a></p>
</li>
<li>
<p>Fix false positives for :ref:<code>invalid-str-returned</code>, :ref:<code>invalid-repr-returned</code>,
:ref:<code>invalid-format-returned</code>, :ref:<code>invalid-bytes-returned</code>, :ref:<code>invalid-hash-returned</code>,
:ref:<code>invalid-index-returned</code>, :ref:<code>invalid-length-returned</code>,
:ref:<code>invalid-length-hint-returned</code>, :ref:<code>invalid-getnewargs-returned</code> and
:ref:<code>invalid-getnewargs-ex-returned</code> when the returned value is an instance of a
subclass of the expected builtin type, such as <code>self</code> in a <code>str</code> subclass or a
<code>namedtuple</code>.</p>
<p>Closes <a href="">#11306</a></p>
</li>
<li>
<p>Fix false positives for :ref:<code>bad-string-format-type</code> when the argument is an
instance of a subclass of <code>int</code>, <code>float</code> or <code>str</code>, such as <code>bool</code> or an
<code>IntEnum</code> member formatted with <code>%d</code>.</p>
<p>Closes <a href="">#11315</a></p>
</li>
</ul>
<h2>False Negatives Fixed</h2>
<ul>
<li>
<p><code>redundant-unittest-assert</code> now also flags <code>assertEqual</code> and <code>assertNotEqual</code>
when both compared values are constants, e.g. <code>self.assertEqual(5, 5)</code>.</p>
<p>Closes <a href="">#11321</a></p>
</li>
</ul>
<p>Other Bug Fixes</p>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>ecb84ba</code></a> Bump pylint to 4.0.8, update changelog (<a href="">#11355</a>)</li>
<li><a href=""><code>989e9c5</code></a> [Backport maintenance/4.0.x] Support isort 9 (<a href="">#11354</a>)</li>
<li><a href=""><code>8c1ee95</code></a> Flag assertEqual and assertNotEqual between two constants in W1503</li>
<li><a href=""><code>eadefe3</code></a> Fix false positive bad-string-format-type for subclasses of builtin types</li>
<li><a href=""><code>db00e3b</code></a> [Backport maintenance/4.0.x] fix(docparams): guard decorated_with_property ag...</li>
<li><a href=""><code>7909c17</code></a> Accept subclass instances in the invalid-*-returned checks</li>
<li><a href=""><code>d19640d</code></a> [Backport maintenance/4.0.x] Fix <code>invalid-name</code> false positive in `if _<em>name</em>...</li>
<li><a href=""><code>94e5704</code></a> Skip unspecified-encoding for unknown open modes (<a href="">#11163</a>)</li>
<li><a href=""><code>d59b329</code></a> fix(refactoring): handle non-AssignName targets in use-yield-from (<a href="">#11286</a>) (#...</li>
<li><a href=""><code>eea0569</code></a> [Backport maintenance/4.0.x] Fix crash in docparams on raising a non-exceptio...</li>
<li>See full diff in <a href="https://github.com/pylint-dev/pylint/compare/v4.0.7...v4.0.8">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.4 to 0.16.5
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.5</h2>
<h2>Release Notes</h2>
<p>Released on 2026-08-27.</p>
<h3>Preview features</h3>
<ul>
<li>Allow rules without codes (<a href="">#28049</a>)</li>
<li>Introduce category selectors (<a href="">#27666</a>)</li>
<li>Update preview default rules and categories (<a href="">#27877</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-async</code>] Detect blocking generic HTTP requests (<code>ASYNC210</code>) (<a href="">#28024</a>)</li>
<li>[<code>flake8-datetimez</code>] Allow timezone-safe <code>strptime</code> chains (<code>DTZ007</code>) (<a href="">#28023</a>)</li>
<li>[<code>flake8-simplify</code>] Respect side effects in <code>lambda</code> defaults (<code>SIM401</code>) (<a href="">#28000</a>)</li>
</ul>
<h3>Server</h3>
<ul>
<li>Fix duplicated &quot;of&quot; in <code>ClientOptions</code> doc comment (<a href="">#27978</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Document rule acceptance guidelines (<a href="">#27910</a>)</li>
<li>Document the new category selectors (<a href="">#27906</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/AlexWaygood"><code>@​AlexWaygood</code></a></li>
<li><a href="https://github.com/sharkdp"><code>@​sharkdp</code></a></li>
<li><a href="https://github.com/jelle-openai"><code>@​jelle-openai</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/aarushkandukoori"><code>@​aarushkandukoori</code></a></li>
</ul>
<h2>Install ruff 0.16.5</h2>
<h3>Install prebuilt binaries via shell script</h3>
<pre lang="sh"><code>curl --proto '=https' --tlsv1.2 -LsSf https://releases.astral.sh/github/ruff/releases/download/0.16.5/ruff-installer.sh | sh
</code></pre>
<h3>Install prebuilt binaries via powershell script</h3>
<pre lang="sh"><code>powershell -ExecutionPolicy Bypass -c &quot;irm https://releases.astral.sh/github/ruff/releases/download/0.16.5/ruff-installer.ps1 | iex&quot;
</code></pre>
<h2>Download ruff 0.16.5</h2>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.5</h2>
<p>Released on 2026-08-27.</p>
<h3>Preview features</h3>
<ul>
<li>Allow rules without codes (<a href="">#28049</a>)</li>
<li>Introduce category selectors (<a href="">#27666</a>)</li>
<li>Update preview default rules and categories (<a href="">#27877</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>[<code>flake8-async</code>] Detect blocking generic HTTP requests (<code>ASYNC210</code>) (<a href="">#28024</a>)</li>
<li>[<code>flake8-datetimez</code>] Allow timezone-safe <code>strptime</code> chains (<code>DTZ007</code>) (<a href="">#28023</a>)</li>
<li>[<code>flake8-simplify</code>] Respect side effects in <code>lambda</code> defaults (<code>SIM401</code>) (<a href="">#28000</a>)</li>
</ul>
<h3>Server</h3>
<ul>
<li>Fix duplicated &quot;of&quot; in <code>ClientOptions</code> doc comment (<a href="">#27978</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Document rule acceptance guidelines (<a href="">#27910</a>)</li>
<li>Document the new category selectors (<a href="">#27906</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/AlexWaygood"><code>@​AlexWaygood</code></a></li>
<li><a href="https://github.com/sharkdp"><code>@​sharkdp</code></a></li>
<li><a href="https://github.com/jelle-openai"><code>@​jelle-openai</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/aarushkandukoori"><code>@​aarushkandukoori</code></a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>9e4938c</code></a> Bump 0.16.5 (<a href="">#28110</a>)</li>
<li><a href=""><code>aad0e90</code></a> Allow rules without codes (<a href="">#28049</a>)</li>
<li><a href=""><code>5fdab73</code></a> Update preview default rules and categories (<a href="">#27877</a>)</li>
<li><a href=""><code>29c8e5b</code></a> Document rule acceptance guidelines (<a href="">#27910</a>)</li>
<li><a href=""><code>50a4d7f</code></a> Document the new category selectors (<a href="">#27906</a>)</li>
<li><a href=""><code>ada8795</code></a> Introduce category selectors (<a href="">#27666</a>)</li>
<li><a href=""><code>d894723</code></a> [ty] Infer lambda parameters through callable type aliases (<a href="">#28109</a>)</li>
<li><a href=""><code>2685fde</code></a> [ty] Narrow functional enum members in <code>==</code> and <code>match</code> (<a href="">#28103</a>)</li>
<li><a href=""><code>efcffd2</code></a> [ty] Intersection simplifications with subtype-related generic specialization...</li>
<li><a href=""><code>eb78048</code></a> [ty] Bump ecosystem-analyzer for HTML escaping (<a href="">#28104</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.4...0.16.5">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `c068568bbeaa`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.