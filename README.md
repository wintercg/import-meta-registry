# `import.meta` Registry

This repository serves as a registry for properties JavaScript runtimes or frameworks may add to the [`import.meta`](https://tc39.es/ecma262/multipage/ecmascript-language-expressions.html#prod-ImportMeta) mechanism defined by TC-39/EcmaScript.

Because `import.meta` is a kind of global namespace, and because implementations are permitted to put whatever they like there, there are potential interoperability and code portability challenges introduced for developers if runtimes and frameworks fail to coordinate their use of the namespace. Therefore, the WinterCG has established this registry to serve as a coordination point.

WinterCG compliant runtimes should never use an `import.meta` property that conflicts in definition with any of the properties included in this registry.

Likewise, implementations should try their best to avoid adding new `import.meta` properties in their implementations, or to this registry, that conflict or overlap with other properties in this registry. Given that such conflict/overlap may not be always avoidable, registrations here should take care to describe when/where/how such properties differ from others they conflict/overlap with.

The process for adding new items to this registry is to open a pull request. Registrations must include all three fields: Name, Description, and a link to a specifying document. The specifying document does not need to be a formal standard -- links to project documentation or even source code is sufficient so long as the semantics of the property are appropriately described. After one week, if there are no objections from WinterCG participants to the registration and at least one sign off on the PR, it can be added.

|        Property       | Description | Link |
| --------------------- | ----------- | ---- |
| `import.meta.url`     | A module scripts base URL | https://html.spec.whatwg.org/multipage/webappapis.html#hostgetimportmetaproperties |
| `import.meta.resolve` | Resolves a module specifier to a URL using the current module's URL as base. | https://html.spec.whatwg.org/multipage/webappapis.html#hostgetimportmetaproperties |
| `import.meta.main`    | Returns whether the current module is the entry point to your program. | https://deno.land/manual@v1.36.4/runtime/import_meta_api#importmeta--api |
| `import.meta.dir`     | Absolute path to the directory containing the current file, e.g. /path/to/project. Equivalent to __dirname in CommonJS modules (and Node.js) | https://bun.sh/docs/api/import-meta |
| `import.meta.file`    | The name of the current file, e.g. index.tsx | https://bun.sh/docs/api/import-meta |
| `import.meta.path`    | Absolute path to the current file, e.g. /path/to/project/index.tx. Equivalent to __filename in CommonJS modules (and Node.js) | https://bun.sh/docs/api/import-meta |

