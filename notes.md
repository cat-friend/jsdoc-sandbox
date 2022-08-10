# A place to test out JSDoc
Internal example:  https://giddyinc.github.io/spresso-sdk-tracking-web/SpressoSdk.html#trackCreateOrder
`jsdoc-to-markdown` example: https://github.com/75lb/handbrake-js

## Usage notes
### local install
Since jsdoc was not installed globally, the command to run jsdoc is
```
./node_modules/.bin/jsdoc yourJavaScriptFile.js
```
where `yourJavaScriptFile.js` is the file that JSDoc will generate documentation from.

For help, run
```./node_modules/.bin/jsdoc --help```

### TypeScript
List of supported constructs:  https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html

## Approach
### JavaScript
1. make some sample code (c & p from open source projects)
2. use 5-10 different constructs
3. generate website

### TypeScript
1. make some sample code (use code from learning TS repo))
2. use 5-10 different constructs
3. generate website
   
### `jsdoc-to-markdown`
1. Generate md from previous JS and TS JSDoc documentation websites.
2. Evaluate.

## Pros
* `jsdoc-to-markdown` plugin can generate to md files, like READMEs.

## Cons
