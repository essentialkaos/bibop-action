<p align="center"><a href="#readme"><img src=".github/images/card.svg"/></a></p>

<br/>

Action for checking scripts with [bibop](https://kaos.sh/bibop).

### Usage

Create file `.github/workflows/bibop.yml`.

Add next code to it:

```yml
name: CI

on:
  push:
    branches: [master, develop]
  pull_request:
    branches: [master]

jobs:
  Bibop:
    name: Bibop
    runs-on: ubuntu-latest

    steps:
      - name: Code checkout
        uses: actions/checkout@v4

      - name: Test recipe with Bibop
        uses: essentialkaos/bibop-action@v1
        with:
          recipe: .bibop/myapp.recipe

```

### Options

| Option | Description | Value |
|--------|-------------|--------|
| `recipe` | Path to Bibop recipe | _Path_ |
| `version` | Bibop version | _Version in semver notation_ |
| `dry-run` | Just parse and validate recipe | _Boolean_ |
| `format` | Output format | `tap`<br/>`json`<br/>`xml` |
| `working-dir` | Path to working directory | _Path_ |
| `path` | Path to directory with binaries | _Path_ |
| `tag` | Command tag | _String_ |

### License

[Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)

<p align="center"><a href="https://essentialkaos.com"><img src="https://gh.kaos.st/ekgh.svg"/></a></p>
