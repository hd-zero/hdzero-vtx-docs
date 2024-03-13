# HDZero Docs

## Viewing Documentation

Open up [https://hd-zero.github.io/hdzero-vtx-docs/latest](https://hd-zero.github.io/hdzero-vtx-docs/latest) in your browser.

## For Dev

### Install mkdocs and mike

```
pip installer mkdocs mike
```

### Release version

```
mike deploy --push --update-aliases x.y.z latest
```

```
mike set-default --push latest
```

### Update a version

```
mike deploy x.y.z --push
```

### Delete a version

```
mike delete x.y.z --push
```

### Browse locally

```
mike serve
```
