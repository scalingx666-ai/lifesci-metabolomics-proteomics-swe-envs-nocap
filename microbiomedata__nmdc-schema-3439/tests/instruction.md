# Issue

**Title:** Bump the python-dependencies group with 3 updates

## Description

Bumps the python-dependencies group with 3 updates: [idna](https://github.com/kjd/idna), [urllib3](https://github.com/urllib3/urllib3) and [ruff](https://github.com/astral-sh/ruff).

Updates `idna` from 3.19 to 3.20
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/kjd/idna/releases">idna's releases</a>.</em></p>
<blockquote>
<h2>v3.20</h2>
<ul>
<li>Update to Unicode 18.0.0.</li>
<li>Better enforcement of the domain length limit in the incremental
codec.</li>
<li>Add support for Python 3.15.</li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/kjd/idna/blob/master/HISTORY.md">idna's changelog</a>.</em></p>
<blockquote>
<h2>3.20 (2026-09-17)</h2>
<ul>
<li>Update to Unicode 18.0.0.</li>
<li>Better enforcement of the domain length limit in the incremental
codec.</li>
<li>Add support for Python 3.15.</li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>d55e65e</code></a> Release 3.20</li>
<li><a href=""><code>0c0824a</code></a> Pre-release 3.20rc0</li>
<li><a href=""><code>bd7c316</code></a> Note Python 3.15 support in the 3.20 changelog</li>
<li><a href=""><code>b6cce85</code></a> Merge pull request <a href="">#276</a> from kjd/unicode-18</li>
<li><a href=""><code>9a4bc59</code></a> Update to Unicode 18.0.0</li>
<li><a href=""><code>dfab5a0</code></a> Merge branch 'python-3.15'</li>
<li><a href=""><code>417c354</code></a> Read the latest Unicode version from the DerivedAge.txt header instead of the...</li>
<li><a href=""><code>cd17392</code></a> Merge pull request <a href="">#274</a> from kjd/fix-decode-length-check</li>
<li><a href=""><code>c5796d7</code></a> Skip the decode round-trip check for domains past encode's length limit</li>
<li><a href=""><code>d6ee690</code></a> Update to Python 3.15 release candidate in CI and add trove classifier</li>
<li>Additional commits viewable in <a href="https://github.com/kjd/idna/compare/v3.19...v3.20">compare view</a></li>
</ul>
</details>
<br />

Updates `urllib3` from 2.7.0 to 2.8.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/urllib3/urllib3/releases">urllib3's releases</a>.</em></p>
<blockquote>
<h2>2.8.0</h2>
<h2>🚀 urllib3 is fundraising for HTTP/2 support</h2>
<p><a href="https://sethmlarson.dev/urllib3-is-fundraising-for-http2-support">urllib3 is raising ~$40,000 USD</a> to release HTTP/2 support and ensure long-term sustainable maintenance of the project. If your company or organization uses Python and would benefit from HTTP/2 support in Requests, pip, cloud SDKs, and thousands of other projects <a href="https://opencollective.com/urllib3">please consider contributing financially</a> to ensure HTTP/2 support is developed sustainably and maintained for the long-haul.</p>
<p>Thank you for your support.</p>
<h2>Security</h2>
<p>Fixed the following security issues:</p>
<ul>
<li>The TLS configuration for HTTPS proxies could be ignored or overridden. (High severity, GHSA-8988-9cw3-xx77)</li>
<li><code>HTTPResponse.stream()</code> and <code>read_chunked()</code> could buffer a chunk-size line of unbounded length in memory. (High severity, GHSA-vxq7-64xx-v4gw)</li>
<li>Chunked Deflate streaming could enter an infinite loop. (Medium severity, GHSA-gh4c-6fx4-qh6g)</li>
</ul>
<blockquote>
<p>[!IMPORTANT]
urllib3 2.8.0 fixes HTTPS proxy TLS configuration being ignored or overridden by destination settings. Configurations relying on that behavior may require changes.</p>
<p>Configure proxy CA certificates and client certificates in <code>proxy_ssl_context</code>, and proxy identity checks with <code>proxy_assert_hostname</code> or <code>proxy_assert_fingerprint</code>. Destination client certificates and identity overrides no longer apply to HTTPS forwarding proxy connections.</p>
</blockquote>
<blockquote>
<p>[!NOTE]
CVE IDs had not yet been assigned to these advisories at the time of release due to a backlog at GitHub's CNA.</p>
</blockquote>
<h2>Deprecations &amp; Removals</h2>
<ul>
<li>Deprecated using an empty collection as the <code>Retry</code> option <code>allowed_methods</code> to retry any verb. (<a href="">#5044</a>)</li>
</ul>
<h2>Features</h2>
<ul>
<li>Added <code>Url.auth_decoded</code> and <code>Url.auth_decoded_joined</code> convenience properties to the result of <code>parse_url()</code>. (<a href="">#4945</a>)</li>
<li>Added <code>basic_auth_encoding</code> and <code>proxy_basic_auth_encoding</code> parameters to <code>urllib3.util.make_headers()</code>. (<a href="">#5092</a>)</li>
</ul>
<h2>Bugfixes</h2>
<ul>
<li>
<p>Fixed response header handling to replace obsolete folded header lines (<code>obs-fold</code>) with spaces in accordance with RFC 9112, preventing raw CRLF sequences from appearing in header values such as <code>Set-Cookie</code>. (<a href="">#1362</a>)</p>
</li>
<li>
<p>Fixed usage of <code>proxy_ssl_context</code> with <code>ProxyManager</code> when <code>use_forwarding_for_https=True</code>. Passing <code>ssl_context</code> instead of <code>proxy_ssl_context</code> for HTTPS proxies in this configuration now emits a <code>FutureWarning</code> and will raise an error in v3.0. (<a href="">#2577</a>)</p>
</li>
<li>
<p>Changed behavior of the default <code>ConnectionPool.pool</code> initialization. <code>LifoQueue</code> is now resolved from the <code>queue</code> module after the <code>ConnectionPool</code> is instantiated instead of using the default cached <code>QueueCls</code> class property. This is done because sometimes the <code>queue.LifoQueue</code> is monkey-patched late in the program, such as by gevent. (<a href="">#3289</a>)</p>
</li>
<li>
<p>Raised <code>UnrewindableBodyError</code> instead of <code>ValueError</code> when retrying a request whose body had <code>tell()</code> but not <code>seek()</code>. (<a href="">#3779</a>)</p>
</li>
<li>
<p>Decoded percent-encoded SOCKS proxy credentials before authenticating with the proxy server. (<a href="">#3785</a>)</p>
</li>
<li>
<p>Fixed <code>HTTPResponse.drain_conn()</code> to discard unread response data in 64 KiB chunks (same as the default <code>amt</code> when doing <code>HTTPResponse.stream(...)</code>). (<a href="">#5019</a>)</p>
</li>
<li>
<p>Fixed <code>is_ipaddress()</code> to detect non-standard IPv4 forms accepted by <code>socket.connect</code>, such as hex (<code>0x7f000001</code>), octal (<code>0177.0.0.1</code>), and decimal integers (<code>2130706433</code>), ensuring SSL certificate verification uses the correct mode for these addresses. (<a href="">#5029</a>)</p>
</li>
<li>
<p>Fixed <code>HTTPConnectionPool.urlopen</code> raising a misleading <code>FullPoolError</code> instead of <code>ValueError</code> when called with an invalid <code>timeout</code> argument on a pool created with <code>block=True</code>. (<a href="">#5059</a>)</p>
</li>
<li>
<p>Fixed port-zero handling to preserve explicit <code>:0</code> values instead of substituting the default ports 80 or 443 in URL parsing, pool selection, proxy configuration, <code>connection_from_url()</code>, and HTTP/2 request authority. (<a href="">#5071</a>, <a href="">#5101</a>)</p>
</li>
<li>
<p>Fixed a bug where <code>PoolManager</code> passed the <code>assert_hostname</code> and <code>assert_fingerprint</code> parameters to HTTP connection pools. (<a href="">#5077</a>)</p>
</li>
<li>
<p>Fixed <code>HTTPConnectionPool.urlopen()</code> and HTTP proxy forwarding to strip URL fragments from absolute request targets before sending requests. (<a href="">#5079</a>)</p>
</li>
<li>
<p>Added safeguards to the proxy tunneling code to prevent potential security issues when handling invalid characters in the proxy host and HTTP headers. This change affects users of Python 3.10, Python 3.11, and Python 3.12 when the standard library does not contain the fix; those on newer Python versions should upgrade to 3.13.14+ or 3.14.5+ to get the same security fixes. (<a href="">#5091</a>)</p>
</li>
<li>
<p>Fixed <code>HTTPSConnection.connect()</code> overriding <code>ProxyConfig.ssl_context</code>'s certificate policy and proxy identity checks with the target connection's TLS settings when forwarding through an HTTPS proxy.</p>
<p><code>HTTPSConnection</code> no longer applies target SNI, assertions, or client credentials to forwarding proxy handshakes and continues to use its <code>ssl_context</code> as a fallback when an HTTPS proxy forwards an HTTP target. (<a href="">#5093</a>)</p>
</li>
<li>
<p>Fixed URL parsing to more strictly enforce RFC 3986 host syntax, rejecting invalid host input such as raw spaces and control characters, malformed percent-encodings, and percent-encoded control characters in HTTP(S) hosts and IPv6 zone identifiers, including proxy CONNECT tunnel targets. Host normalization now also follows RFC 3986 normalization rules for percent-encoded octets by decoding percent-encoded unreserved characters and uppercasing the hexadecimal digits of retained percent-encoded octets. (<a href="">#5095</a>)</p>
</li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/urllib3/urllib3/blob/main/CHANGES.rst">urllib3's changelog</a>.</em></p>
<blockquote>
<h1>2.8.0 (2026-09-15)</h1>
<h2>Security</h2>
<p>Fixed the following security issues:</p>
<ul>
<li>The TLS configuration for HTTPS proxies could be ignored or overridden.
(High severity, <code>GHSA-8988-9cw3-xx77 &lt;https://github.com/urllib3/urllib3/security/advisories/GHSA-8988-9cw3-xx77&gt;</code>__)</li>
<li><code>HTTPResponse.stream()</code> and <code>read_chunked()</code> could buffer a chunk-size
line of unbounded length in memory. (High severity,
<code>GHSA-vxq7-64xx-v4gw &lt;https://github.com/urllib3/urllib3/security/advisories/GHSA-vxq7-64xx-v4gw&gt;</code>__)</li>
<li>Chunked Deflate streaming could enter an infinite loop. (Medium severity,
<code>GHSA-gh4c-6fx4-qh6g &lt;https://github.com/urllib3/urllib3/security/advisories/GHSA-gh4c-6fx4-qh6g&gt;</code>__)</li>
</ul>
<p>.. caution::</p>
<pre><code>urllib3 2.8.0 fixes HTTPS proxy TLS configuration being ignored or
overridden by destination settings. Configurations relying on that
behavior may require changes.
<p>Configure proxy CA certificates and client certificates in
<code>proxy_ssl_context</code>, and proxy identity checks with
<code>proxy_assert_hostname</code> or <code>proxy_assert_fingerprint</code>.
Destination client certificates and identity overrides no longer
apply to HTTPS forwarding proxy connections.
</code></pre></p>
<h2>Deprecations &amp; Removals</h2>
<ul>
<li>Deprecated using an empty collection as the <code>Retry</code> option
<code>allowed_methods</code> to retry any verb.
(<code> &lt;</code>__)</li>
</ul>
<h2>Features</h2>
<ul>
<li>Added <code>Url.auth_decoded</code> and <code>Url.auth_decoded_joined</code> convenience
properties to the result of <code>parse_url()</code>.
(<code> &lt;</code>__)</li>
<li>Added <code>basic_auth_encoding</code> and <code>proxy_basic_auth_encoding</code> parameters to
<code>urllib3.util.make_headers()</code>.
(<code> &lt;</code>__)</li>
</ul>
<h2>Bugfixes</h2>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>b1d30ab</code></a> Release 2.8.0</li>
<li><a href=""><code>9016d7e</code></a> Skip <code>test_read_chunked_with_trailing_data_does_not_hang</code> for brotlicffi (<a href="">#5258</a>)</li>
<li><a href=""><code>9101f58</code></a> Fix <code>nox -s docs</code> warning (<a href="">#5256</a>)</li>
<li><a href=""><code>cd770b0</code></a> Merge commit from fork</li>
<li><a href=""><code>ea2ad7b</code></a> Merge commit from fork</li>
<li><a href=""><code>0716e31</code></a> Fix loading unencrypted client keys with a password in pyOpenSSL (<a href="">#5255</a>)</li>
<li><a href=""><code>43c68c8</code></a> Test pickling of <code>InvalidChunkLength</code> (<a href="">#5247</a>)</li>
<li><a href=""><code>308b279</code></a> Share security policy between GitHub and Read the Docs (<a href="">#5253</a>)</li>
<li><a href=""><code>53fa073</code></a> Add policy on duplicate pull requests (<a href="">#5252</a>)</li>
<li><a href=""><code>5f2a6a8</code></a> Assert on the ALPN extension in test_tunnel_sets_http_11_alpn (<a href="">#5232</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/urllib3/urllib3/compare/2.7.0...2.8.0">compare view</a></li>
</ul>
</details>
<br />

Updates `ruff` from 0.16.7 to 0.16.8
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/releases">ruff's releases</a>.</em></p>
<blockquote>
<h2>0.16.8</h2>
<h2>Release Notes</h2>
<p>Released on 2026-09-16.</p>
<h3>Bug fixes</h3>
<ul>
<li>Visit functional <code>TypedDict</code> keyword arguments correctly (<a href="">#28584</a>)</li>
<li>[<code>flake8-simplify</code>] Detect nested <code>async with</code> under sync parent (<code>SIM117</code>) (<a href="">#27821</a>)</li>
<li>[<code>flake8-simplify</code>] Preserve operand order in <code>SIM109</code> fix (<a href="">#27824</a>)</li>
<li>[<code>pyupgrade</code>] Preserve required parentheses in multiline <code>UP040</code> fixes (<a href="">#28164</a>)</li>
<li>[<code>pyupgrade</code>] Skip <code>TypeVarTuple</code> and <code>ParamSpec</code> conversions with bounds or constraints (<code>UP040</code>, <code>UP046</code>, <code>UP047</code>) (<a href="">#28505</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Add support for <code>__lazy_modules__</code> (<a href="">#28459</a>)</li>
<li>Recognize PEP-728 <code>TypedDict</code> class keywords (<a href="">#28533</a>)</li>
<li>Recognize quoted types in <code>typing.TypeForm</code> (<a href="">#28507</a>)</li>
<li>Support conditional assignment to <code>__lazy_modules__</code> (<a href="">#28491</a>)</li>
<li>[<code>flake8-type-checking</code>] Prefer lazy imports over <code>TYPE_CHECKING</code> on Python 3.15 and later (<code>TC001</code>, <code>TC002</code>, <code>TC003</code>) (<a href="">#28541</a>)</li>
<li>[<code>pyupgrade</code>] Make the fix for <code>UP040</code> always unsafe (<a href="">#28526</a>)</li>
<li>[<code>pyupgrade</code>] Stop recommending deprecated <code>ByteString</code> aliases (<code>UP035</code>) (<a href="">#28498</a>)</li>
<li>[<code>ruff</code>, <code>flake8-use-pathlib</code>] Recognize the <code>parent_mode</code> argument (<code>RUF064</code>, <code>PTH103</code>) (<a href="">#28528</a>)</li>
<li>[<code>ruff</code>] Detect <code>\Z</code> in <code>pytest.raises()</code> match patterns (<code>RUF043</code>) (<a href="">#28598</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Use rule name and code in formatter incompatibility warnings (<a href="">#28571</a>)</li>
</ul>
<h3>Configuration</h3>
<ul>
<li>[<code>flake8-tidy-imports</code>] Add <code>extend-banned-api</code> (<a href="">#28644</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/VedantMadane"><code>@​VedantMadane</code></a></li>
<li><a href="https://github.com/alzeph"><code>@​alzeph</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/fredrikblau"><code>@​fredrikblau</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/zsol"><code>@​zsol</code></a></li>
<li><a href="https://github.com/Aniket-a14"><code>@​Aniket-a14</code></a></li>
<li><a href="https://github.com/r-b-1"><code>@​r-b-1</code></a></li>
</ul>
<h2>Install ruff 0.16.8</h2>
<h3>Install prebuilt binaries via shell script</h3>
<pre lang="sh"><code>curl --proto '=https' --tlsv1.2 -LsSf https://releases.astral.sh/github/ruff/releases/download/0.16.8/ruff-installer.sh | sh
&lt;/tr&gt;&lt;/table&gt;
</code></pre>
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/astral-sh/ruff/blob/main/CHANGELOG.md">ruff's changelog</a>.</em></p>
<blockquote>
<h2>0.16.8</h2>
<p>Released on 2026-09-16.</p>
<h3>Bug fixes</h3>
<ul>
<li>Visit functional <code>TypedDict</code> keyword arguments correctly (<a href="">#28584</a>)</li>
<li>[<code>flake8-simplify</code>] Detect nested <code>async with</code> under sync parent (<code>SIM117</code>) (<a href="">#27821</a>)</li>
<li>[<code>flake8-simplify</code>] Preserve operand order in <code>SIM109</code> fix (<a href="">#27824</a>)</li>
<li>[<code>pyupgrade</code>] Preserve required parentheses in multiline <code>UP040</code> fixes (<a href="">#28164</a>)</li>
<li>[<code>pyupgrade</code>] Skip <code>TypeVarTuple</code> and <code>ParamSpec</code> conversions with bounds or constraints (<code>UP040</code>, <code>UP046</code>, <code>UP047</code>) (<a href="">#28505</a>)</li>
</ul>
<h3>Rule changes</h3>
<ul>
<li>Add support for <code>__lazy_modules__</code> (<a href="">#28459</a>)</li>
<li>Recognize PEP-728 <code>TypedDict</code> class keywords (<a href="">#28533</a>)</li>
<li>Recognize quoted types in <code>typing.TypeForm</code> (<a href="">#28507</a>)</li>
<li>Support conditional assignment to <code>__lazy_modules__</code> (<a href="">#28491</a>)</li>
<li>[<code>flake8-type-checking</code>] Prefer lazy imports over <code>TYPE_CHECKING</code> on Python 3.15 and later (<code>TC001</code>, <code>TC002</code>, <code>TC003</code>) (<a href="">#28541</a>)</li>
<li>[<code>pyupgrade</code>] Make the fix for <code>UP040</code> always unsafe (<a href="">#28526</a>)</li>
<li>[<code>pyupgrade</code>] Stop recommending deprecated <code>ByteString</code> aliases (<code>UP035</code>) (<a href="">#28498</a>)</li>
<li>[<code>ruff</code>, <code>flake8-use-pathlib</code>] Recognize the <code>parent_mode</code> argument (<code>RUF064</code>, <code>PTH103</code>) (<a href="">#28528</a>)</li>
<li>[<code>ruff</code>] Detect <code>\Z</code> in <code>pytest.raises()</code> match patterns (<code>RUF043</code>) (<a href="">#28598</a>)</li>
</ul>
<h3>CLI</h3>
<ul>
<li>Use rule name and code in formatter incompatibility warnings (<a href="">#28571</a>)</li>
</ul>
<h3>Configuration</h3>
<ul>
<li>[<code>flake8-tidy-imports</code>] Add <code>extend-banned-api</code> (<a href="">#28644</a>)</li>
</ul>
<h3>Contributors</h3>
<ul>
<li><a href="https://github.com/VedantMadane"><code>@​VedantMadane</code></a></li>
<li><a href="https://github.com/alzeph"><code>@​alzeph</code></a></li>
<li><a href="https://github.com/charliermarsh"><code>@​charliermarsh</code></a></li>
<li><a href="https://github.com/fredrikblau"><code>@​fredrikblau</code></a></li>
<li><a href="https://github.com/ntBre"><code>@​ntBre</code></a></li>
<li><a href="https://github.com/zsol"><code>@​zsol</code></a></li>
<li><a href="https://github.com/Aniket-a14"><code>@​Aniket-a14</code></a></li>
<li><a href="https://github.com/r-b-1"><code>@​r-b-1</code></a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>62914c4</code></a> Bump version to 0.16.8 (<a href="">#28648</a>)</li>
<li><a href=""><code>c47e0cd</code></a> [ty] Bound aliased intersection expansion during inference (<a href="">#28546</a>)</li>
<li><a href=""><code>ff4747b</code></a> renovate: update uv hashes correctly with setup-uv (<a href="">#28621</a>)</li>
<li><a href=""><code>94efeaa</code></a> [ty] Compact reachable binding and declaration histories (<a href="">#28349</a>)</li>
<li><a href=""><code>50020fb</code></a> [ty] Avoid storing constraint nodes twice (<a href="">#28375</a>)</li>
<li><a href=""><code>446bb68</code></a> [ty] Compare bound-method receivers before signatures (<a href="">#28384</a>)</li>
<li><a href=""><code>304ab86</code></a> [<code>flake8-type-checking</code>] Prefer lazy imports over <code>TYPE_CHECKING</code> on 3.15+ (`...</li>
<li><a href=""><code>d940b24</code></a> [ty] Watch script dependencies in CLI watch mode (<a href="">#28125</a>)</li>
<li><a href=""><code>fe9f065</code></a> [flake8-tidy-imports] Add <code>extend-banned-api</code> (<a href="">#28644</a>)</li>
<li><a href=""><code>31131db</code></a> [ty] Support <code>type[A &amp; B]</code> (<a href="">#27124</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/astral-sh/ruff/compare/0.16.7...0.16.8">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `e284a4634748`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.