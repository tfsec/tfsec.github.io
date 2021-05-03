---
title: tfsec PR Commenter Github Action
author: tfsec
categories: [news, release, github action]
---

In October 2020, the [Thoughtworks Tech Radar](https://www.thoughtworks.com/radar/tools/tfsec{:target="_blank"}) promoted [tfsec](https://tfsec.dev{:target="_blank"}) to Trial status. In the past few months, there has been a flurry of activity to improve performance, rewrite the parsing and add new features.

One of the recent additions is a Github Action that will process your Github Pull Request commits and add comments where there are `tfsec` failures.

## Example

Let's take a possible addition to a code repo where the PR includes the creation of a bucket;

```terraform
resource "aws_s3_bucket" "another-bucket-with-logging" {
  bucket = "my-failing-bucket-no-encryption"

  logging {
    target_bucket = data.aws_s3_bucket.acme-s3-access-logging.id
    target_prefix = "my-failing-bucket-not-encryption/logs/"
  }
}
```

This bucket has logging, but the definition doesn't set up encryption on the bucket. This fails tfsec check `AWS017`.

When the PR is committed, the Github Action runs and comments directly to the PR has failed the tfsec check. Reviewers can now quickly see the issues and act accordingly.

![Failed tfsec check]({{ site.baseurl }}/images/tfsec-pr-committer.png)

## Configuring your project

With Github Actions it is now incredibly easy to add this check to your repositories quickly.

The tfsec PR Commenter is [available in the Marketplace](https://github.com/marketplace/actions/run-tfsec-pr-commenter{:target="_blank"})

The steps are quite simple;

1. In the root of the project there must be a `.github/workflows` directory
2. Create a new file called something like `tfsec_pr_commenter.yml` - the only requirement being that it has the `yml` suffix.
3. The content of the file should be as below
    ```yaml
    name: tfsec-pr-commenter
    on:
      pull_request:
    jobs:
      tfsec_commenter:
        name: tfsec PR commenter
        runs-on: ubuntu-latest

        steps:
          - name: Clone repo
            uses: actions/checkout@master

          - name: tfsec commenter
            uses: tfsec/tfsec-pr-commenter-action@main
            with:
              github_token: {% raw %}${{ secrets.GITHUB_TOKEN }}{% endraw %}
    ```

A quick note on `secrets.GITHUB_TOKEN` - this is created automatically for you when you start using Actions. Additional secrets can be added in the Settings of the project repo, but this one is all you need.

Now, when you go to the `Actions` tab in the Github page for your repo, you can see the action which will run on PR commit.

![Action Tab]({{ site.baseurl }}/images/actions_tab.png)

When the PR has a commit or is closed and reopened, the Github Action will run and add the comment, as below

![Failed tfsec check]({{ site.baseurl }}/images/tfsec-pr-committer.png)

As you can see in the comment, this is a multi line comment. Something is missing from the definition so the error spans the entire `aws_s3_bucket` block.

When there is a specific issue, for example an attribute is set to a value it shouldn't be, the comment is scoped to the single line. This can be seen in the image below;

![Failed tfsec check]({{ site.baseurl }}/images/single_line_pr_commit.png)

For more information on the GitHub Action, check the [docs](/docs/pr-commenter)
