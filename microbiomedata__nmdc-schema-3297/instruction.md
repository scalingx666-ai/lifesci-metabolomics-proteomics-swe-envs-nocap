# Issue

**Title:** Bump the github-actions group with 6 updates

## Description

Bumps the github-actions group with 6 updates:

| Package | From | To |
| --- | --- | --- |
| [actions/checkout](https://github.com/actions/checkout) | `7.0.0` | `7.0.1` |
| [actions/setup-python](https://github.com/actions/setup-python) | `6.3.0` | `7.0.0` |
| [github/codeql-action/init](https://github.com/github/codeql-action) | `4.37.0` | `4.37.3` |
| [github/codeql-action/analyze](https://github.com/github/codeql-action) | `4.37.0` | `4.37.3` |
| [pypa/gh-action-pypi-publish](https://github.com/pypa/gh-action-pypi-publish) | `1.14.0` | `1.14.1` |
| [github/codeql-action/upload-sarif](https://github.com/github/codeql-action) | `4.37.0` | `4.37.3` |

Updates `actions/checkout` from 7.0.0 to 7.0.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/actions/checkout/releases">actions/checkout's releases</a>.</em></p>
<blockquote>
<h2>v7.0.1</h2>
<h2>What's Changed</h2>
<ul>
<li>skip running unsafe pr check if input is default by <a href="https://github.com/aiqiaoy"><code>@​aiqiaoy</code></a> in <a href="">actions/checkout#2518</a></li>
<li>trim only ascii whitespace for branch by <a href="https://github.com/aiqiaoy"><code>@​aiqiaoy</code></a> in <a href="">actions/checkout#2521</a></li>
<li>escape values passed to --unset by <a href="https://github.com/aiqiaoy"><code>@​aiqiaoy</code></a> in <a href="">actions/checkout#2530</a></li>
<li>Various dependency updates</li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/actions/checkout/compare/v7...v7.0.1">https://github.com/actions/checkout/compare/v7...v7.0.1</a></p>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/actions/checkout/blob/main/CHANGELOG.md">actions/checkout's changelog</a>.</em></p>
<blockquote>
<h1>Changelog</h1>
<h2>v7.0.1</h2>
<ul>
<li>Skip running unsafe pr check if input is default by <a href="https://github.com/aiqiaoy"><code>@​aiqiaoy</code></a> in <a href="">actions/checkout#2518</a></li>
<li>Trim only ascii whitespace for branch by <a href="https://github.com/aiqiaoy"><code>@​aiqiaoy</code></a> in <a href="">actions/checkout#2521</a></li>
<li>Escape values passed to --unset by <a href="https://github.com/aiqiaoy"><code>@​aiqiaoy</code></a> in <a href="">actions/checkout#2530</a></li>
<li>Various dependency updates</li>
</ul>
<h2>v7.0.0</h2>
<ul>
<li>Block checking out fork PR for pull_request_target and workflow_run by <a href="https://github.com/aiqiaoy"><code>@​aiqiaoy</code></a> in <a href="">actions/checkout#2454</a></li>
<li>Various dependency updates</li>
</ul>
<h2>v6.0.3</h2>
<ul>
<li>Fix checkout init for SHA-256 repositories by <a href="https://github.com/yaananth"><code>@​yaananth</code></a> in <a href="">actions/checkout#2439</a></li>
<li>fix: expand merge commit SHA regex and add SHA-256 test cases by <a href="https://github.com/yaananth"><code>@​yaananth</code></a> in <a href="">actions/checkout#2414</a></li>
</ul>
<h2>v6.0.2</h2>
<ul>
<li>Fix tag handling: preserve annotations and explicit fetch-tags by <a href="https://github.com/ericsciple"><code>@​ericsciple</code></a> in <a href="">actions/checkout#2356</a></li>
</ul>
<h2>v6.0.1</h2>
<ul>
<li>Add worktree support for persist-credentials includeIf by <a href="https://github.com/ericsciple"><code>@​ericsciple</code></a> in <a href="">actions/checkout#2327</a></li>
</ul>
<h2>v6.0.0</h2>
<ul>
<li>Persist creds to a separate file by <a href="https://github.com/ericsciple"><code>@​ericsciple</code></a> in <a href="">actions/checkout#2286</a></li>
<li>Update README to include Node.js 24 support details and requirements by <a href="https://github.com/salmanmkc"><code>@​salmanmkc</code></a> in <a href="">actions/checkout#2248</a></li>
</ul>
<h2>v5.0.1</h2>
<ul>
<li>Port v6 cleanup to v5 by <a href="https://github.com/ericsciple"><code>@​ericsciple</code></a> in <a href="">actions/checkout#2301</a></li>
</ul>
<h2>v5.0.0</h2>
<ul>
<li>Update actions checkout to use node 24 by <a href="https://github.com/salmanmkc"><code>@​salmanmkc</code></a> in <a href="">actions/checkout#2226</a></li>
</ul>
<h2>v4.3.1</h2>
<ul>
<li>Port v6 cleanup to v4 by <a href="https://github.com/ericsciple"><code>@​ericsciple</code></a> in <a href="">actions/checkout#2305</a></li>
</ul>
<h2>v4.3.0</h2>
<ul>
<li>docs: update README.md by <a href="https://github.com/motss"><code>@​motss</code></a> in <a href="">actions/checkout#1971</a></li>
<li>Add internal repos for checking out multiple repositories by <a href="https://github.com/mouismail"><code>@​mouismail</code></a> in <a href="">actions/checkout#1977</a></li>
<li>Documentation update - add recommended permissions to Readme by <a href="https://github.com/benwells"><code>@​benwells</code></a> in <a href="">actions/checkout#2043</a></li>
<li>Adjust positioning of user email note and permissions heading by <a href="https://github.com/joshmgross"><code>@​joshmgross</code></a> in <a href="">actions/checkout#2044</a></li>
<li>Update README.md by <a href="https://github.com/nebuk89"><code>@​nebuk89</code></a> in <a href="">actions/checkout#2194</a></li>
<li>Update CODEOWNERS for actions by <a href="https://github.com/TingluoHuang"><code>@​TingluoHuang</code></a> in <a href="">actions/checkout#2224</a></li>
<li>Update package dependencies by <a href="https://github.com/salmanmkc"><code>@​salmanmkc</code></a> in <a href="">actions/checkout#2236</a></li>
</ul>
<h2>v4.2.2</h2>
<ul>
<li><code>url-helper.ts</code> now leverages well-known environment variables by <a href="https://github.com/jww3"><code>@​jww3</code></a> in <a href="">actions/checkout#1941</a></li>
<li>Expand unit test coverage for <code>isGhes</code> by <a href="https://github.com/jww3"><code>@​jww3</code></a> in <a href="">actions/checkout#1946</a></li>
</ul>
<h2>v4.2.1</h2>
<ul>
<li>Check out other refs/* by commit if provided, fall back to ref by <a href="https://github.com/orhantoy"><code>@​orhantoy</code></a> in <a href="">actions/checkout#1924</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>3d3c42e</code></a> prep v7.0.1 release (<a href="">#2531</a>)</li>
<li><a href=""><code>2880268</code></a> escape values passed to --unset (<a href="">#2530</a>)</li>
<li><a href=""><code>12cd223</code></a> trim only ascii whitespace for branch (<a href="">#2521</a>)</li>
<li><a href=""><code>62661c4</code></a> skip running unsafe pr check if input is default (<a href="">#2518</a>)</li>
<li><a href=""><code>e8d4307</code></a> Bump the minor-actions-dependencies group with 2 updates (<a href="">#2499</a>)</li>
<li><a href=""><code>631c942</code></a> eslint 9 (<a href="">#2474</a>)</li>
<li><a href=""><code>4f1f4ae</code></a> Bump actions/upload-artifact from 4 to 7 (<a href="">#2476</a>)</li>
<li><a href=""><code>ba09753</code></a> Bump actions/checkout from 6 to 7 (<a href="">#2488</a>)</li>
<li><a href=""><code>b9e0990</code></a> Bump docker/login-action from 3.3.0 to 4.2.0 (<a href="">#2479</a>)</li>
<li><a href=""><code>e8cb398</code></a> Bump docker/build-push-action from 6.5.0 to 7.2.0 (<a href="">#2478</a>)</li>
<li>Additional commits viewable in <a href="https://github.com/actions/checkout/compare/9c091bb21b7c1c1d1991bb908d89e4e9dddfe3e0...3d3c42e5aac5ba805825da76410c181273ba90b1">compare view</a></li>
</ul>
</details>
<br />

Updates `actions/setup-python` from 6.3.0 to 7.0.0
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/actions/setup-python/releases">actions/setup-python's releases</a>.</em></p>
<blockquote>
<h2>v7.0.0</h2>
<h2>What's Changed</h2>
<h3>Enhancements</h3>
<ul>
<li>Migrate to ESM and upgrade dependencies by <a href="https://github.com/priyagupta108"><code>@​priyagupta108</code></a> in <a href="">actions/setup-python#1330</a></li>
<li>Pin SHA commits and update docs with latest versions by <a href="https://github.com/HarithaVattikuti"><code>@​HarithaVattikuti</code></a> in <a href="">actions/setup-python#1338</a></li>
<li>Remove the pip-install input by <a href="https://github.com/gowridurgad"><code>@​gowridurgad</code></a> in <a href="">actions/setup-python#1336</a></li>
</ul>
<h3>Bug Fix</h3>
<ul>
<li>Fix to Classify stderr warning messages as warnings instead of errors in annotations by <a href="https://github.com/lmvysakh"><code>@​lmvysakh</code></a> in <a href="">actions/setup-python#1335</a></li>
<li>Validate and retry manifest fetch to prevent silent failures by <a href="https://github.com/priyagupta108"><code>@​priyagupta108</code></a> in <a href="">actions/setup-python#1332</a></li>
</ul>
<h3>Dependency Upgrade</h3>
<ul>
<li>Bump certifi from 2020.6.20 to 2024.7.4 in /<strong>tests</strong>/data by <a href="https://github.com/dependabot"><code>@​dependabot</code></a> in <a href="">actions/setup-python#1328</a></li>
<li>Remove EOL Python versions and Bumps numpy text fixture by <a href="https://github.com/priya-kinthali"><code>@​priya-kinthali</code></a> in <a href="">actions/setup-python#1333</a></li>
<li>Upgrade <code>@​actions/cache</code> to 6.2.0 by <a href="https://github.com/philip-gai"><code>@​philip-gai</code></a> in <a href="">actions/setup-python#1337</a></li>
</ul>
<h2>New Contributors</h2>
<ul>
<li><a href="https://github.com/lmvysakh"><code>@​lmvysakh</code></a> made their first contribution in <a href="">actions/setup-python#1335</a></li>
<li><a href="https://github.com/philip-gai"><code>@​philip-gai</code></a> made their first contribution in <a href="">actions/setup-python#1337</a></li>
</ul>
<p><strong>Full Changelog</strong>: <a href="https://github.com/actions/setup-python/compare/v6...v7.0.0">https://github.com/actions/setup-python/compare/v6...v7.0.0</a></p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>5fda3b9</code></a> Pin SHA commits and update docs with latest versions (<a href="">#1338</a>)</li>
<li><a href=""><code>4ab7e95</code></a> Merge pull request <a href="">#1337</a> from actions/philip-gai/bump-actions-cache-6-2-0</li>
<li><a href=""><code>0f3a009</code></a> Remove the pip-install input (<a href="">#1336</a>)</li>
<li><a href=""><code>f8cf429</code></a> Migrate to ESM and upgrade dependencies (<a href="">#1330</a>)</li>
<li><a href=""><code>54baeea</code></a> Validate and retry manifest fetch to prevent silent failures (<a href="">#1332</a>)</li>
<li><a href=""><code>c709277</code></a> Annotation code fix (<a href="">#1335</a>)</li>
<li><a href=""><code>6849080</code></a> remove EOL Python versions and Bumps numpy text fixture (<a href="">#1333</a>)</li>
<li><a href=""><code>0903b46</code></a> Bump certifi from 2020.6.20 to 2024.7.4 in /<strong>tests</strong>/data (<a href="">#1328</a>)</li>
<li>See full diff in <a href="https://github.com/actions/setup-python/compare/ece7cb06caefa5fff74198d8649806c4678c61a1...5fda3b95a4ea91299a34e894583c3862153e4b97">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/init` from 4.37.0 to 4.37.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/init's releases</a>.</em></p>
<blockquote>
<h2>v4.37.3</h2>
<p>No user facing changes.</p>
<h2>v4.37.2</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
<li>The CodeQL Action can now make use of <a href="https://docs.github.com/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries">configured private registries</a> in Default Setup to retrieve CodeQL configuration files from remote repositories that require authentication. This will allow customers to store their CodeQL configuration in a single repository that can then be referenced by Default Setup workflows in other repositories. We expect to roll this and other, related changes out to everyone in July. <a href="">#4007</a></li>
</ul>
<h2>v4.37.1</h2>
<ul>
<li><em>Upcoming breaking change</em>: Add a deprecation warning for customers using CodeQL version 2.20.6 and earlier. These versions of CodeQL were discontinued on 1 July 2026 alongside GitHub Enterprise Server 3.16, and will be unsupported by the next minor release of the CodeQL Action. <a href="">#3956</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.1">2.26.1</a>. <a href="">#4019</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/blob/main/CHANGELOG.md">github/codeql-action/init's changelog</a>.</em></p>
<blockquote>
<h1>CodeQL Action Changelog</h1>
<p>See the <a href="https://github.com/github/codeql-action/releases">releases page</a> for the relevant changes to the CodeQL CLI and language packs.</p>
<h2>[UNRELEASED]</h2>
<p>No user facing changes.</p>
<h2>4.37.3 - 22 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.2 - 21 Jul 2026</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
<li>The CodeQL Action can now make use of <a href="https://docs.github.com/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries">configured private registries</a> in Default Setup to retrieve CodeQL configuration files from remote repositories that require authentication. This will allow customers to store their CodeQL configuration in a single repository that can then be referenced by Default Setup workflows in other repositories. We expect to roll this and other, related changes out to everyone in July. <a href="">#4007</a></li>
</ul>
<h2>4.37.1 - 16 Jul 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: Add a deprecation warning for customers using CodeQL version 2.20.6 and earlier. These versions of CodeQL were discontinued on 1 July 2026 alongside GitHub Enterprise Server 3.16, and will be unsupported by the next minor release of the CodeQL Action. <a href="">#3956</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.1">2.26.1</a>. <a href="">#4019</a></li>
</ul>
<h2>4.37.0 - 08 Jul 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.0">2.26.0</a>. <a href="">#3995</a></li>
<li>In addition to the existing input format, the <code>config-file</code> input for the <code>codeql-action/init</code> step will soon support a new <code>[owner/]repo[@ref][:path]</code> format. All components except the repository name are optional. If omitted, <code>owner</code> defaults to the same owner as the repository the analysis is running for, <code>ref</code> to <code>main</code>, and <code>path</code> to <code>.github/codeql-action.yaml</code>. Support for this format ships in this version of the CodeQL Action, but will only be enabled over the coming weeks. <a href="">#3973</a></li>
</ul>
<h2>4.36.3 - 01 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.36.2 - 04 Jun 2026</h2>
<ul>
<li>Cache CodeQL CLI version information across Actions steps. <a href="">#3943</a></li>
<li>Reduce requests while waiting for analysis processing by using exponential backoff when polling SARIF processing status. <a href="">#3937</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.25.6">2.25.6</a>. <a href="">#3948</a></li>
</ul>
<h2>4.36.1 - 02 Jun 2026</h2>
<p>No user facing changes.</p>
<h2>4.36.0 - 22 May 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.19.4. <a href="">#3894</a></li>
<li>Add support for SHA-256 Git object IDs. <a href="">#3893</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.25.5">2.25.5</a>. <a href="">#3926</a></li>
</ul>
<h2>4.35.5 - 15 May 2026</h2>
<ul>
<li>We have improved how the JavaScript bundles for the CodeQL Action are generated to avoid duplication across bundles and reduce the size of the repository by around 70%. This should have no effect on the runtime behaviour of the CodeQL Action. <a href="">#3899</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>e4fba86</code></a> Merge pull request <a href="">#4031</a> from github/update-v4.37.3-72f6a9da0</li>
<li><a href=""><code>fb50ab5</code></a> Update changelog for v4.37.3</li>
<li><a href=""><code>72f6a9d</code></a> Merge pull request <a href="">#4030</a> from github/mbg/fix/no-proxy</li>
<li><a href=""><code>3b5ee58</code></a> Use default <code>request</code> options instead of <code>undefined</code></li>
<li><a href=""><code>bfb6be4</code></a> Merge pull request <a href="">#4028</a> from github/mergeback/v4.37.2-to-main-e0647621</li>
<li><a href=""><code>526ab84</code></a> Rebuild</li>
<li><a href=""><code>d6217b9</code></a> Update changelog and version after v4.37.2</li>
<li><a href=""><code>e064762</code></a> Merge pull request <a href="">#4027</a> from github/update-v4.37.2-385bcdc5a</li>
<li><a href=""><code>e0faed8</code></a> Add a couple of change notes</li>
<li><a href=""><code>73aad0e</code></a> Update changelog for v4.37.2</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/99df26d4f13ea111d4ec1a7dddef6063f76b97e9...e4fba868fa4b1b91e1fdab776edc8cfbe6e9fb81">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/analyze` from 4.37.0 to 4.37.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/analyze's releases</a>.</em></p>
<blockquote>
<h2>v4.37.3</h2>
<p>No user facing changes.</p>
<h2>v4.37.2</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
<li>The CodeQL Action can now make use of <a href="https://docs.github.com/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries">configured private registries</a> in Default Setup to retrieve CodeQL configuration files from remote repositories that require authentication. This will allow customers to store their CodeQL configuration in a single repository that can then be referenced by Default Setup workflows in other repositories. We expect to roll this and other, related changes out to everyone in July. <a href="">#4007</a></li>
</ul>
<h2>v4.37.1</h2>
<ul>
<li><em>Upcoming breaking change</em>: Add a deprecation warning for customers using CodeQL version 2.20.6 and earlier. These versions of CodeQL were discontinued on 1 July 2026 alongside GitHub Enterprise Server 3.16, and will be unsupported by the next minor release of the CodeQL Action. <a href="">#3956</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.1">2.26.1</a>. <a href="">#4019</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/blob/main/CHANGELOG.md">github/codeql-action/analyze's changelog</a>.</em></p>
<blockquote>
<h1>CodeQL Action Changelog</h1>
<p>See the <a href="https://github.com/github/codeql-action/releases">releases page</a> for the relevant changes to the CodeQL CLI and language packs.</p>
<h2>[UNRELEASED]</h2>
<p>No user facing changes.</p>
<h2>4.37.3 - 22 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.2 - 21 Jul 2026</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
<li>The CodeQL Action can now make use of <a href="https://docs.github.com/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries">configured private registries</a> in Default Setup to retrieve CodeQL configuration files from remote repositories that require authentication. This will allow customers to store their CodeQL configuration in a single repository that can then be referenced by Default Setup workflows in other repositories. We expect to roll this and other, related changes out to everyone in July. <a href="">#4007</a></li>
</ul>
<h2>4.37.1 - 16 Jul 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: Add a deprecation warning for customers using CodeQL version 2.20.6 and earlier. These versions of CodeQL were discontinued on 1 July 2026 alongside GitHub Enterprise Server 3.16, and will be unsupported by the next minor release of the CodeQL Action. <a href="">#3956</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.1">2.26.1</a>. <a href="">#4019</a></li>
</ul>
<h2>4.37.0 - 08 Jul 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.0">2.26.0</a>. <a href="">#3995</a></li>
<li>In addition to the existing input format, the <code>config-file</code> input for the <code>codeql-action/init</code> step will soon support a new <code>[owner/]repo[@ref][:path]</code> format. All components except the repository name are optional. If omitted, <code>owner</code> defaults to the same owner as the repository the analysis is running for, <code>ref</code> to <code>main</code>, and <code>path</code> to <code>.github/codeql-action.yaml</code>. Support for this format ships in this version of the CodeQL Action, but will only be enabled over the coming weeks. <a href="">#3973</a></li>
</ul>
<h2>4.36.3 - 01 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.36.2 - 04 Jun 2026</h2>
<ul>
<li>Cache CodeQL CLI version information across Actions steps. <a href="">#3943</a></li>
<li>Reduce requests while waiting for analysis processing by using exponential backoff when polling SARIF processing status. <a href="">#3937</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.25.6">2.25.6</a>. <a href="">#3948</a></li>
</ul>
<h2>4.36.1 - 02 Jun 2026</h2>
<p>No user facing changes.</p>
<h2>4.36.0 - 22 May 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.19.4. <a href="">#3894</a></li>
<li>Add support for SHA-256 Git object IDs. <a href="">#3893</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.25.5">2.25.5</a>. <a href="">#3926</a></li>
</ul>
<h2>4.35.5 - 15 May 2026</h2>
<ul>
<li>We have improved how the JavaScript bundles for the CodeQL Action are generated to avoid duplication across bundles and reduce the size of the repository by around 70%. This should have no effect on the runtime behaviour of the CodeQL Action. <a href="">#3899</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>e4fba86</code></a> Merge pull request <a href="">#4031</a> from github/update-v4.37.3-72f6a9da0</li>
<li><a href=""><code>fb50ab5</code></a> Update changelog for v4.37.3</li>
<li><a href=""><code>72f6a9d</code></a> Merge pull request <a href="">#4030</a> from github/mbg/fix/no-proxy</li>
<li><a href=""><code>3b5ee58</code></a> Use default <code>request</code> options instead of <code>undefined</code></li>
<li><a href=""><code>bfb6be4</code></a> Merge pull request <a href="">#4028</a> from github/mergeback/v4.37.2-to-main-e0647621</li>
<li><a href=""><code>526ab84</code></a> Rebuild</li>
<li><a href=""><code>d6217b9</code></a> Update changelog and version after v4.37.2</li>
<li><a href=""><code>e064762</code></a> Merge pull request <a href="">#4027</a> from github/update-v4.37.2-385bcdc5a</li>
<li><a href=""><code>e0faed8</code></a> Add a couple of change notes</li>
<li><a href=""><code>73aad0e</code></a> Update changelog for v4.37.2</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/99df26d4f13ea111d4ec1a7dddef6063f76b97e9...e4fba868fa4b1b91e1fdab776edc8cfbe6e9fb81">compare view</a></li>
</ul>
</details>
<br />

Updates `pypa/gh-action-pypi-publish` from 1.14.0 to 1.14.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/pypa/gh-action-pypi-publish/releases">pypa/gh-action-pypi-publish's releases</a>.</em></p>
<blockquote>
<h2>v1.14.1</h2>
<!-- raw HTML omitted -->
<h2>🛠️ Internal Dependencies</h2>
<p><a href="https://github.com/adisivaprasad"><code>@​adisivaprasad</code></a><a href="https://github.com/sponsors/adisivaprasad">💰</a> helped get rid of the GitHub Actions runner warning about the old Node 20 runtime being used by updating <code>actions/setup-python</code> from v5.6.0 to v6.2.0 in <a href="">#408</a>.</p>
<h2>💪 New Contributors</h2>
<ul>
<li><a href="https://github.com/adisivaprasad"><code>@​adisivaprasad</code></a> made their first contribution in <a href="">#408</a></li>
<li><a href="https://github.com/jylenhof"><code>@​jylenhof</code></a><a href="https://github.com/sponsors/jylenhof">💰</a> followed up and reminded us to actually cut this release in <a href="">#413</a></li>
</ul>
<p><strong>🪞 Full Diff</strong>: <a href="https://github.com/pypa/gh-action-pypi-publish/compare/v1.14.0...v1.14.1">https://github.com/pypa/gh-action-pypi-publish/compare/v1.14.0...v1.14.1</a></p>
<p><strong>🧔‍♂️ Release Manager:</strong> <a href="https://github.com/sponsors/webknjaz"><code>@​webknjaz</code></a> <a href="https://stand-with-ukraine.pp.ua">🇺🇦</a></p>
<p><strong>🙏 Special Thanks</strong> to <a href="https://github.com/jylenhof"><code>@​jylenhof</code></a><a href="https://github.com/sponsors/jylenhof">💰</a> for reminding me to work on this release!</p>
<p><a href="https://github.com/sponsors/webknjaz"><img src="https://img.shields.io/badge/%40webknjaz-transparent?logo=githubsponsors&amp;logoColor=%23EA4AAA&amp;label=Sponsor&amp;color=2a313c" alt="GH Sponsors badge" /></a></p>
</blockquote>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>ba38be9</code></a> Merge pull request <a href="">#408</a> from adisivaprasad/bump-setup-python-v6</li>
<li><a href=""><code>a6c5088</code></a> Bump actions/setup-python from v5.6.0 to v6.2.0</li>
<li>See full diff in <a href="https://github.com/pypa/gh-action-pypi-publish/compare/cef221092ed1bacb1cc03d23a2d87d1d172e277b...ba38be9e461d3875417946c167d0b5f3d385a247">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/upload-sarif` from 4.37.0 to 4.37.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/upload-sarif's releases</a>.</em></p>
<blockquote>
<h2>v4.37.3</h2>
<p>No user facing changes.</p>
<h2>v4.37.2</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
<li>The CodeQL Action can now make use of <a href="https://docs.github.com/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries">configured private registries</a> in Default Setup to retrieve CodeQL configuration files from remote repositories that require authentication. This will allow customers to store their CodeQL configuration in a single repository that can then be referenced by Default Setup workflows in other repositories. We expect to roll this and other, related changes out to everyone in July. <a href="">#4007</a></li>
</ul>
<h2>v4.37.1</h2>
<ul>
<li><em>Upcoming breaking change</em>: Add a deprecation warning for customers using CodeQL version 2.20.6 and earlier. These versions of CodeQL were discontinued on 1 July 2026 alongside GitHub Enterprise Server 3.16, and will be unsupported by the next minor release of the CodeQL Action. <a href="">#3956</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.1">2.26.1</a>. <a href="">#4019</a></li>
</ul>
</blockquote>
</details>
<details>
<summary>Changelog</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/blob/main/CHANGELOG.md">github/codeql-action/upload-sarif's changelog</a>.</em></p>
<blockquote>
<h1>CodeQL Action Changelog</h1>
<p>See the <a href="https://github.com/github/codeql-action/releases">releases page</a> for the relevant changes to the CodeQL CLI and language packs.</p>
<h2>[UNRELEASED]</h2>
<p>No user facing changes.</p>
<h2>4.37.3 - 22 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.2 - 21 Jul 2026</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
<li>The CodeQL Action can now make use of <a href="https://docs.github.com/en/code-security/how-tos/secure-at-scale/configure-organization-security/manage-usage-and-access/giving-org-access-private-registries">configured private registries</a> in Default Setup to retrieve CodeQL configuration files from remote repositories that require authentication. This will allow customers to store their CodeQL configuration in a single repository that can then be referenced by Default Setup workflows in other repositories. We expect to roll this and other, related changes out to everyone in July. <a href="">#4007</a></li>
</ul>
<h2>4.37.1 - 16 Jul 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: Add a deprecation warning for customers using CodeQL version 2.20.6 and earlier. These versions of CodeQL were discontinued on 1 July 2026 alongside GitHub Enterprise Server 3.16, and will be unsupported by the next minor release of the CodeQL Action. <a href="">#3956</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.1">2.26.1</a>. <a href="">#4019</a></li>
</ul>
<h2>4.37.0 - 08 Jul 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.0">2.26.0</a>. <a href="">#3995</a></li>
<li>In addition to the existing input format, the <code>config-file</code> input for the <code>codeql-action/init</code> step will soon support a new <code>[owner/]repo[@ref][:path]</code> format. All components except the repository name are optional. If omitted, <code>owner</code> defaults to the same owner as the repository the analysis is running for, <code>ref</code> to <code>main</code>, and <code>path</code> to <code>.github/codeql-action.yaml</code>. Support for this format ships in this version of the CodeQL Action, but will only be enabled over the coming weeks. <a href="">#3973</a></li>
</ul>
<h2>4.36.3 - 01 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.36.2 - 04 Jun 2026</h2>
<ul>
<li>Cache CodeQL CLI version information across Actions steps. <a href="">#3943</a></li>
<li>Reduce requests while waiting for analysis processing by using exponential backoff when polling SARIF processing status. <a href="">#3937</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.25.6">2.25.6</a>. <a href="">#3948</a></li>
</ul>
<h2>4.36.1 - 02 Jun 2026</h2>
<p>No user facing changes.</p>
<h2>4.36.0 - 22 May 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.19.4. <a href="">#3894</a></li>
<li>Add support for SHA-256 Git object IDs. <a href="">#3893</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.25.5">2.25.5</a>. <a href="">#3926</a></li>
</ul>
<h2>4.35.5 - 15 May 2026</h2>
<ul>
<li>We have improved how the JavaScript bundles for the CodeQL Action are generated to avoid duplication across bundles and reduce the size of the repository by around 70%. This should have no effect on the runtime behaviour of the CodeQL Action. <a href="">#3899</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>e4fba86</code></a> Merge pull request <a href="">#4031</a> from github/update-v4.37.3-72f6a9da0</li>
<li><a href=""><code>fb50ab5</code></a> Update changelog for v4.37.3</li>
<li><a href=""><code>72f6a9d</code></a> Merge pull request <a href="">#4030</a> from github/mbg/fix/no-proxy</li>
<li><a href=""><code>3b5ee58</code></a> Use default <code>request</code> options instead of <code>undefined</code></li>
<li><a href=""><code>bfb6be4</code></a> Merge pull request <a href="">#4028</a> from github/mergeback/v4.37.2-to-main-e0647621</li>
<li><a href=""><code>526ab84</code></a> Rebuild</li>
<li><a href=""><code>d6217b9</code></a> Update changelog and version after v4.37.2</li>
<li><a href=""><code>e064762</code></a> Merge pull request <a href="">#4027</a> from github/update-v4.37.2-385bcdc5a</li>
<li><a href=""><code>e0faed8</code></a> Add a couple of change notes</li>
<li><a href=""><code>73aad0e</code></a> Update changelog for v4.37.2</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/99df26d4f13ea111d4ec1a7dddef6063f76b97e9...e4fba868fa4b1b91e1fdab776edc8cfbe6e9fb81">compare view</a></li>
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

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `258b0aa79663`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.