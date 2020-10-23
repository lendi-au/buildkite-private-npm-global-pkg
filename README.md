# Private Global NPM Packages

A [Buildkite plugin](https://buildkite.com/docs/agent/v3/plugins) to utilise
global installations of npm packages in your builds.
This is particularly useful if you need to access private packages.

## Prerequisites

Node installation on your Buildkite agents.

## Install a npm package as global

```yml
steps:
  - plugins:
    - lendi-au/npm-global:
          env: "NPM_TOKEN"
          package: "@private-org/package"
```

## Custom registry support

We have a custom registry which uses basic authentication rather than a
typical `NPM_TOKEN`.

```yml
steps:
  - plugins:
    - lendi-au/npm-global:
          token: "echo -n user:password | openssl base64"
          authtype: "BASIC"
          registry: "https://my-registry.example.org"
          package: "@private-org/package"
```
