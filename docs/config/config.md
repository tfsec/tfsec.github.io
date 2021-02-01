---
title: Config
permalink: /docs/config/
has_children: true
has_toc: no
nav_order: 10
---

## Severity Overrides

There are occasions where the default severity level for one of the built in checks is too severe or in some cases not strong enough. 

The config file can be used to specify overrides for any check identifier to replace the result output.

The structure of the config file can be either `json` or `yaml` and is passed using the `--config-file` argument at runtime.

```json
{
  "severity_overrides": {
    "CUS002": "ERROR",
    "AWS025": "WARNING"
  }
}
``` 

or 

```yaml
---
severity_overrides:
  CUS002: ERROR
  AWS025: INFO
```

## Ignoring warnings

You may wish to ignore some warnings. If you'd like to do so, you can
simply add a comment containing `tfsec:ignore:<RULE>` to the offending
line in your templates. If the problem refers to a block of code, such
as a multiline string, you can add the comment on the line above the
block, by itself.

For example, to ignore an open security group rule:

```hcl
resource "aws_security_group_rule" "my-rule" {
    type = "ingress"
    cidr_blocks = ["0.0.0.0/0"] #tfsec:ignore:AWS006
}
```

or

```hcl
resource "aws_security_group_rule" "my-rule" {
    type = "ingress"
    #tfsec:ignore:AWS006
    cidr_blocks = ["0.0.0.0/0"]
}
```

If you're not sure which line to add the comment on, just check the
tfsec output for the line number of the discovered problem.

You can ignore multiple rules by concatenating the rules on a single line:

```hcl
#tfsec:ignore:AWS017 tfsec:ignore:AWS002
resource "aws_s3_bucket" "my-bucket" {
  bucket = "foobar"
  acl    = "private"
}
```

## Excluding checks

There are moments where the list of checks you'd want to exclude becomes larger and larger.
Rather than passing all the excluded checks via the command line, you can use the configuration
entry `exclude` to list them all out. 

```json
{
  "exclude": ["CUS002", "AWS025"]
}
``` 

or 

```yaml
---
exclude:
  - CUS002
  - AWS025
```

## Running with the config

To run tfsec against a Terraform folder called `tf` with the config file `tfsec.yml` you would run 

```
tfsec --config-file tfsec.yml ./tf
```
