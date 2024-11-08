# Pre-Commit

A set of git pre-commit hooks, including for use with [encore.dev](https://encore.dev/go).

## Prerequisites
- https://pre-commit.com/ framework to be installed

## Installation
Use tge following in your .pre-commit-config.yaml file:
```yaml
- repo: https://github.com/echarrod/pre-commit
  rev: main
  hooks:
    # Select one of the following:
    - id: encore-test-mod
    - id: encore-test-pkg
    - id: encore-test-repo-mod
    - id: encore-test-repo-pkg
```

-----------------
### Hook Suffixes
Hooks have suffixes in their name that indicate their targets:

| Suffix      | Target       | Description                                       |
|-------------|--------------|---------------------------------------------------|
| \<none>     | Files        | Targets staged files directly                     |
| `-mod`      | Module       | Targets module root folders of staged `.go` files |
| `-pkg`      | Package      | Targets folders containing staged `.go` files     |
| `-repo-mod` | All Modules  | Targets all module root folders in the repo       |
| `-repo-pkg` | All Packages | Targets all package folders in the repo           |
