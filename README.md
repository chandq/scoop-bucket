# chandq/scoop-bucket

A [Scoop](https://scoop.sh) bucket for command-line tools published by [chandq](https://github.com/chandq).

Add the bucket **once**, then any app in it can be installed by name:

```powershell
scoop bucket add chandq https://github.com/chandq/scoop-bucket
scoop install <app>
```

## Requirements

- Windows
- [Scoop](https://scoop.sh) — if not installed yet:

  ```powershell
  Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
  Invoke-RestMethod -Uri https://get.scoop.sh | Invoke-Expression
  ```

- Node.js LTS — each app installs it automatically as a dependency (`nodejs-lts`)

## Available apps

| App | Description |
| --- | --- |
| [`mock-service-cli`](mock-service-cli.json) | Local Mock/Static/SPA server, HTTP request proxy, API overview page and File explorer |
| [`mock-service-cli-ultra`](mock-service-cli-ultra.json) | Light edition plus RAR/7z/bzip2/xz archive support |

> This table grows as new apps are added. Run `scoop update` to pick up new versions.

### Example: mock-service-cli

```powershell
scoop install mock-service-cli
mock-service-cli --help
```

Per-tool documentation lives in each tool's own repository:

- [chandq/mock-service-cli](https://github.com/chandq/mock-service-cli)

## Update / Uninstall

```powershell
scoop update <app>
scoop uninstall <app>

scoop bucket rm chandq      # optional: remove the bucket itself
```

## Maintainers

This bucket is updated automatically, not by hand. Each tool is released to npm, and the tool's own `sync-package-managers` workflow mirrors the fresh npm tarball into a manifest here; `checkver` / `autoupdate` let Scoop and ScoopSearch track new versions.

Adding a new tool means adding its `<name>.json` (produced by that tool's release pipeline) **and** a row in the table above. The bucket name and layout never change.

## Discoverability

`scoop.sh` finds this bucket through ScoopSearch, which indexes GitHub repositories carrying the `scoop-bucket` topic.

## License

Third-party bucket. Manifests describe the upstream projects, each under its own license (e.g. mock-service-cli under MIT), and are provided as-is.
