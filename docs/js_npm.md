# Javascript npm

Npm is a package manager for javascript.

## Installing packages

Use `npm install`, use flage `--save` or `--save-dev` to add
it to  the `package.json`

```bash
# unscoped package
npm install package-name --save-dev

# scoped package
npm install @scope/package-name --save
```

The `package.json` file can specify the version to install.
Otherwise, the latest version is installed.

Test the installation with:

> ls node_modules | grep package-name
 
## package.json

Add a `package.json` file in a project to manage and install
its dependency.

```json
{
  "name": "my-awesome-package",
  "version": "1.0.0",
  "author": "Your Name <email@example.com>"
}
```
You can create a default package.json file using information
from the current directory with:

> npm init --yes
