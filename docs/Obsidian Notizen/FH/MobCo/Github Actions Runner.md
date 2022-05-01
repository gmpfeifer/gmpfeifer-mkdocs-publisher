---
share: True
description: Github Actions Runner Setup am Raspberry Pi
category: Obsidian Notizen/FH/MobCo
---
# Github Actions Runner

Abgewandelt davon: https://www.raeffs.dev/blog/2021/01-jan/26-github-ci-cd-pipeline/

### Mein main.yml
```yaml title="main.yml" linenums="1"
# This is a basic workflow to help you get started with Actions

name: CI

# Controls when the workflow will run
on:
  # Triggers the workflow on push or pull request events but only for the master branch
  push:
    branches: [ master ]
  pull_request:
    branches: [ master ]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# A workflow run is made up of one or more jobs that can run sequentially or in parallel
jobs:
  # This workflow contains a single job called "build"
  build-and-deploy:
    # The type of runner that the job will run on
    runs-on: self-hosted

    # Steps represent a sequence of tasks that will be executed as part of the job
    steps:
      # Checks-out your repository under $GITHUB_WORKSPACE, so your job can access it
      - uses: actions/checkout@v3
      - name: Restore Node Modules
        uses: actions/cache@v2
        with:
          path: node_modules
          key: ${{ runner.os }}-modules-${{ hashFiles('**/yarn.lock') }}
          restore-keys: |
                        ${{ runner.os }}-modules-
      - name: Install Dependencies
        run: yarn --frozen-lockfile
      - name: Build Site
        run: yarn build
```


Dieser Teil am Ende wurde entfernt, weil der Runner sonst nicht fertig wird:
```yaml
- name: Start Site
        run: yarn start
```


Wenn aber die 11ty Seite gerade "geserved" wird während der Runner das Repo updated, gibt es vorübergehend Fehler: 
![[Bildschirmfoto 2022-04-24 um 01.17.08.png]]
**Scheinbare Lösung:** Symbolischer Link auf das Work-Directory vom Github Runner
```bash
gmpfeifer@raspberrypi:~/11ty $ ln -s ~/actions-runner/_work/eleventy-duo/eleventy-duo duo-blog
```


`ln -s ~/actions-runner/_work/eleventy-duo/eleventy-duo duo-blog`