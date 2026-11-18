# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [curies](https://github.com/biopragmatics/curies), [oaklib](https://github.com/incatools/ontology-access-kit) and [ruff](https://github.com/astral-sh/ruff).

Updates `curies` from 0.14.1 to 0.14.5
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>3f37ec7</code></a> Bump version: 0.14.5-dev → 0.14.5</li>
<li><a href=""><code>2fde67a</code></a> Update vocabulary.py</li>
<li><a href=""><code>73baf91</code></a> Bump version: 0.14.4 → 0.14.5-dev</li>
<li><a href=""><code>85a44eb</code></a> Bump version: 0.14.4-dev → 0.14.4</li>
<li><a href=""><code>f24248d</code></a> Implement XSD string parser</li>
<li><a href=""><code>e81bc7e</code></a> Add missing type hint</li>
<li><a href=""><code>9dd4a2d</code></a> Bump version: 0.14.3 → 0.14.4-dev</li>
<li><a href=""><code>efa12d8</code></a> Bump version: 0.14.3-dev → 0.14.3</li>
<li><a href=""><code>f3b8f70</code></a> Extend XSD handling (<a href="">#234</a>)</li>
<li><a href=""><code>0cb7f1e</code></a> Bump version: 0.14.2 → 0.14.3-dev</li>
<li>Additional commits viewable in <a href="https://github.com/biopragmatics/curies/compare/v0.14.1...v0.14.5">compare view</a></li>
</ul>
</details>
<br />

Updates `oaklib` from 0.6.23 to 0.7.4
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/incatools/ontology-access-kit/releases">oaklib's releases</a>.</em></p>
<blockquote>
<h2>v0.7.4</h2>
<h2>What's Changed</h2>
<ul>
<li>Move <code>linkml</code> to dev dependency group by <a href="https://github.com/pkalita-lbl"><code>@​pkalita-lbl</code></a> in <a href="">INCATools/ontology-access-kit#906</a></li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/INCATools/ontology-access-kit/compare/v0.7.3...v0.7.4">https://github.com/INCATools/ontology-access-kit/compare/v0.7.3...v0.7.4</a></p>
<h2>v0.7.3 release</h2>
<h2>What's Changed</h2>
<ul>
<li>Remove curies upper pin and guard against pronto backtrack by <a href="https://github.com/matentzn"><code>@​matentzn</code></a> in <a href="">INCATools/ontology-access-kit#900</a></li>
<li>Adding Python 3.14 support by <a href="https://github.com/DnlRKorn"><code>@​DnlRKorn</code></a> in <a href="">INCATools/ontology-access-kit#902</a></li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/INCATools/ontology-access-kit/compare/v0.7.2...v0.7.3">https://github.com/INCATools/ontology-access-kit/compare/v0.7.2...v0.7.3</a></p>
<h2>v0.7.2</h2>
<h2>What's Changed</h2>
<ul>
<li>Enable parallel test execution and improve CI efficiency by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#890</a></li>
<li>Fix silent truncation of OLS descendant/ancestor closures to the first page by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#893</a></li>
<li>[codex] fix FunOWL search syntax and stub node regressions by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#891</a></li>
<li>Switch default sqlite location to the new semanticsql CDN URL (<a href="">#897</a>) by <a href="https://github.com/caufieldjh"><code>@​caufieldjh</code></a> in <a href="">INCATools/ontology-access-kit#898</a></li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/INCATools/ontology-access-kit/compare/v0.7.1...v0.7.2">https://github.com/INCATools/ontology-access-kit/compare/v0.7.1...v0.7.2</a></p>
<h2>v0.7.1</h2>
<h2>What's Changed</h2>
<ul>
<li>Fix bare string CURIE handling and OLS4 API compatibility by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#888</a></li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/INCATools/ontology-access-kit/compare/v0.7.0.0...v0.7.1">https://github.com/INCATools/ontology-access-kit/compare/v0.7.0.0...v0.7.1</a></p>
<h2>v0.7.0.0</h2>
<h2>What's Changed</h2>
<ul>
<li>Ensuring that pronto definition objects are stringified (730) by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#731</a></li>
<li>Adding a notebook demonstrating statistics command. by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#724</a></li>
<li>Fixed test by <a href="https://github.com/hrshdhgd"><code>@​hrshdhgd</code></a> in <a href="">INCATools/ontology-access-kit#723</a></li>
<li>Added <code>diff</code> markdown for <code>AddNodeToSubset</code> by <a href="https://github.com/hrshdhgd"><code>@​hrshdhgd</code></a> in <a href="">INCATools/ontology-access-kit#736</a></li>
<li>Ran formatter and minor code cleanup by <a href="https://github.com/hrshdhgd"><code>@​hrshdhgd</code></a> in <a href="">INCATools/ontology-access-kit#737</a></li>
<li>Adding definition validation functionality by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#738</a></li>
<li>Adding option for non-redundant entialed relationships. by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#740</a></li>
<li>Enriched mapping documentation by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#741</a></li>
<li>Adding defusedxml dependency. Fixes <a href="">#743</a> by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#744</a></li>
<li>Refactored <code>mappings</code> to more generic <code>relationships</code> in diff markdown output by <a href="https://github.com/hrshdhgd"><code>@​hrshdhgd</code></a> in <a href="">INCATools/ontology-access-kit#750</a></li>
<li>Update obo compliance suite using latest robot by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#747</a></li>
<li>Make ruff happy by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#757</a></li>
<li>Adding additional docs on the OAK expression language by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#749</a></li>
<li>Berkeley Hackathon: Enhancing semsim docs. by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#753</a></li>
<li>Adding skos-xref-duplicate to obo compliance suite by <a href="https://github.com/cmungall"><code>@​cmungall</code></a> in <a href="">INCATools/ontology-access-kit#752</a></li>
<li>Update to support new semsimian IC map functionality by <a href="https://github.com/caufieldjh"><code>@​caufieldjh</code></a> in <a href="">INCATools/ontology-access-kit#755</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>5a1570c</code></a> Move <code>linkml</code> to dev dependency group (<a href="">#906</a>)</li>
<li><a href=""><code>65c8760</code></a> Adding Python 3.14 support (<a href="">#902</a>)</li>
<li><a href=""><code>57a2ec0</code></a> Remove curies upper pin and guard against pronto backtrack (<a href="">#900</a>)</li>
<li><a href=""><code>f700060</code></a> Switch default sqlite location to the new semanticsql CDN URL (<a href="">#897</a>) (<a href="">#898</a>)</li>
<li><a href=""><code>d8ea39e</code></a> [codex] fix FunOWL search syntax and stub node regressions (<a href="">#891</a>)</li>
<li><a href=""><code>0a609ab</code></a> Fix silent truncation of OLS descendant/ancestor closures to the first page (...</li>
<li><a href=""><code>f6d0392</code></a> Enable parallel test execution and improve CI efficiency (<a href="">#890</a>)</li>
<li><a href=""><code>7dab07e</code></a> Fix bare string CURIE handling and OLS4 API compatibility (<a href="">#888</a>)</li>
<li><a href=""><code>3627fe6</code></a> Implement destructor for sqlite session and engine cleanup (<a href="">#846</a>)</li>
<li><a href=""><code>1e6bc84</code></a> Increase default cache TTL from 1 week to 1 month (<a href="">#879</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/incatools/ontology-access-kit/compare/v0.6.23...v0.7.4">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.0 to 0.16.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.1</h2>
<h2>Release Notes</h2>
<p>Released on 2026-07-30.</p>
<h3>Preview features</h3>
<ul>
<li>Add an option to opt out of human-readable names (<a href="">#27160</a>)</li>
<li>[<code>flake8-pytest-style</code>] Make fixes safe by default and unsafe only when comments are present (<code>PT018</code>) (<a href="">#27201</a>)</li>
<li>[<code>pyupgrade</code>] Skip fix when a defaulted <code>TypeVar</code> precedes a non-defaulted one (<code>UP040</code>, <code>UP046</code>, <code>UP047</code>) (<a href="">#27133</a>)</li>
<li>[<code>ruff</code>] Fix false positive with unpacked arguments (<code>RUF065</code>) (<a href="">#26959</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Bump <code>gen-lsp-types</code> to gracefully handle unknown enumeration values in LSP messages (<a href="">#27230</a>)</li>
<li>[<code>flake8-bugbear</code>] Mark <code>range</code> as immutable (<code>B008</code>) (<a href="">#27247</a>)</li>
<li>[<code>flake8-comprehensions</code>] NFKC-normalize keyword names in <code>C408</code> fix (<a href="">#26813</a>)</li>
<li>[<code>flake8-return</code>] Fix false positive when variable is read in <code>finally</code> clause (<code>RET504</code>) (<a href="">#25441</a>)</li>
<li>[<code>pydocstyle</code>] Skip section detection inside RST directive bodies (<code>D214</code>, <code>D405</code>, <code>D413</code>) (<a href="">#23635</a>)</li>
<li>[<code>refurb</code>] Parenthesize <code>yield</code> arguments in the <code>FURB192</code> fix (<a href="">#27192</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-pytest-style</code>] Mark <code>PT022</code> fixes as unsafe (<a href="">#26440</a>)</li>
<li>[<code>refurb</code>] Mark fixes that remove unknown separators as unsafe (<code>FURB105</code>) (<a href="">#27200</a>)</li>
</ul>
<h3>Server</h3>
<ul>
<li>Fix indexing of excluded nested Ruff workspaces (<a href="">#27303</a>)</li>
<li>Lint TOML files in the LSP (<a href="">#26862</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Cover <code>pycon</code> Markdown formatting (<a href="">#27153</a>)</li>
<li>[<code>flake8-bandit</code>] Document <code>TYPE_CHECKING</code> exception (<code>S101</code>) (<a href="">#27004</a>)</li>
<li>[<code>flake8-import-conventions</code>] Document that <code>extend-aliases</code> can override default aliases (<a href="">#27191</a>)</li>
<li>[<code>pylint</code>] Add missing fix safety gotchas for <code>non-augmented-assignment</code> (<code>PLR6104</code>) (<a href="">#27250</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Reduce syntax error noise by swallowing dedents like indents (<a href="">#27170</a>)</li>
<li>Vendor latest annotate-snippets (<a href="">#27033</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/bxff"><code>@​bxff</code></a></li>
<li><a href="https://github.com/anishgirianish"><code>@​anishgirianish</code></a></li>
<li><a href="https://github.com/Avasam"><code>@​Avasam</code></a></li>
<li><a href="https://github.com/epage"><code>@​epage</code></a></li>
<li><a href="https://github.com/LHMQ878"><code>@​LHMQ878</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.1</h2>
<p>Released on 2026-07-30.</p>
<h3>Preview features</h3>
<ul>
<li>Add an option to opt out of human-readable names (<a href="">#27160</a>)</li>
<li>[<code>flake8-pytest-style</code>] Make fixes safe by default and unsafe only when comments are present (<code>PT018</code>) (<a href="">#27201</a>)</li>
<li>[<code>pyupgrade</code>] Skip fix when a defaulted <code>TypeVar</code> precedes a non-defaulted one (<code>UP040</code>, <code>UP046</code>, <code>UP047</code>) (<a href="">#27133</a>)</li>
<li>[<code>ruff</code>] Fix false positive with unpacked arguments (<code>RUF065</code>) (<a href="">#26959</a>)</li>
</ul>
<h3>Bug fixes</h3>
<ul>
<li>Bump <code>gen-lsp-types</code> to gracefully handle unknown enumeration values in LSP messages (<a href="">#27230</a>)</li>
<li>[<code>flake8-bugbear</code>] Mark <code>range</code> as immutable (<code>B008</code>) (<a href="">#27247</a>)</li>
<li>[<code>flake8-comprehensions</code>] NFKC-normalize keyword names in <code>C408</code> fix (<a href="">#26813</a>)</li>
<li>[<code>flake8-return</code>] Fix false positive when variable is read in <code>finally</code> clause (<code>RET504</code>) (<a href="">#25441</a>)</li>
<li>[<code>pydocstyle</code>] Skip section detection inside RST directive bodies (<code>D214</code>, <code>D405</code>, <code>D413</code>) (<a href="">#23635</a>)</li>
<li>[<code>refurb</code>] Parenthesize <code>yield</code> arguments in the <code>FURB192</code> fix (<a href="">#27192</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>[<code>flake8-pytest-style</code>] Mark <code>PT022</code> fixes as unsafe (<a href="">#26440</a>)</li>
<li>[<code>refurb</code>] Mark fixes that remove unknown separators as unsafe (<code>FURB105</code>) (<a href="">#27200</a>)</li>
</ul>
<h3>Server</h3>
<ul>
<li>Fix indexing of excluded nested Ruff workspaces (<a href="">#27303</a>)</li>
<li>Lint TOML files in the LSP (<a href="">#26862</a>)</li>
</ul>
<h3>Documentation</h3>
<ul>
<li>Cover <code>pycon</code> Markdown formatting (<a href="">#27153</a>)</li>
<li>[<code>flake8-bandit</code>] Document <code>TYPE_CHECKING</code> exception (<code>S101</code>) (<a href="">#27004</a>)</li>
<li>[<code>flake8-import-conventions</code>] Document that <code>extend-aliases</code> can override default aliases (<a href="">#27191</a>)</li>
<li>[<code>pylint</code>] Add missing fix safety gotchas for <code>non-augmented-assignment</code> (<code>PLR6104</code>) (<a href="">#27250</a>)</li>
</ul>
<h3>Other changes</h3>
<ul>
<li>Reduce syntax error noise by swallowing dedents like indents (<a href="">#27170</a>)</li>
<li>Vendor latest annotate-snippets (<a href="">#27033</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/bxff"><code>@​bxff</code></a></li>
<li><a href="https://github.com/anishgirianish"><code>@​anishgirianish</code></a></li>
<li><a href="https://github.com/Avasam"><code>@​Avasam</code></a></li>
<li><a href="https://github.com/epage"><code>@​epage</code></a></li>
<li><a href="https://github.com/LHMQ878"><code>@​LHMQ878</code></a></li>
<li><a href="https://github.com/MichaReiser"><code>@​MichaReiser</code></a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>80790b3</code></a> Bump 0.16.1 (<a href="">#27330</a>)</li>
<li><a href=""><code>63830f3</code></a> [ty] Borrow from constraint set storage less often (<a href="">#27328</a>)</li>
<li><a href=""><code>f40dca9</code></a> [ty] Preserve forwarded expanded-variadic diagnostic sources (<a href="">#27266</a>)</li>
<li><a href=""><code>0d80497</code></a> Lint TOML files in the LSP (<a href="">#26862</a>)</li>
<li><a href=""><code>d91586b</code></a> Update prek dependencies (<a href="">#27293</a>)</li>
<li><a href=""><code>7da4b8b</code></a> [ty] Respect bounds and constraints in generic materializations (<a href="">#27228</a>)</li>
<li><a href=""><code>b20daf7</code></a> [ty] refactor: add helper function to send partial results (<a href="">#27249</a>)</li>
<li><a href=""><code>4d4c8fa</code></a> [ty] Emit diagnostic when specializing a non-generic class (<a href="">#26883</a>)</li>
<li><a href=""><code>7c3e2db</code></a> [ty] Fix enum class container assignability (<a href="">#27318</a>)</li>
<li><a href=""><code>d5ef97f</code></a> [<code>flake8-return</code>] Fix false positive when variable is read in <code>finally</code> claus...</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.0...0.16.1">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `f1e24ec0b4b2`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.