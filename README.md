## JSDoc and Better-Docs
# Installation
1. install JSDoc
2. install better-docs
3. in package.json file, add new script:
```json
"script": {
  "docs": "jsdoc -c jsdoc.json"
}
```
4. in `./jsdoc.json` set the template:
```json
"opts": {
  "template": "node_modules/better-docs"
}
```

## Configuring Better-Docs to generate documentation for TypeScript code
Update the `./jsdoc.json` file:
```json
...
"tags": {
    "allowUnknownTags": ["optional"] //or true
},
"plugins": [
    "node_modules/better-docs/typescript"
],
"source": {
    "includePattern": "\\.(jsx|js|ts|tsx)$",
},
...
```
### Excluding file names
**Optional!** If you want to exclude certain file names, for example, your *.test.ts files, add a RegEx pattern to the `./jsdoc.json` file:
In the `./jsdoc.json` file, under `"source"`, add `"excludePattern": "<RegEx pattern goes here>"`
Example:
```json
"excludePattern": "\\.test\\.(jsx|js|ts|tsx)$"
```


## Example `jsdoc.json`
### JSDoc & Better-Docs installation, excludes *.test.ts
```json
{
    "tags": {
        "allowUnknownTags": true
    },
    "source": {
        "includePattern": "\\.(jsx|js|ts|tsx)$",
        "include": ["src"],
        "excludePattern": "\\.test\\.(jsx|js|ts|tsx)$"
    },
    "plugins": [
        "plugins/markdown",
        "node_modules/better-docs/category",
        "node_modules/better-docs/typescript"
    ],
    "opts": {
        "encoding": "utf8",
        "destination": "docs/",
        "recurse": true,
        "verbose": true,
        "template": "node_modules/better-docs"
    },
    "templates": {
        "better-docs": {
            "name": "Name of Documentation", // this appears in the upper right of the output document
            "title": "Flux SDK -"
        }
    }
}
```

To run JSDocs + Better-Docs plug-in, execute the following code:
```sh
./node_modules./bin/jsdoc YOUR-FILE-NAME.ts -t ./node_modules/better-docs
```

./node_modules/.bin/jsdoc example.ts -t ./node_modules/better-docs

## Using the CLI
To build documentation for the entire project, execute the following command:
```zh
npm run docs
```

To build documentation for _one_ file, execute the following command:
```zh
npx jsdoc -c jsdoc.json example.ts
```

Note! If using _only_ JSDoc, your generated documentation files will be in `./out/`. If using JSDoc _and_ Better-Docs, your generated documentation files will be in `./docs/`. You may consider adding either or both folders to your `.gitignore`.
