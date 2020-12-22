# docker-prebuild-alpine

A Docker image to prebuild Node.js native addons for Alpine Linux

## Usage

With GitHub Actions:

1. Create a workflow file (say, `.github/workflows/prebuild.yml`)

```yaml
name: Prebuild Package
on:
  push:
    tags:
      - '*'
jobs:
  prebuild:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: actions/setup-node@v2.1.3
        with:
          node-version: 14
      - run: npm ci
      - run: npm run build
      - run: |
          docker run --rm -v $(pwd):/usr/src/app wildwildangel/docker-prebuild-alpine npx prebuild -r napi -u ${{ secrets.GITHUB_TOKEN }}
          docker run --rm -v $(pwd):/usr/src/app wildwildangel/docker-prebuild-devtoolset-7-toolchain-centos7 npx prebuild -r napi -u ${{ secrets.GITHUB_TOKEN }}
```

2. Update your `package.json`, add something like this into `scripts`:

```
"install": "prebuild-install || node-gyp rebuild"
```

The actual command may differ, please consult with [prebuild-install documentation](https://www.npmjs.com/package/prebuild-install) for details.

3. Add `prebuild-install` to `dependencies`, and `prebuild` to `devDependencies`:

```bash
npm i prebuild-install
npm i -D prebuild
```
