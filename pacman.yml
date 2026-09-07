name: Generate Pacman contribution graph

on:
  schedule:
    - cron: "0 0 * * *"   # se ejecuta una vez al día
  workflow_dispatch: {}    # te permite correrlo manualmente desde la pestaña "Actions"
  push:
    branches:
      - main               # cambia esto si tu rama principal se llama distinto

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    steps:
      - name: Generate pacman contribution graph
        uses: Platane/snk@v3
        id: pacman
        with:
          github_user_name: CatalinaP19
          outputs: |
            pacman-contribution-graph.svg
            pacman-contribution-graph-dark.svg?palette=github-dark

      - name: Push graph to pacman-output branch
        uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: pacman-output
          build_dir: .
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
