---
title: New User-friendly IDs
author: tfsec
categories: [news, release]
---

In preparation for our v1 release, we've been looking at ways to make tfsec easier to use. A common complaint among the community has been that the current check identifiers are hard to relate to particular checks - e.g. `AWS099` is not a particularly meaningful string.

Thus, we've decided to switch to a new format that conveys more meaning. The previous "legacy" check IDs will still work alongside the new ones in ignore rules and config files. The output will now use our new format and list legacy IDs for results where applicable. New rules will not have a legacy ID assigned.

![New ID Format Example](/assets/img/new-ids.png)

The new identifiers consist of 3 parts: cloud provider, service, and a descriptive *shortcode*. For example: `aws-s3-block-public-acls`. This identifies the rule as related to the AWS S3 service, and the shortcode indicates the rule content.
