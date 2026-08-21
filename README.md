# AnyRule Distribution

Public, machine-readable rule artifacts for Anywhere. Source code, generators,
tests, and review history remain in a separate private repository; this
repository contains only reviewed distribution files.

## Routing rules

- [Apple Podcasts](https://raw.githubusercontent.com/carolcheng520/anyrule-dist/main/rules/apple-podcasts.arrs) — assign the imported set to the intended proxy.
- [WeChat Ads Reject](https://raw.githubusercontent.com/carolcheng520/anyrule-dist/main/rules/wechat-ads.arrs) — use the file's reviewed REJECT action.

## MITM rules

- [WeChat Ads](https://raw.githubusercontent.com/carolcheng520/anyrule-dist/main/mitm/WeChatAds.amrs) — use with the WeChat Ads Reject routing rule.
- [Tencent Sports Ad Block](https://raw.githubusercontent.com/carolcheng520/anyrule-dist/main/mitm/TencentSportsAdBlock.amrs) — standalone MITM rule with conservative behavior by default.

MITM rules decrypt and modify matching HTTPS traffic. Review their exact
hostnames and rules before enabling them, install only from the URLs above, and
remove the corresponding old subscription only after a successful refresh.

`main` is the mutable update channel. Each distribution commit records the
private source commit, its successful CI run, and the SHA-256 of every rule
artifact. Publication is performed only by the guarded `anywhere-ops` control
plane; web edits and manual file copies are outside the supported workflow.

Public readability does not grant a repository-wide open-source license. See
[NOTICE](NOTICE) for provenance and attribution.
