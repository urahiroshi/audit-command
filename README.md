# orb-npm-audit

This repository contains source code for `npm-audit` Orb
https://circleci.com/orbs/registry/orb/urahiroshi/npm-audit

# Orb usage

```yaml
orbs:
  audit: urahiroshi/npm-audit@1.0.4

jobs:
  audit:
    executor: audit/default
    steps:
      - checkout
      - audit/audit_diff:
          # save diff to .diff.log (if there is no diff, this file will be empty)
          diff_out: .diff.log
          # cache key for preserving `npm audit` result (fixed by jq)
          cache_key_prefix: npm-audit-{{ .Branch }}
```
