# Terraspace

## Basic

| # | Command                                                                            | Description |
| - | ---------------------------------------------------------------------------------- | ----------- |
| 1 | `aws-vault exec dev -- env TS_ENV=dev bundler exec terraspace plan [project_name]` | Run plan    |
| 2 | `aws-vault exec dev -- env TS_ENV=dev bundler exec terraspace up [project_name]`   | Apply       |
| 3 | `aws-vault exec dev -- env TS_ENV=dev bundler exec terraspace down [project_name]` | Destroy     |
