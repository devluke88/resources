# Terraspace

## Basic

| # | Command                                                                                                                                                                         | Description |
| - | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------- |
| 1 | <p><code>aws-vault exec dev -- env TS_ENV=dev bundler exec terraspace plan [project_name]</code><br><code></code><br><code>TS_ENV=dev terraspace plan [project_name]</code></p> | Run plan    |
| 2 | `aws-vault exec dev -- env TS_ENV=dev bundler exec terraspace up [project_name]`                                                                                                | Apply       |
| 3 | `aws-vault exec dev -- env TS_ENV=dev bundler exec terraspace down [project_name]`                                                                                              | Destroy     |
| 4 | terraspace cache clean                                                                                                                                                          |             |
