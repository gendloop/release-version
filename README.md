# release-version

## Usage

```yaml
# # Required
#   version:
#     description: 'New version. e.g. v0.0.0'
#     required: true
#     default: 'v0.0.0'
#   token:
#     description: 'Personal token'
#     required: true
#     default: ${{ github.token }}
# # Optional
#   branch:
#     description: 'branch'
#     required: false
#     default: main

name: Release_Version

permissions:
  contents: write
  actions: write

on: 
  push:
    tags:
      - 'v*'

jobs:
  release_version:
    runs-on: windows-latest
    steps:
      - name: releaes-version
        uses: gendloop/release-version@main
        with:
          version: ${{ github.ref_name }}
          token: ${{ secrets.GITHUB_TOKEN }}

```

