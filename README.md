# gitlab-pipeline-deleter

[![GitHub Actions status](https://github.com/screendriver/gitlab-pipeline-deleter/workflows/CI/badge.svg)](https://github.com/screendriver/gitlab-pipeline-deleter/actions)
[![codecov](https://codecov.io/gh/screendriver/gitlab-pipeline-deleter/branch/main/graph/badge.svg)](https://codecov.io/gh/screendriver/gitlab-pipeline-deleter)

A Node.js CLI tool that deletes old [GitLab CI](https://docs.gitlab.com/ee/ci/) pipelines.

### Installation

```sh
$ npm install -g gitlab-pipeline-deleter
```

### Usage

```
Usage: glpd [options] [gitlab-url] [project-id] [access-token]

Deletes old GitLab pipelines

Options:
  -d --days <days>  older than days (default: "30")
  --trace           show stack traces for errors when possible (default: false)
  -h, --help        display help for command
```

You can use either the command line arguments `gitlab-url`, `project-id` and `access-token` or you can create a `glpdrc.js` configuration file that exports an object. All of the command line arguments are supported but needs to be written in `camelCase`:

```js
module.exports = {
  gitlabUrl: 'https://example.com',
  projectId: 42,
  accessToken: '<my-token>',
  days: 30,
  trace: false,
};
```
