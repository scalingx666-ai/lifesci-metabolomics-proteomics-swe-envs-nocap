# Issue

**Title:** Bump the github-actions group with 3 updates

## Description

Bumps the github-actions group with 3 updates: [github/codeql-action/init](https://github.com/github/codeql-action), [github/codeql-action/analyze](https://github.com/github/codeql-action) and [github/codeql-action/upload-sarif](https://github.com/github/codeql-action).

Updates `github/codeql-action/init` from 4.39.1 to 4.39.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/init's releases</a>.</em></p>
<blockquote>
<h2>v4.39.3</h2>
<ul>
<li>Fixed diff-informed alert filtering incorrectly removing alerts in changed files whose paths contain spaces, special characters, or non-ASCII characters. <a href="">#4283</a></li>
</ul>
<h2>v4.39.2</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.4">2.27.4</a>. <a href="">#4284</a></li>
<li><em>Upcoming breaking change</em>: CodeQL version 2.22.3 and earlier were discontinued on 16 October 2026 alongside GitHub Enterprise Server 3.18, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4266</a></li>
<li>Starting with macOS 27 and Xcode 27, traced analyses are unsupported. See <a href="https://github.blog/changelog/2026-10-19-codeql-changes-for-macos-27-xcode-27-and-swift-6-4/">this blog post for more information</a>. The CodeQL Action will now try to identify if a workflow is about to perform a traced analysis on version 27 or above of macOS or Xcode. If so, the CodeQL Action will emit a corresponding warning that will also be visible on the <a href="https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning">Tool Status Page</a>. This check will be rolled out following this release of the CodeQL Action. <a href="">#4221</a></li>
<li>The undocumented TRAP cache cleanup feature that could be enabled using the <code>CODEQL_ACTION_CLEANUP_TRAP_CACHES</code> environment variable has been removed, as announced in the release notes for CodeQL Action 4.35.2. The <code>analyze</code> Action now warns if this environment variable is set. If you used TRAP cache cleanup to limit Actions cache usage, we recommend disabling TRAP caching by passing the <code>trap-caching: false</code> input to the <code>init</code> Action. <a href="">#4243</a></li>
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
<h2>4.39.3 - 04 Nov 2026</h2>
<ul>
<li>Fixed diff-informed alert filtering incorrectly removing alerts in changed files whose paths contain spaces, special characters, or non-ASCII characters. <a href="">#4283</a></li>
</ul>
<h2>4.39.2 - 03 Nov 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.4">2.27.4</a>. <a href="">#4284</a></li>
<li><em>Upcoming breaking change</em>: CodeQL version 2.22.3 and earlier were discontinued on 16 October 2026 alongside GitHub Enterprise Server 3.18, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4266</a></li>
<li>Starting with macOS 27 and Xcode 27, traced analyses are unsupported. See <a href="https://github.blog/changelog/2026-10-19-codeql-changes-for-macos-27-xcode-27-and-swift-6-4/">this blog post for more information</a>. The CodeQL Action will now try to identify if a workflow is about to perform a traced analysis on version 27 or above of macOS or Xcode. If so, the CodeQL Action will emit a corresponding warning that will also be visible on the <a href="https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning">Tool Status Page</a>. This check will be rolled out following this release of the CodeQL Action. <a href="">#4221</a></li>
<li>The undocumented TRAP cache cleanup feature that could be enabled using the <code>CODEQL_ACTION_CLEANUP_TRAP_CACHES</code> environment variable has been removed, as announced in the release notes for CodeQL Action 4.35.2. The <code>analyze</code> Action now warns if this environment variable is set. If you used TRAP cache cleanup to limit Actions cache usage, we recommend disabling TRAP caching by passing the <code>trap-caching: false</code> input to the <code>init</code> Action. <a href="">#4243</a></li>
</ul>
<h2>4.39.1 - 21 Oct 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>4.39.0 - 15 Oct 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
<h2>4.38.3 - 08 Oct 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: CodeQL version 2.21.2 and earlier were discontinued on 24 September 2026 alongside GitHub Enterprise Server 3.17, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4188</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.2">2.27.2</a>. <a href="">#4203</a></li>
<li>Fixed a bug where the decision of whether to use a per-language bundle did not account for custom configurations that reference queries outside of compiled CodeQL packs. This issue was caught during internal testing and did not affect any customer repositories. We will resume the roll out of per-language bundles in the coming weeks. <a href="">#4184</a></li>
</ul>
<h2>4.38.2 - 24 Sept 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.1">2.27.1</a>. <a href="">#4160</a></li>
</ul>
<h2>4.38.1 - 18 Sept 2026</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
</ul>
<h2>4.38.0 - 09 Sept 2026</h2>
<ul>
<li>On GitHub-hosted runners, the CodeQL Action now deletes unused CodeQL bundles from the toolcache before downloading a different bundle, which frees up disk space for the analysis. We expect to roll this change out to everyone in September. <a href="">#4124</a></li>
<li>The CodeQL Action now supports CodeQL releases that are compatible with Linux Arm64 and downloads the native <code>linux-arm64</code> CodeQL bundle when available. <a href="">#4072</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.0">2.27.0</a>. <a href="">#4129</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>33d7b85</code></a> Merge pull request <a href="">#4299</a> from github/update-v4.39.3-064910ba2</li>
<li><a href=""><code>24393f8</code></a> Update changelog for v4.39.3</li>
<li><a href=""><code>064910b</code></a> Merge pull request <a href="">#4297</a> from github/mbg/update-glob</li>
<li><a href=""><code>f532ac5</code></a> Update <code>glob</code> to <code>14.0.3</code></li>
<li><a href=""><code>8cd4dfa</code></a> Merge pull request <a href="">#4280</a> from github/mbg/ci/validate-yaml</li>
<li><a href=""><code>cea289b</code></a> Return different exit code when a language is not recognised</li>
<li><a href=""><code>7287bb3</code></a> Remove <code>exclude</code> entry that's no longer needed</li>
<li><a href=""><code>8eb7cdf</code></a> Use normal <code>.editorconfig</code> pattern</li>
<li><a href=""><code>160e547</code></a> Merge remote-tracking branch 'origin/main' into mbg/ci/validate-yaml</li>
<li><a href=""><code>913e1bb</code></a> Merge pull request <a href="">#4283</a> from github/sam-robson/decode-diff-informed-sarif-uris</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/9b3254085494b55a0f7c4c2b3d2d52cc712ce370...33d7b85da1a04171e211befe2c739303b9a4c066">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/analyze` from 4.39.1 to 4.39.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/analyze's releases</a>.</em></p>
<blockquote>
<h2>v4.39.3</h2>
<ul>
<li>Fixed diff-informed alert filtering incorrectly removing alerts in changed files whose paths contain spaces, special characters, or non-ASCII characters. <a href="">#4283</a></li>
</ul>
<h2>v4.39.2</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.4">2.27.4</a>. <a href="">#4284</a></li>
<li><em>Upcoming breaking change</em>: CodeQL version 2.22.3 and earlier were discontinued on 16 October 2026 alongside GitHub Enterprise Server 3.18, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4266</a></li>
<li>Starting with macOS 27 and Xcode 27, traced analyses are unsupported. See <a href="https://github.blog/changelog/2026-10-19-codeql-changes-for-macos-27-xcode-27-and-swift-6-4/">this blog post for more information</a>. The CodeQL Action will now try to identify if a workflow is about to perform a traced analysis on version 27 or above of macOS or Xcode. If so, the CodeQL Action will emit a corresponding warning that will also be visible on the <a href="https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning">Tool Status Page</a>. This check will be rolled out following this release of the CodeQL Action. <a href="">#4221</a></li>
<li>The undocumented TRAP cache cleanup feature that could be enabled using the <code>CODEQL_ACTION_CLEANUP_TRAP_CACHES</code> environment variable has been removed, as announced in the release notes for CodeQL Action 4.35.2. The <code>analyze</code> Action now warns if this environment variable is set. If you used TRAP cache cleanup to limit Actions cache usage, we recommend disabling TRAP caching by passing the <code>trap-caching: false</code> input to the <code>init</code> Action. <a href="">#4243</a></li>
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
<h2>4.39.3 - 04 Nov 2026</h2>
<ul>
<li>Fixed diff-informed alert filtering incorrectly removing alerts in changed files whose paths contain spaces, special characters, or non-ASCII characters. <a href="">#4283</a></li>
</ul>
<h2>4.39.2 - 03 Nov 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.4">2.27.4</a>. <a href="">#4284</a></li>
<li><em>Upcoming breaking change</em>: CodeQL version 2.22.3 and earlier were discontinued on 16 October 2026 alongside GitHub Enterprise Server 3.18, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4266</a></li>
<li>Starting with macOS 27 and Xcode 27, traced analyses are unsupported. See <a href="https://github.blog/changelog/2026-10-19-codeql-changes-for-macos-27-xcode-27-and-swift-6-4/">this blog post for more information</a>. The CodeQL Action will now try to identify if a workflow is about to perform a traced analysis on version 27 or above of macOS or Xcode. If so, the CodeQL Action will emit a corresponding warning that will also be visible on the <a href="https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning">Tool Status Page</a>. This check will be rolled out following this release of the CodeQL Action. <a href="">#4221</a></li>
<li>The undocumented TRAP cache cleanup feature that could be enabled using the <code>CODEQL_ACTION_CLEANUP_TRAP_CACHES</code> environment variable has been removed, as announced in the release notes for CodeQL Action 4.35.2. The <code>analyze</code> Action now warns if this environment variable is set. If you used TRAP cache cleanup to limit Actions cache usage, we recommend disabling TRAP caching by passing the <code>trap-caching: false</code> input to the <code>init</code> Action. <a href="">#4243</a></li>
</ul>
<h2>4.39.1 - 21 Oct 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>4.39.0 - 15 Oct 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
<h2>4.38.3 - 08 Oct 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: CodeQL version 2.21.2 and earlier were discontinued on 24 September 2026 alongside GitHub Enterprise Server 3.17, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4188</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.2">2.27.2</a>. <a href="">#4203</a></li>
<li>Fixed a bug where the decision of whether to use a per-language bundle did not account for custom configurations that reference queries outside of compiled CodeQL packs. This issue was caught during internal testing and did not affect any customer repositories. We will resume the roll out of per-language bundles in the coming weeks. <a href="">#4184</a></li>
</ul>
<h2>4.38.2 - 24 Sept 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.1">2.27.1</a>. <a href="">#4160</a></li>
</ul>
<h2>4.38.1 - 18 Sept 2026</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
</ul>
<h2>4.38.0 - 09 Sept 2026</h2>
<ul>
<li>On GitHub-hosted runners, the CodeQL Action now deletes unused CodeQL bundles from the toolcache before downloading a different bundle, which frees up disk space for the analysis. We expect to roll this change out to everyone in September. <a href="">#4124</a></li>
<li>The CodeQL Action now supports CodeQL releases that are compatible with Linux Arm64 and downloads the native <code>linux-arm64</code> CodeQL bundle when available. <a href="">#4072</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.0">2.27.0</a>. <a href="">#4129</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>33d7b85</code></a> Merge pull request <a href="">#4299</a> from github/update-v4.39.3-064910ba2</li>
<li><a href=""><code>24393f8</code></a> Update changelog for v4.39.3</li>
<li><a href=""><code>064910b</code></a> Merge pull request <a href="">#4297</a> from github/mbg/update-glob</li>
<li><a href=""><code>f532ac5</code></a> Update <code>glob</code> to <code>14.0.3</code></li>
<li><a href=""><code>8cd4dfa</code></a> Merge pull request <a href="">#4280</a> from github/mbg/ci/validate-yaml</li>
<li><a href=""><code>cea289b</code></a> Return different exit code when a language is not recognised</li>
<li><a href=""><code>7287bb3</code></a> Remove <code>exclude</code> entry that's no longer needed</li>
<li><a href=""><code>8eb7cdf</code></a> Use normal <code>.editorconfig</code> pattern</li>
<li><a href=""><code>160e547</code></a> Merge remote-tracking branch 'origin/main' into mbg/ci/validate-yaml</li>
<li><a href=""><code>913e1bb</code></a> Merge pull request <a href="">#4283</a> from github/sam-robson/decode-diff-informed-sarif-uris</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/9b3254085494b55a0f7c4c2b3d2d52cc712ce370...33d7b85da1a04171e211befe2c739303b9a4c066">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/upload-sarif` from 4.39.1 to 4.39.3
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/upload-sarif's releases</a>.</em></p>
<blockquote>
<h2>v4.39.3</h2>
<ul>
<li>Fixed diff-informed alert filtering incorrectly removing alerts in changed files whose paths contain spaces, special characters, or non-ASCII characters. <a href="">#4283</a></li>
</ul>
<h2>v4.39.2</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.4">2.27.4</a>. <a href="">#4284</a></li>
<li><em>Upcoming breaking change</em>: CodeQL version 2.22.3 and earlier were discontinued on 16 October 2026 alongside GitHub Enterprise Server 3.18, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4266</a></li>
<li>Starting with macOS 27 and Xcode 27, traced analyses are unsupported. See <a href="https://github.blog/changelog/2026-10-19-codeql-changes-for-macos-27-xcode-27-and-swift-6-4/">this blog post for more information</a>. The CodeQL Action will now try to identify if a workflow is about to perform a traced analysis on version 27 or above of macOS or Xcode. If so, the CodeQL Action will emit a corresponding warning that will also be visible on the <a href="https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning">Tool Status Page</a>. This check will be rolled out following this release of the CodeQL Action. <a href="">#4221</a></li>
<li>The undocumented TRAP cache cleanup feature that could be enabled using the <code>CODEQL_ACTION_CLEANUP_TRAP_CACHES</code> environment variable has been removed, as announced in the release notes for CodeQL Action 4.35.2. The <code>analyze</code> Action now warns if this environment variable is set. If you used TRAP cache cleanup to limit Actions cache usage, we recommend disabling TRAP caching by passing the <code>trap-caching: false</code> input to the <code>init</code> Action. <a href="">#4243</a></li>
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
<h2>4.39.3 - 04 Nov 2026</h2>
<ul>
<li>Fixed diff-informed alert filtering incorrectly removing alerts in changed files whose paths contain spaces, special characters, or non-ASCII characters. <a href="">#4283</a></li>
</ul>
<h2>4.39.2 - 03 Nov 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.4">2.27.4</a>. <a href="">#4284</a></li>
<li><em>Upcoming breaking change</em>: CodeQL version 2.22.3 and earlier were discontinued on 16 October 2026 alongside GitHub Enterprise Server 3.18, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4266</a></li>
<li>Starting with macOS 27 and Xcode 27, traced analyses are unsupported. See <a href="https://github.blog/changelog/2026-10-19-codeql-changes-for-macos-27-xcode-27-and-swift-6-4/">this blog post for more information</a>. The CodeQL Action will now try to identify if a workflow is about to perform a traced analysis on version 27 or above of macOS or Xcode. If so, the CodeQL Action will emit a corresponding warning that will also be visible on the <a href="https://docs.github.com/en/code-security/how-tos/find-and-fix-code-vulnerabilities/manage-your-configuration/use-the-tools-status-page-for-code-scanning">Tool Status Page</a>. This check will be rolled out following this release of the CodeQL Action. <a href="">#4221</a></li>
<li>The undocumented TRAP cache cleanup feature that could be enabled using the <code>CODEQL_ACTION_CLEANUP_TRAP_CACHES</code> environment variable has been removed, as announced in the release notes for CodeQL Action 4.35.2. The <code>analyze</code> Action now warns if this environment variable is set. If you used TRAP cache cleanup to limit Actions cache usage, we recommend disabling TRAP caching by passing the <code>trap-caching: false</code> input to the <code>init</code> Action. <a href="">#4243</a></li>
</ul>
<h2>4.39.1 - 21 Oct 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.3">2.27.3</a>. <a href="">#4256</a></li>
</ul>
<h2>4.39.0 - 15 Oct 2026</h2>
<ul>
<li><em>Breaking change</em>: Bump the minimum required CodeQL bundle version to 2.20.7. <a href="">#4205</a></li>
<li>The <code>codeql-action/analyze</code> step now validates that a correct argument for the <code>checkout_path</code> input has been provided. The <code>checkout_path</code> input must be set to the path where the repository that is being analyzed is checked out at on the runner, if that path is something other than the workspace root. If the path does not point to a repository checkout or is different from the path that was used by <code>codeql-action/init</code>, then the CodeQL Action now produces a warning. <a href="">#4148</a></li>
<li>Resolved an issue with third-party caching implementations that prevented caches from being restored correctly. <a href="">#4206</a></li>
<li>The <code>codeql-action/start-proxy</code> step that is used in Code Scanning Default Setup now finds CodeQL releases using the same logic as <code>codeql-action/init</code>. This primarily benefits customers who are using GitHub instances other than <code>github.com</code> where the <code>codeql-action/start-proxy</code> step may previously have been unable to locate recent releases and ended up using outdated versions of the private registry authentication proxy as a result. <a href="">#4198</a></li>
</ul>
<h2>4.38.3 - 08 Oct 2026</h2>
<ul>
<li><em>Upcoming breaking change</em>: CodeQL version 2.21.2 and earlier were discontinued on 24 September 2026 alongside GitHub Enterprise Server 3.17, and will be unsupported by the next minor release of the CodeQL Action. Added a deprecation warning for customers using these versions of CodeQL. <a href="">#4188</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.2">2.27.2</a>. <a href="">#4203</a></li>
<li>Fixed a bug where the decision of whether to use a per-language bundle did not account for custom configurations that reference queries outside of compiled CodeQL packs. This issue was caught during internal testing and did not affect any customer repositories. We will resume the roll out of per-language bundles in the coming weeks. <a href="">#4184</a></li>
</ul>
<h2>4.38.2 - 24 Sept 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.1">2.27.1</a>. <a href="">#4160</a></li>
</ul>
<h2>4.38.1 - 18 Sept 2026</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
</ul>
<h2>4.38.0 - 09 Sept 2026</h2>
<ul>
<li>On GitHub-hosted runners, the CodeQL Action now deletes unused CodeQL bundles from the toolcache before downloading a different bundle, which frees up disk space for the analysis. We expect to roll this change out to everyone in September. <a href="">#4124</a></li>
<li>The CodeQL Action now supports CodeQL releases that are compatible with Linux Arm64 and downloads the native <code>linux-arm64</code> CodeQL bundle when available. <a href="">#4072</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.27.0">2.27.0</a>. <a href="">#4129</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>33d7b85</code></a> Merge pull request <a href="">#4299</a> from github/update-v4.39.3-064910ba2</li>
<li><a href=""><code>24393f8</code></a> Update changelog for v4.39.3</li>
<li><a href=""><code>064910b</code></a> Merge pull request <a href="">#4297</a> from github/mbg/update-glob</li>
<li><a href=""><code>f532ac5</code></a> Update <code>glob</code> to <code>14.0.3</code></li>
<li><a href=""><code>8cd4dfa</code></a> Merge pull request <a href="">#4280</a> from github/mbg/ci/validate-yaml</li>
<li><a href=""><code>cea289b</code></a> Return different exit code when a language is not recognised</li>
<li><a href=""><code>7287bb3</code></a> Remove <code>exclude</code> entry that's no longer needed</li>
<li><a href=""><code>8eb7cdf</code></a> Use normal <code>.editorconfig</code> pattern</li>
<li><a href=""><code>160e547</code></a> Merge remote-tracking branch 'origin/main' into mbg/ci/validate-yaml</li>
<li><a href=""><code>913e1bb</code></a> Merge pull request <a href="">#4283</a> from github/sam-robson/decode-diff-informed-sarif-uris</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/9b3254085494b55a0f7c4c2b3d2d52cc712ce370...33d7b85da1a04171e211befe2c739303b9a4c066">compare view</a></li>
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