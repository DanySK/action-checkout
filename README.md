# action-checkout
One-shot checkout of a repository with submodules and tags, basically a shorthand for:

```yaml
- uses: actions/checkout@<latest stable>
  with:
    fetch-depth: 0
    submodules: recursive
- shell: bash
  run: git fetch --tags -f
```

The only available option is `token`, that can be used to preconfigure the checked out repository authorization.
If omitted, the value does not get passed to actions/checkout

```
steps:
  - name: Checkout
    uses: danysk/action-checkout@<select the latest stable>
    # optionally
    with:
      token: ${{ secrets.GITHUB_TOKEN }}
      # or any other valid secret, of course
```
