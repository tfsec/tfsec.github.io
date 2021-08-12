---
title: Custom tag checking with tfsec
author: Owen Rumney
categories: [guide, custom-checks]
---

tfsec has a large number of built-in checks covering the main public cloud providers and key security and best practice rules. We recognised early that individual users and organisations might need to check their Terraform complies with internal compliance requirements. For example, all EC2 instances should have an `Environment` tag.

The solution to this was [custom checks](../docs/custom-checks/){:target="_blank" rel="nofollow noreferrer noopener"}
. Using `json` or `yaml`, new checks can be created to satisfy these compliance and internal requirements.

## Checking tags

This blog post is going to focus on tackling tag checking using custom checks, to learn more about what else can be achieved you can refer to the [custom check documentation](../docs/custom-checks/){:target="_blank" rel="nofollow noreferrer noopener"}.

### Example use case
Lets look at a likely real world use case; a large engineering team might have multiple development environments running in an AWS account with duplicate infrastructure for each of the development teams.

In this scenario, it might be good to filter EC2 instances by team and/or environment both for tag based billing and general asset tracking. You might want to ensure that all EC2 instances created using Terraform have these tags or raise an error.

### Creating the custom check

There are two easy ways to use custom checks; they can go in the root of the Terraform project (wherever the `terraform init` is going to be performed) or they can go in an arbitrary folder and use the `--custom-check-dir` flag to point to the folder at run time.

Check files have the name that ends with `_tfchecks.json` or `_tfchecks.yaml` for them to be included in the run; any prefix is allowable as long as they end with this.

So, what would a custom check file look like for this use case? For this exanple I'm going to stick with `yaml` format as it reduces the noise in the snippets.

Lets start with ensuring that the 

```yml
---
checks:
  - code: valid-environment-tag
    description: Ensure that a valid Environment tag is provided
    errorMessage: The required Environment tag was missing or invalid
    requiredTypes:
    - resource
    requiredLabels:
    - aws_instance
    matchSpec:
      action: contains
      name: tags
      value: 
        Environment:
          action: isAny
          value: 
            - production
            - test
            - dev

    severity: HIGH

```

Breaking this down to its parts, we have;

**code**: the ID that will be shown in the results

**description**: a description of the check

**errorMessage**: the error message to be displayed when the check fails

**requiredTypes**: the block types (resource, data etc) that are to be checked

**requiredLabels**: the Terraform types to check (aws_instance, azurerm_key_vault_secret etc)

**matchSpec**: the conditions that need to be met for the check to pass. In this match spec we are saying that the `aws_instance` must have an attribute `tags` which contains a tag with the name `Environment`. Further to that, it must be one of the values [`production`, `test`, `dev`] to pass the checks.

Other options for this could be `action: isNone` to ensure that these resources aren't beind deployed into a given environment.

**severity**: the level of the check failure that is raised. 

#### Team Tag

Lets now look at the case where we need all `aws_instances` to have a `Team` tag. For this example, lets consider that all teams are 



