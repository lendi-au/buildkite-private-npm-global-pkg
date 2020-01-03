# Private Global NPM Packages

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) to utilise global installations of npm packages in your builds. 
This is particularly useful if you need to access private packages.

## Prerequisites

Node installation on your Buildkite agents.

## Install a npm package as global

```yml
steps:
  - plugins:
    - lendi-au/platform-tool:
          env: "NPM_TOKEN"
          package: "@private-org/package"
```