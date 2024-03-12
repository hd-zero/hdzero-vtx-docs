# HDZero Docs

## Viewing Documentation

Open up [https://hd-zero.github.io/hdzero-vtx-docs/latest](https://hd-zero.github.io/hdzero-vtx-docs/latest) in your browser.

## For Dev

### Install mkdocs and mike

```
pip installer mkdocs mike
```

### Set default

```
mike deploy --push --update-aliases dev latest
```

```
mike set-default --push latest
```

### Release/update a version and deploy

```
mike deploy x.y.z --push
```

### Delete a version and deploy

```
mike deploy x.y.z --push
```
