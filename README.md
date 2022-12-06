# Corepack Yarn Project

- toggle yarn functionality (it's managed within a subdirectory of .nvm with corepack)

```shell
corepack disable
corepack enable yarn
```

- in order to first get it going, you may need to run corepack prepare yarn@stable --activate
  - to upgrade to the latest stable yarn version yarn set version stable

```shell
corepack prepare yarn@stable --activate
yarn set version stable
```

- create a new yarn project and add a package just like normal (no need for calls to corepack)

```shell
yarn init -2
yarn add axios
```

- note: yarn is now the interpreter for the project (in order to run your index.js node server file, for instance, prefix the command with yarn, or put the call to node in scripts)

```shell
yarn node index.js
```

```json
{
  "type": "module",
  "scripts": {
    "start": "node index.js"
  }
}
```

- .yarnrc.yml defines how the modules are resolved; you have 3 options: local cache (default in .yarn/cache), global cache (links to your user's .yarn/cache folder; used for local dev not for zero-install PnP) and node modules (for compatibility)

```yml
yarnPath: .yarn/releases/yarn-3.3.0.cjs
# enableGlobalCache: true
# nodeLinker: node-modules
```
