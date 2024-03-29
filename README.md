# Reproduction steps

```bash
npm install

npm run generate

npm run lint
```

On windows eslint will fail with the following error when attempting to import "./.nuxt/eslint.config.mjs":
```
ESLint: 8.57.0

Error [ERR_UNSUPPORTED_ESM_URL_SCHEME]: Only URLs with a scheme in: file, data, and node are supported by the default ESM loader. On Windows, absolute paths must be valid file:// URLs. Received protocol 'e:'
    at throwIfUnsupportedURLScheme (node:internal/modules/esm/load:239:11)
    at defaultLoad (node:internal/modules/esm/load:130:3)
    at ModuleLoader.load (node:internal/modules/esm/loader:409:13)
    at ModuleLoader.moduleProvider (node:internal/modules/esm/loader:291:56)
    at new ModuleJob (node:internal/modules/esm/module_job:65:26)
    at #createModuleJob (node:internal/modules/esm/loader:303:17)
    at ModuleLoader.getJobFromResolveResult (node:internal/modules/esm/loader:260:34)
    at ModuleLoader.getModuleJob (node:internal/modules/esm/loader:241:17)
    at async ModuleWrap.<anonymous> (node:internal/modules/esm/module_job:85:21)
```

Absolute path imports just need to be prefixed with "file://"