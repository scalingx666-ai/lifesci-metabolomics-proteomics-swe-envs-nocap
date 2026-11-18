# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [pymongo](https://github.com/mongodb/mongo-python-driver), [psycopg2-binary](https://github.com/psycopg/psycopg2) and [ruff](https://github.com/astral-sh/ruff).

Updates `pymongo` from 4.18.0 to 4.18.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/releases">pymongo's releases</a>.</em></p>
<blockquote>
<h2>PyMongo 4.18.1</h2>
<p>Community notes: <a href="https://www.mongodb.com/community/forums/t/pymongo-4-18-1-released/343338">https://www.mongodb.com/community/forums/t/pymongo-4-18-1-released/343338</a></p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/blob/main/doc/changelog.rst">pymongo's changelog</a>.</em></p>
<blockquote>
<h2>Changes in Version 4.18.1 (2026/09/10)</h2>
<p>Version 4.18.1 is a bug fix release.</p>
<ul>
<li>Use an exact match for the file ID in GridFS delete methods
(<code>CVE-2026-88029</code>_).</li>
</ul>
<p>.. _CVE-2026-88029: <a href="https://www.cve.org/CVERecord?id=CVE-2026-88029">https://www.cve.org/CVERecord?id=CVE-2026-88029</a></p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>127d140</code></a> PYTHON-6085 Prep for 4.18.1 release (<a href="">#3047</a>)</li>
<li><a href=""><code>fa67658</code></a> PYTHON-5994 Use exact match for file ID in GridFS delete methods (<a href="">#3046</a>)</li>
<li><a href=""><code>1011e57</code></a> Prep branch v4.18</li>
<li><a href=""><code>4dd7303</code></a> PYTHON-6076 Request workflows permission in create-release-branch (<a href="">#3039</a>)</li>
<li><a href=""><code>e66da83</code></a> PYTHON-5956 Use shared python/setup action for CI setup (<a href="">#2990</a>)</li>
<li><a href=""><code>22a2ec8</code></a> PYTHON-6021 Move _write_concern_for_cmd into BaseObject (<a href="">#3036</a>)</li>
<li><a href=""><code>2a4a004</code></a> PYTHON-5874 Fix test_fork.py failures on Python 3.15 due to fork() Deprecatio...</li>
<li><a href=""><code>0f6da1c</code></a> PYTHON-6071 Fix ML-KEM OCSP tests and run min-deps OCSP task on PRs (<a href="">#3037</a>)</li>
<li><a href=""><code>3890060</code></a> BUMP 4.19.0.dev0</li>
<li>See full diff in <a href="https://github.com/mongodb/mongo-python-driver/compare/4.18.0...4.18.1">compare view</a></li>
</ul>
</details>
<br />

Updates `psycopg2-binary` from 2.9.12 to 2.9.13
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/psycopg/psycopg2/blob/master/NEWS">psycopg2-binary's changelog</a>.</em></p>
<blockquote>
<h2>Current release</h2>
<p>What's new in psycopg 2.9.13
^^^^^^^^^^^^^^^^^^^^^^^^^^^^</p>
<ul>
<li>Add support for Python 3.15 (:ticket:<code></code>).</li>
<li>Fix parsing of malformed bytea input.</li>
<li>Fix parsing of malformed int64 input in arrays (:ticket:<code></code>).</li>
<li>Add a <code>pyproject.toml</code> file to declare a PEP 517 build backend
(:ticket:<code></code>).</li>
<li>Drop support for Python 3.9.</li>
</ul>
<p>What's new in psycopg 2.9.12
^^^^^^^^^^^^^^^^^^^^^^^^^^^^</p>
<ul>
<li>Fix infinite loop with malformed interval (:ticket:<code>1835</code>).</li>
</ul>
<p>What's new in psycopg 2.9.11
^^^^^^^^^^^^^^^^^^^^^^^^^^^^</p>
<ul>
<li>Add support for Python 3.14.</li>
<li>Avoid a segfault passing more arguments than placeholders if Python is built
with assertions enabled (:ticket:<code></code>).</li>
<li>Add riscv64 platform binary packages (:ticket:<code></code>).</li>
<li><code>~psycopg2.errorcodes</code> map and <code>~psycopg2.errors</code> classes updated to
PostgreSQL 18.</li>
<li>Drop support for Python 3.8.</li>
</ul>
<p>What's new in psycopg 2.9.10
^^^^^^^^^^^^^^^^^^^^^^^^^^^^</p>
<ul>
<li>Add support for Python 3.13.</li>
<li>Receive notifications on commit (:ticket:<code></code>).</li>
<li><code>~psycopg2.errorcodes</code> map and <code>~psycopg2.errors</code> classes updated to
PostgreSQL 17.</li>
<li>Drop support for Python 3.7.</li>
</ul>
<p>What's new in psycopg 2.9.9
^^^^^^^^^^^^^^^^^^^^^^^^^^^</p>
<ul>
<li>Add support for Python 3.12.</li>
<li>Drop support for Python 3.6.</li>
</ul>
<p>What's new in psycopg 2.9.8</p>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>f650e7a</code></a> chore: bump to release 2.9.13</li>
<li><a href=""><code>368c8a1</code></a> chore!: drop support for Python 3.9</li>
<li><a href=""><code>9b39e65</code></a> chore: drop scaleway build support</li>
<li><a href=""><code>2ca7041</code></a> fix: fix handling of PostgreSQL 18 exceptions</li>
<li><a href=""><code>5385c02</code></a> Build CPython 3.15 wheels</li>
<li><a href=""><code>1d32e1f</code></a> ci: only attempt triggering documentation refresh when pushing on main repo</li>
<li><a href=""><code>433e7b7</code></a> chore: add pyproject.toml file to declare a PEP 517 build backend</li>
<li><a href=""><code>8fb80bc</code></a> fix: fix parsing of malformed int64 input in arrays</li>
<li><a href=""><code>f98014a</code></a> fix: fix parsing of malformed bytea input</li>
<li><a href=""><code>822b79c</code></a> chore: bump dependencies in binary package</li>
<li>Additional commits viewable in <a href="https://github.com/psycopg/psycopg2/compare/2.9.12...2.9.13">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.6 to 0.16.7
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.7</h2>
<h2>Release Notes</h2>
<p>Released on 2026-09-10.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>ruff</code>] Add rule for default values on method receivers (<code>RUF077</code>) (<a href="">#26700</a>)</li>
<li>[<code>ruff</code>] Recognize <code>re.prefixmatch</code> (<code>RUF039</code>, <code>RUF055</code>) (<a href="">#28311</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Alternate nested quotes inside format spec interpolations (<a href="">#28259</a>)</li>
<li>[<code>flake8-implicit-str-concat</code>] Mark fix unsafe when it creates a docstring (<code>ISC003</code>) (<a href="">#27981</a>)</li>
<li>[<code>flake8-tidy-imports</code>] Skip fixes for multi-member imports (<code>TID254</code>) (<a href="">#26584</a>)</li>
<li>[<code>pylint</code>] Gate <code>ImportCycleError</code> on Python 3.15 (<code>PLW0133</code>) (<a href="">#28310</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Correct <code>D211</code> and <code>D203</code> rule conflict diagnostic (<a href="">#28444</a>)</li>
<li>Recognize <code>slice</code> and <code>frozendict</code> generics (<a href="">#28477</a>)</li>
<li>Stop defining <code>__cached__</code> for Python 3.15 (<a href="">#28476</a>)</li>
<li>[<code>pyupgrade</code>] Stop recommending removed <code>typing.no_type_check_decorator</code> (<code>UP035</code>) (<a href="">#28475</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Reuse parser name lookups when interning (<a href="">#28399</a>)</li>
<li>Speed up inherited configuration resolution (<a href="">#28299</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Fix <code>line-length</code> path in <code>--config</code> example (<a href="">#28392</a>)</li>
<li>Remove the &quot;Who’s Using Ruff?&quot; list (<a href="">#28455</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Embed archive checksums in the shell installer (<a href="">#28281</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/The-Compiler"><code>@​The-Compiler</code></a></li>
<li><a href="https://github.com/mdiniz97"><code>@​mdiniz97</code></a></li>
<li><a href="https://github.com/zsol"><code>@​zsol</code></a></li>
<li><a href="https://github.com/gorewilliams"><code>@​gorewilliams</code></a></li>
<li><a href="https://github.com/RafaelJohn9"><code>@​RafaelJohn9</code></a></li>
<li><a href="https://github.com/qatcod"><code>@​qatcod</code></a></li>
<li><a href="https://github.com/zanieb"><code>@​zanieb</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
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
<h2>0.16.7</h2>
<p>Released on 2026-09-10.</p>
<h3>Preview features</h3>
<ul>
<li>[<code>ruff</code>] Add rule for default values on method receivers (<code>RUF077</code>) (<a href="">#26700</a>)</li>
<li>[<code>ruff</code>] Recognize <code>re.prefixmatch</code> (<code>RUF039</code>, <code>RUF055</code>) (<a href="">#28311</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Alternate nested quotes inside format spec interpolations (<a href="">#28259</a>)</li>
<li>[<code>flake8-implicit-str-concat</code>] Mark fix unsafe when it creates a docstring (<code>ISC003</code>) (<a href="">#27981</a>)</li>
<li>[<code>flake8-tidy-imports</code>] Skip fixes for multi-member imports (<code>TID254</code>) (<a href="">#26584</a>)</li>
<li>[<code>pylint</code>] Gate <code>ImportCycleError</code> on Python 3.15 (<code>PLW0133</code>) (<a href="">#28310</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Correct <code>D211</code> and <code>D203</code> rule conflict diagnostic (<a href="">#28444</a>)</li>
<li>Recognize <code>slice</code> and <code>frozendict</code> generics (<a href="">#28477</a>)</li>
<li>Stop defining <code>__cached__</code> for Python 3.15 (<a href="">#28476</a>)</li>
<li>[<code>pyupgrade</code>] Stop recommending removed <code>typing.no_type_check_decorator</code> (<code>UP035</code>) (<a href="">#28475</a>)</li>
</ul>
<h3>Performance</h3>
<ul>
<li>Reuse parser name lookups when interning (<a href="">#28399</a>)</li>
<li>Speed up inherited configuration resolution (<a href="">#28299</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Fix <code>line-length</code> path in <code>--config</code> example (<a href="">#28392</a>)</li>
<li>Remove the &quot;Who’s Using Ruff?&quot; list (<a href="">#28455</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Embed archive checksums in the shell installer (<a href="">#28281</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/The-Compiler"><code>@​The-Compiler</code></a></li>
<li><a href="https://github.com/mdiniz97"><code>@​mdiniz97</code></a></li>
<li><a href="https://github.com/zsol"><code>@​zsol</code></a></li>
<li><a href="https://github.com/gorewilliams"><code>@​gorewilliams</code></a></li>
<li><a href="https://github.com/RafaelJohn9"><code>@​RafaelJohn9</code></a></li>
<li><a href="https://github.com/qatcod"><code>@​qatcod</code></a></li>
<li><a href="https://github.com/zanieb"><code>@​zanieb</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/nightt5879"><code>@​nightt5879</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>b5dba86</code></a> Bump version to 0.16.7 (<a href="">#28496</a>)</li>
<li><a href=""><code>5992d05</code></a> Install rustfmt before linting releases (<a href="">#28495</a>)</li>
<li><a href=""><code>1713a1f</code></a> ensure prepare release changes pass prek (<a href="">#28488</a>)</li>
<li><a href=""><code>18cdbb4</code></a> use scoped token for release workflow (<a href="">#28484</a>)</li>
<li><a href=""><code>c3813a5</code></a> add a workflow for preparing releases (<a href="">#28486</a>)</li>
<li><a href=""><code>00948c0</code></a> Remove the &quot;Who’s Using Ruff?&quot; list (<a href="">#28455</a>)</li>
<li><a href=""><code>86a2eba</code></a> [<code>pyupgrade</code>] Stop recommending removed <code>typing.no_type_check_decorator</code> (`UP...</li>
<li><a href=""><code>609e184</code></a> Stop defining <code>__cached__</code> for Python 3.15 (<a href="">#28476</a>)</li>
<li><a href=""><code>859ff2f</code></a> [ty] Track symlinked directory status in listings (<a href="">#28482</a>)</li>
<li><a href=""><code>77f6538</code></a> Use paid GitHub-hosted runners for Linux (<a href="">#28478</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.6...0.16.7">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `d41ef9577a33`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.