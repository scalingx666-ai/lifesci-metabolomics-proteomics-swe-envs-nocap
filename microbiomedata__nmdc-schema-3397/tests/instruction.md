# Issue

**Title:** Bump the python-dependencies group with 2 updates

## Description

Bumps the python-dependencies group with 2 updates: [pymongo](https://github.com/mongodb/mongo-python-driver) and [ruff](https://github.com/astral-sh/ruff).

Updates `pymongo` from 4.17.0 to 4.18.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/releases">pymongo's releases</a>.</em></p>
<blockquote>
<h2>PyMongo 4.18.0</h2>
<p>Community notes: <a href="https://www.mongodb.com/community/forums/t/pymongo-4-18-released/343137">https://www.mongodb.com/community/forums/t/pymongo-4-18-released/343137</a></p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/mongodb/mongo-python-driver/blob/main/doc/changelog.rst">pymongo's changelog</a>.</em></p>
<blockquote>
<h2>Changes in Version 4.18.0 (2026/09/03)</h2>
<p>PyMongo 4.18 brings a number of changes including:</p>
<ul>
<li>Added <code>srvAllowedHostsSuffix</code> as a URI option and keyword argument to
:class:<code>~pymongo.synchronous.mongo_client.MongoClient</code> and
:class:<code>~pymongo.asynchronous.mongo_client.AsyncMongoClient</code>. When connecting
via <code>mongodb+srv://</code>, this option overrides the default requirement that
SRV-returned hosts share the same parent domain as the seed hostname,
allowing hosts under a different domain suffix to be accepted. The suffix must
not be a public suffix (per the <code>Public Suffix List &lt;https://publicsuffix.org/list/&gt;</code>_). See the
:class:<code>~pymongo.synchronous.mongo_client.MongoClient</code> and
:class:<code>~pymongo.asynchronous.mongo_client.AsyncMongoClient</code> documentation for
security considerations.</li>
<li>Dropped support for MongoDB 4.2.</li>
<li>Added support for MongoDB 9.0.</li>
<li>PyPy support is deprecated and will be removed in a future release.</li>
<li>Improved TLS connection performance by reusing TLS sessions across connections
to the same server, avoiding a full handshake on each new connection.
Session resumption is supported on all Python versions for synchronous clients
and on Python 3.11+ for async clients.</li>
<li>Improved performance for MongoDB 9.0's Intelligent Workload Management (IWM) by only retrying overload errors when doing so is expected to not worsen server conditions.</li>
<li>Added support for exhaust cursors (:attr:<code>~pymongo.cursor.CursorType.EXHAUST</code>)
against mongos 7.1+. An older mongos still raises
:class:<code>~pymongo.errors.InvalidOperation</code>, now on the first iteration of the
cursor rather than from
:meth:<code>~pymongo.synchronous.collection.Collection.find</code>, since the requirement
is checked against the connection in use. Separately, async cursors combining
<code>limit</code> with :attr:<code>~pymongo.cursor.CursorType.EXHAUST</code> now raise at <code>find</code>
rather than on first iteration, matching the synchronous API.</li>
<li>Redacted potentially sensitive authentication mechanism properties, including
AWS session tokens, from the representations of
:class:<code>~pymongo.synchronous.mongo_client.MongoClient</code> and
:class:<code>~pymongo.asynchronous.mongo_client.AsyncMongoClient</code>.</li>
<li>Command monitoring events and command log messages for a single logical
operation now share one stable <code>operation_id</code> across all of its retry
attempts, so consumers can correlate a retried operation's events. As a
result, <code>operation_id</code> is no longer equal to the per-attempt <code>request_id</code>
for these operations.</li>
<li>Added validation of OP_COMPRESSED decompressed message size against
<code>max_message_size</code> to prevent memory exhaustion from maliciously crafted
compressed server responses.</li>
<li>Improved the performance and memory usage of decoding large documents to
:class:<code>~bson.raw_bson.RawBSONDocument</code>. Documents and subdocuments that are 4KB or greater
and decoded from an immutable buffer are now exposed as read-only :class:<code>memoryview</code>
slices instead of :class:<code>bytes</code> copies. Documents decoded from mutable buffers such as a
:class:<code>bytearray</code> are always :class:<code>bytes</code> copies.</li>
<li>:func:<code>bson.get_data_and_view</code> now returns a view of a private :class:<code>bytes</code> copy</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>8e7ece4</code></a> PYTHON-6072 - Update changelog for 4.18 release (<a href="">#3038</a>)</li>
<li><a href=""><code>f4d0ca6</code></a> PYTHON-5814 Configurable DNS domain validation for SRV records (<a href="">#2868</a>)</li>
<li><a href=""><code>3ed144a</code></a> PYTHON-6070 Improve help output for just run-server and just setup-tests (<a href="">#3035</a>)</li>
<li><a href=""><code>003c9cc</code></a> PYTHON-6020 Move _have_dnspython into uri_parser_shared.py (<a href="">#3032</a>)</li>
<li><a href=""><code>a3c768d</code></a> PYTHON-5983 Validate uncompressed size in OP_COMPRESSED messages (<a href="">#2976</a>)</li>
<li><a href=""><code>1a99d50</code></a> PYTHON 5790 Standardize references to test collections in tests (<a href="">#3026</a>)</li>
<li><a href=""><code>364c1ea</code></a> PYTHON-5884 Explicit Encryption prose test &quot;Case 2&quot; fails on latest server: p...</li>
<li><a href=""><code>cc5deb2</code></a> PYTHON-6017 Consolidate QE enums into shared class (<a href="">#3024</a>)</li>
<li><a href=""><code>6506f48</code></a> PYTHON-6007 Fix versionchanged marker for text_opts in ClientEncryption.encry...</li>
<li><a href=""><code>f9f9b03</code></a> PYTHON-6019 Consolidate mongo_client module-level helpers into shared… (<a href="">#3031</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/mongodb/mongo-python-driver/compare/4.17.0...4.18.0">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.5 to 0.16.6
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.6</h2>
<h2>Release Notes</h2>
<p>Released on 2026-09-03.</p>
<h3>Preview features</h3>
<ul>
<li>Move <code>pytest-fixture-autouse</code> to the <code>restriction</code> category (<a href="">#28219</a>)</li>
<li>[<code>flake8-pytest-style</code>] Add an autofix for <code>PT020</code> (<a href="">#27993</a>)</li>
<li>[<code>flake8-tidy-imports</code>] Prevent fix loop between <code>TID254</code> and <code>TID255</code> (<a href="">#28262</a>)</li>
<li>[<code>isort</code>] Exclude pragma comments from line length calculation (<code>I001</code>) (<a href="">#27313</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Validate unary expressions when parsing (<a href="">#28233</a>)</li>
<li>[<code>flake8-async</code>, <code>pylint</code>] Recognize <code>builtins.open</code> (<code>ASYNC230</code>, <code>PLW1514</code>) (<a href="">#28021</a>)</li>
<li>[<code>flake8-bugbear</code>] Fix panic on <code>match</code> subjects (<code>B031</code>) (<a href="">#27781</a>)</li>
<li>[<code>flake8-datetimez</code>] Reject <code>tzinfo=None</code> for <code>datetime</code> bounds (<code>DTZ901</code>) (<a href="">#28022</a>)</li>
<li>[<code>flake8-pytest-style</code>] Avoid duplicate <code>PT017</code> diagnostics (<a href="">#27918</a>)</li>
<li>[<code>ruff</code>] Remove <code>lint.external</code> hint for Ruff-specific suppressions (<code>RUF102</code>) (<a href="">#27923</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-use-pathlib</code>] Add display-only fix for <code>os.listdir</code> (<code>PTH208</code>) (<a href="">#28027</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Add another example and glob reference for <code>lint.per-file-ignores</code> (<a href="">#28106</a>)</li>
<li>Add duplicate work guidance (<a href="">#28229</a>)</li>
<li>[<code>flake8-async</code>] Document thread offloading (<code>ASYNC240</code>) (<a href="">#28008</a>)</li>
<li>[<code>pyupgrade</code>] Clarify default <code>encoding</code> argument handling (<code>UP012</code>) (<a href="">#27315</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Allow unary plus in match patterns on Python 3.15 (<a href="">#28231</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/flying-sheep"><code>@​flying-sheep</code></a></li>
<li><a href="https://github.com/pikammmmm"><code>@​pikammmmm</code></a></li>
<li><a href="https://github.com/fly1d"><code>@​fly1d</code></a></li>
<li><a href="https://github.com/waterWang"><code>@​waterWang</code></a></li>
<li><a href="https://github.com/Pierre-Sassoulas"><code>@​Pierre-Sassoulas</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/jelle-openai"><code>@​jelle-openai</code></a></li>
<li><a href="https://github.com/ericbuehl"><code>@​ericbuehl</code></a></li>
<li><a href="https://github.com/tjkuson"><code>@​tjkuson</code></a></li>
<li><a href="https://github.com/AbhinavMir"><code>@​AbhinavMir</code></a></li>
<li><a href="https://github.com/Whning0513"><code>@​Whning0513</code></a></li>
<li><a href="https://github.com/chirizxc"><code>@​chirizxc</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.6</h2>
<p>Released on 2026-09-03.</p>
<h3>Preview features</h3>
<ul>
<li>Move <code>pytest-fixture-autouse</code> to the <code>restriction</code> category (<a href="">#28219</a>)</li>
<li>[<code>flake8-pytest-style</code>] Add an autofix for <code>PT020</code> (<a href="">#27993</a>)</li>
<li>[<code>flake8-tidy-imports</code>] Prevent fix loop between <code>TID254</code> and <code>TID255</code> (<a href="">#28262</a>)</li>
<li>[<code>isort</code>] Exclude pragma comments from line length calculation (<code>I001</code>) (<a href="">#27313</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Validate unary expressions when parsing (<a href="">#28233</a>)</li>
<li>[<code>flake8-async</code>, <code>pylint</code>] Recognize <code>builtins.open</code> (<code>ASYNC230</code>, <code>PLW1514</code>) (<a href="">#28021</a>)</li>
<li>[<code>flake8-bugbear</code>] Fix panic on <code>match</code> subjects (<code>B031</code>) (<a href="">#27781</a>)</li>
<li>[<code>flake8-datetimez</code>] Reject <code>tzinfo=None</code> for <code>datetime</code> bounds (<code>DTZ901</code>) (<a href="">#28022</a>)</li>
<li>[<code>flake8-pytest-style</code>] Avoid duplicate <code>PT017</code> diagnostics (<a href="">#27918</a>)</li>
<li>[<code>ruff</code>] Remove <code>lint.external</code> hint for Ruff-specific suppressions (<code>RUF102</code>) (<a href="">#27923</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-use-pathlib</code>] Add display-only fix for <code>os.listdir</code> (<code>PTH208</code>) (<a href="">#28027</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Add another example and glob reference for <code>lint.per-file-ignores</code> (<a href="">#28106</a>)</li>
<li>Add duplicate work guidance (<a href="">#28229</a>)</li>
<li>[<code>flake8-async</code>] Document thread offloading (<code>ASYNC240</code>) (<a href="">#28008</a>)</li>
<li>[<code>pyupgrade</code>] Clarify default <code>encoding</code> argument handling (<code>UP012</code>) (<a href="">#27315</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Allow unary plus in match patterns on Python 3.15 (<a href="">#28231</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/flying-sheep"><code>@​flying-sheep</code></a></li>
<li><a href="https://github.com/pikammmmm"><code>@​pikammmmm</code></a></li>
<li><a href="https://github.com/fly1d"><code>@​fly1d</code></a></li>
<li><a href="https://github.com/waterWang"><code>@​waterWang</code></a></li>
<li><a href="https://github.com/Pierre-Sassoulas"><code>@​Pierre-Sassoulas</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/jelle-openai"><code>@​jelle-openai</code></a></li>
<li><a href="https://github.com/ericbuehl"><code>@​ericbuehl</code></a></li>
<li><a href="https://github.com/tjkuson"><code>@​tjkuson</code></a></li>
<li><a href="https://github.com/AbhinavMir"><code>@​AbhinavMir</code></a></li>
<li><a href="https://github.com/Whning0513"><code>@​Whning0513</code></a></li>
<li><a href="https://github.com/chirizxc"><code>@​chirizxc</code></a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>22f65a2</code></a> Bump 0.16.6 (<a href="">#28280</a>)</li>
<li><a href=""><code>7cc9f1e</code></a> [ty] Document <code>CallableTypeKind</code> variants (<a href="">#28277</a>)</li>
<li><a href=""><code>056ce07</code></a> Add UV_LOCKED to all workflows (<a href="">#28261</a>)</li>
<li><a href=""><code>6d6e35d</code></a> [<code>flake8-pytest-style</code>] Avoid duplicate <code>PT017</code> diagnostics (<a href="">#27918</a>)</li>
<li><a href=""><code>80b4891</code></a> [ty] Temporarily disable tuple types in property tests (<a href="">#28275</a>)</li>
<li><a href=""><code>3f7a54d</code></a> [<code>flake8-tidy-imports</code>] Prevent fix loop between <code>TID254</code> and <code>TID255</code> (<a href="">#28262</a>)</li>
<li><a href=""><code>35656cf</code></a> [ty] Preserve deprecations on decorated callables (<a href="">#28256</a>)</li>
<li><a href=""><code>d2626c8</code></a> [ty] Reject missing attributes on <code>type[]</code> aliases (<a href="">#28267</a>)</li>
<li><a href=""><code>ee6a6d1</code></a> [ty] Support ParamSpecs in <code>ConstraintSet</code> (<a href="">#28028</a>)</li>
<li><a href=""><code>7f6a170</code></a> [ty] Move bound APIs to constraint owners (<a href="">#28094</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.5...0.16.6">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `a4fff7dcf2a8`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.