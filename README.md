# Zig Release Action

Automatically creates and publishes GitHub releases for Zig projects when the version is updated.

## Usage

Here is an example workflow that uses the `zig-release` action:
```yaml
name: Create Release
on:
  push:
    branches:
      - main  # your main branch
    paths:
      - 'build.zig.zon'

jobs:
  release:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
        with:
          fetch-depth: 0

      - uses: jokelbaf/zig-release@master
```

## Inputs

- `cliff_template` (optional): URL to custom git-cliff template configuration
- `zig_zon_path` (optional): Path to build.zig.zon file (default: `build.zig.zon`)

## Acknowledgements

[Seria's](https://github.com/seriaati) [create-release](https://github.com/seriaati/create-release) action (for python) was used as a reference for this action.
