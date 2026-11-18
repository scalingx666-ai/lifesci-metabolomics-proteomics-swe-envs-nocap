# Issue

**Title:** Bump the github-actions group with 3 updates

## Description

Bumps the github-actions group with 3 updates: [github/codeql-action/init](https://github.com/github/codeql-action), [github/codeql-action/analyze](https://github.com/github/codeql-action) and [github/codeql-action/upload-sarif](https://github.com/github/codeql-action).

Updates `github/codeql-action/init` from 4.38.0 to 4.38.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/init's releases</a>.</em></p>
<blockquote>
<h2>v4.38.1</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
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
<h2>4.37.9 - 26 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.4">2.26.4</a>. <a href="">#4106</a></li>
</ul>
<h2>4.37.8 - 21 Aug 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.7 - 13 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.3">2.26.3</a>. <a href="">#4085</a></li>
</ul>
<h2>4.37.6 - 04 Aug 2026</h2>
<ul>
<li>Changed the default filepath for the new remote file address format that was introduced in CodeQL Action 4.37.0 / 3.37.0 to <code>.github/codeql-config.yml</code> to align it with the suggested path that is used elsewhere. <a href="">#4070</a></li>
</ul>
<h2>4.37.5 - 03 Aug 2026</h2>
<ul>
<li>Fixed a bug where a network error while streaming the download of the CodeQL bundle could terminate the <code>init</code> Action instead of falling back to downloading the bundle before extracting it. <a href="">#4061</a></li>
</ul>
<h2>4.37.4 - 29 Jul 2026</h2>
<ul>
<li>This version of the CodeQL Action adds support for the <code>tools</code> input for the <code>codeql-action/init</code> step to be specified using a <code>github-codeql-tools</code> <a href="https://docs.github.com/en/organizations/managing-organization-settings/managing-custom-properties-for-repositories-in-your-organization">repository property</a>. This feature will gradually be rolled out following the release of this version. Once rolled out, this allows for the CodeQL CLI version that is used in GitHub-managed workflows, such as Default Setup, to be set to a custom value. For example, customers who run into issues with rate limits when a new CodeQL CLI version is released can set the value to <code>toolcache</code> to always use the CodeQL CLI version that is available in the runner toolcache. For Advanced Setup workflows, the value provided for <code>tools</code> in the workflow definition always takes precedence unless the value of the repository property starts with <code>!</code>. <a href="">#4037</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.2">2.26.2</a>. <a href="">#4051</a></li>
</ul>
<h2>4.37.3 - 22 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.2 - 21 Jul 2026</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>1c5b675</code></a> Merge pull request <a href="">#4152</a> from github/update-v4.38.1-a65b83a73</li>
<li><a href=""><code>a97cdca</code></a> Add changelog entry for <a href="">#4146</a></li>
<li><a href=""><code>cc6c691</code></a> Update changelog for v4.38.1</li>
<li><a href=""><code>a65b83a</code></a> Merge pull request <a href="">#4146</a> from github/henrymercer/per-language-bundles-pr</li>
<li><a href=""><code>07fa87d</code></a> Clarify the latest-nightly eligibility exception</li>
<li><a href=""><code>f18f353</code></a> Describe the bundle URL resolver</li>
<li><a href=""><code>ecec9b5</code></a> Share per-language telemetry fields without renaming</li>
<li><a href=""><code>79fe3a1</code></a> Move download telemetry into the status-report directory</li>
<li><a href=""><code>ead1f7d</code></a> Rename the platform module</li>
<li><a href=""><code>549d498</code></a> Simplify per-language platform eligibility checks</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/b96794f015dfd88f77b49b1c93e0fa7110f94c63...1c5b675653bb5c22dbe9b12b556ec555138e09fd">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/analyze` from 4.38.0 to 4.38.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/analyze's releases</a>.</em></p>
<blockquote>
<h2>v4.38.1</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
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
<h2>4.37.9 - 26 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.4">2.26.4</a>. <a href="">#4106</a></li>
</ul>
<h2>4.37.8 - 21 Aug 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.7 - 13 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.3">2.26.3</a>. <a href="">#4085</a></li>
</ul>
<h2>4.37.6 - 04 Aug 2026</h2>
<ul>
<li>Changed the default filepath for the new remote file address format that was introduced in CodeQL Action 4.37.0 / 3.37.0 to <code>.github/codeql-config.yml</code> to align it with the suggested path that is used elsewhere. <a href="">#4070</a></li>
</ul>
<h2>4.37.5 - 03 Aug 2026</h2>
<ul>
<li>Fixed a bug where a network error while streaming the download of the CodeQL bundle could terminate the <code>init</code> Action instead of falling back to downloading the bundle before extracting it. <a href="">#4061</a></li>
</ul>
<h2>4.37.4 - 29 Jul 2026</h2>
<ul>
<li>This version of the CodeQL Action adds support for the <code>tools</code> input for the <code>codeql-action/init</code> step to be specified using a <code>github-codeql-tools</code> <a href="https://docs.github.com/en/organizations/managing-organization-settings/managing-custom-properties-for-repositories-in-your-organization">repository property</a>. This feature will gradually be rolled out following the release of this version. Once rolled out, this allows for the CodeQL CLI version that is used in GitHub-managed workflows, such as Default Setup, to be set to a custom value. For example, customers who run into issues with rate limits when a new CodeQL CLI version is released can set the value to <code>toolcache</code> to always use the CodeQL CLI version that is available in the runner toolcache. For Advanced Setup workflows, the value provided for <code>tools</code> in the workflow definition always takes precedence unless the value of the repository property starts with <code>!</code>. <a href="">#4037</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.2">2.26.2</a>. <a href="">#4051</a></li>
</ul>
<h2>4.37.3 - 22 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.2 - 21 Jul 2026</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>1c5b675</code></a> Merge pull request <a href="">#4152</a> from github/update-v4.38.1-a65b83a73</li>
<li><a href=""><code>a97cdca</code></a> Add changelog entry for <a href="">#4146</a></li>
<li><a href=""><code>cc6c691</code></a> Update changelog for v4.38.1</li>
<li><a href=""><code>a65b83a</code></a> Merge pull request <a href="">#4146</a> from github/henrymercer/per-language-bundles-pr</li>
<li><a href=""><code>07fa87d</code></a> Clarify the latest-nightly eligibility exception</li>
<li><a href=""><code>f18f353</code></a> Describe the bundle URL resolver</li>
<li><a href=""><code>ecec9b5</code></a> Share per-language telemetry fields without renaming</li>
<li><a href=""><code>79fe3a1</code></a> Move download telemetry into the status-report directory</li>
<li><a href=""><code>ead1f7d</code></a> Rename the platform module</li>
<li><a href=""><code>549d498</code></a> Simplify per-language platform eligibility checks</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/b96794f015dfd88f77b49b1c93e0fa7110f94c63...1c5b675653bb5c22dbe9b12b556ec555138e09fd">compare view</a></li>
</ul>
</details>
<br />

Updates `github/codeql-action/upload-sarif` from 4.38.0 to 4.38.1
<details>
<summary>Release notes</summary>
<p><em>Sourced from <a href="https://github.com/github/codeql-action/releases">github/codeql-action/upload-sarif's releases</a>.</em></p>
<blockquote>
<h2>v4.38.1</h2>
<ul>
<li>The CodeQL Action now has experimental support for CodeQL releases for which per-language bundles are available. Per-language bundles support analysis for a single language and are therefore smaller than the combined bundles that allow analysis for all supported languages. As a result, per-language bundles take up less space on disk and are faster to download. We expect to roll this change out to everyone in the coming weeks. <a href="">#4146</a></li>
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
<h2>4.37.9 - 26 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.4">2.26.4</a>. <a href="">#4106</a></li>
</ul>
<h2>4.37.8 - 21 Aug 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.7 - 13 Aug 2026</h2>
<ul>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.3">2.26.3</a>. <a href="">#4085</a></li>
</ul>
<h2>4.37.6 - 04 Aug 2026</h2>
<ul>
<li>Changed the default filepath for the new remote file address format that was introduced in CodeQL Action 4.37.0 / 3.37.0 to <code>.github/codeql-config.yml</code> to align it with the suggested path that is used elsewhere. <a href="">#4070</a></li>
</ul>
<h2>4.37.5 - 03 Aug 2026</h2>
<ul>
<li>Fixed a bug where a network error while streaming the download of the CodeQL bundle could terminate the <code>init</code> Action instead of falling back to downloading the bundle before extracting it. <a href="">#4061</a></li>
</ul>
<h2>4.37.4 - 29 Jul 2026</h2>
<ul>
<li>This version of the CodeQL Action adds support for the <code>tools</code> input for the <code>codeql-action/init</code> step to be specified using a <code>github-codeql-tools</code> <a href="https://docs.github.com/en/organizations/managing-organization-settings/managing-custom-properties-for-repositories-in-your-organization">repository property</a>. This feature will gradually be rolled out following the release of this version. Once rolled out, this allows for the CodeQL CLI version that is used in GitHub-managed workflows, such as Default Setup, to be set to a custom value. For example, customers who run into issues with rate limits when a new CodeQL CLI version is released can set the value to <code>toolcache</code> to always use the CodeQL CLI version that is available in the runner toolcache. For Advanced Setup workflows, the value provided for <code>tools</code> in the workflow definition always takes precedence unless the value of the repository property starts with <code>!</code>. <a href="">#4037</a></li>
<li>Update default CodeQL bundle version to <a href="https://github.com/github/codeql-action/releases/tag/codeql-bundle-v2.26.2">2.26.2</a>. <a href="">#4051</a></li>
</ul>
<h2>4.37.3 - 22 Jul 2026</h2>
<p>No user facing changes.</p>
<h2>4.37.2 - 21 Jul 2026</h2>
<ul>
<li>The new address format for the <code>config-file</code> input that was introduced in CodeQL Action 4.37.0 is now enabled by default. In addition to the format described there, the <code>remote=</code> prefix can now be used to explicitly indicate that the input refers to a remote file. All previous input formats continue to be accepted as well. <a href="">#4023</a></li>
</ul>
<!-- raw HTML omitted -->
</blockquote>
<p>... (truncated)</p>
</details>
<details>
<summary>Commits</summary>
<ul>
<li><a href=""><code>1c5b675</code></a> Merge pull request <a href="">#4152</a> from github/update-v4.38.1-a65b83a73</li>
<li><a href=""><code>a97cdca</code></a> Add changelog entry for <a href="">#4146</a></li>
<li><a href=""><code>cc6c691</code></a> Update changelog for v4.38.1</li>
<li><a href=""><code>a65b83a</code></a> Merge pull request <a href="">#4146</a> from github/henrymercer/per-language-bundles-pr</li>
<li><a href=""><code>07fa87d</code></a> Clarify the latest-nightly eligibility exception</li>
<li><a href=""><code>f18f353</code></a> Describe the bundle URL resolver</li>
<li><a href=""><code>ecec9b5</code></a> Share per-language telemetry fields without renaming</li>
<li><a href=""><code>79fe3a1</code></a> Move download telemetry into the status-report directory</li>
<li><a href=""><code>ead1f7d</code></a> Rename the platform module</li>
<li><a href=""><code>549d498</code></a> Simplify per-language platform eligibility checks</li>
<li>Additional commits viewable in <a href="https://github.com/github/codeql-action/compare/b96794f015dfd88f77b49b1c93e0fa7110f94c63...1c5b675653bb5c22dbe9b12b556ec555138e09fd">compare view</a></li>
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