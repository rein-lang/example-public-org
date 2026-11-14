# example-public-org

An example [Rein](https://rein-lang.com) program. It sets up a public GitHub organization, step by step. Run it again at any time: each step checks first and changes only what is missing.

1. **Owner check**: the agent must be an owner of the organization.
2. **Profile** (`profile.rein`): display name, description and website, written from the organization's own repositories.
3. **`.github` repository** (`community.rein`): the profile README and the default community health files: code of conduct, contributing guide, security policy, support, issue forms and the pull request template.
4. **Security baseline** (`security.rein`): read-only default repository permission, no public repositories made by members, read-only Actions tokens, and a default code security configuration (dependency graph, Dependabot, secret scanning, push protection). The user approves the changes before they apply.
5. **Public repositories** (`repos.rein`): description, homepage, topics, README, license and private vulnerability reporting. A missing license goes to the user.
6. **Web UI steps** (`manual.rein`): avatar, pinned repositories, verified domain and the two-factor requirement. The API cannot set these, so the program lists only the open ones, with links.

## Install

```sh
rein install -g github:rein-lang/example-public-org
```

## Use

```sh
rein step example-public-org --input org=<organization login>
```

## Develop

Run `git config core.hooksPath .githooks` once. Pushes then run `rein check .`.

## License

MIT
