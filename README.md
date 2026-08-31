# scoop-tasqx

Scoop bucket for [tasqx](https://github.com/dimitritholen/tasqx), the task
manager that lives in the terminal and treats an AI agent as a normal user.

```console
scoop bucket add tasqx https://github.com/dimitritholen/scoop-tasqx
scoop install tasqx
```

Updating is `scoop update tasqx`.

## How the manifest gets here

`bucket/tasqx.json` is **generated per release**, never edited by hand: the
main repository's `scripts/scoop-manifest.sh <tag>` renders it from the
checksum the release itself publishes, so the manifest cannot disagree with
what a user downloads. It arrives on a branch, the CI in this repository
installs it for real on a Windows runner and runs the binary, and only a green
run merges to `main` — the branch users actually add as a bucket. The
`autoupdate` block additionally lets Scoop's own tooling bump the version
between generations; it templates the same target the generator guards.

Found a problem with the manifest? File it against
[dimitritholen/tasqx](https://github.com/dimitritholen/tasqx/issues); this
repository only carries the rendered output.
