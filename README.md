github-actions-macos-13-xcode-versions
======================================

An unofficial partial mirror repository of [actions/runner-images](https://github.com/actions/runner-images).

This repository is useful for tracking Xcode updates of macOS 13 image.

:warning: Currently macOS 13 image has not been released yet so this repository has no releases for now.

Usage examples
--------------

- You can see tool set changes between versions on [mirror](https://github.com/manicmaniac/github-actions-macos-13-xcode-versions/tree/mirror) branch.
- By subscribing this repositories' releases, you can receive notifications that tell new Xcode becomes available on GitHub Actions.
- You can subscribe [RSS feed](https://github.com/manicmaniac/github-actions-macos-13-xcode-versions/releases.atom) with [Slack RSS app](https://slack.com/apps/A0F81R7U7-rss) to send Slack message as soon as new Xcode version becomes available on GitHub Actions.
- You can automate Xcode upgrading in your repositories with [Renovate](https://github.com/renovatebot/renovate).

Renovate configuration examples
-------------------------------

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": [
    "config:base"
  ],
  "regexManagers": [
    {
      "fileMatch": "^\\.github/workflows/.+\\.yml$",
      "matchStrings": [
        "/Applications/Xcode_${{ currentValue }}.app/Contents/Developer"
      ],
      "depNameTemplate": "manicmaniac/github-actions-macos-13-xcode-versions",
      "datasourceTemplate": "github-releases"
    }
  ]
}
```
