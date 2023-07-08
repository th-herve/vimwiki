# Javascript npm

Npm is a package manager for javascript.

## Installing packages

The `package.json` file can specify the version to install.
Otherwise, the latest version is installed.

### Unscoped package

```bash
npm install package-name
```
### Scoped package

```bash
npm install @scope/package-name
```

## Test package installation

```bash
ls node_modules | grep package-name
```
