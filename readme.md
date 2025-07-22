# HDZero Docs

## Viewing Documentation

Open up [https://hd-zero.github.io/hdzero-vtx-docs/latest](https://hd-zero.github.io/hdzero-vtx-docs/latest) in your browser.

## For Dev

### Install mkdocs and mike

```
pip install mkdocs mike
```

You may need to add mike path to env path. To check the installation location with:

```
pip show mike
```

### Update a version

```
mike deploy x.y.z --push --branch gh-pages
```

### Release version as latest

```
mike alias x.y.z latest --push --update-aliases --branch gh-pages
```

### Delete a version

```
mike delete x.y.z --push --branch gh-pages
```

### Browse locally

```
mike serve
```

### Show verion list

```
mike list
```
