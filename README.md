<p align="center"><a href="#readme"><img src="https://gh.kaos.st/bibop-action.svg"/></a></p>

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
        uses: actions/checkout@v2

      - name: Run test recipes with Bibop
        uses: essentialkaos/bibop-action@v1
        with:
          recipe: .bibop/myapp.recipe
          dry-run: true
          format: json
          working-dir: src/app
          path: src/app/bin
          tag: simple

```

### License

[Apache License, Version 2.0](https://www.apache.org/licenses/LICENSE-2.0)

<p align="center"><a href="https://essentialkaos.com"><img src="https://gh.kaos.st/ekgh.svg"/></a></p>
