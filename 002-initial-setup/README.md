# Initial Setup

Initial steps to create our first typescript project

## Install typescript
To install globally:
```sh
$ npm i typescript -g
# or, using Yarn:
$ yarn global add typescript
```
To install locally:
```sh
$ npm i typescript --save-dev
# or, using Yarn:
$ yarn add typescript --dev
```
# Initialize our project
To initialize a TypeScript project, simply use the --init flag:
```sh
$ tsc --init
```
or if you have installed it locally you can run:
```sh
$ ./node_modules/.bin/tsc --init
# or if you have npx:
$ npx tslint --init
```

After this we will see a tsconfig.json with default values. Similar to:

```json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "strict": true
  }
}
```

Let's add a couple more: ```outDir``` and ```sourceMap```
```json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "strict": true,
    "outDir": "dist",
    "sourceMap": true
  }
}
```

### Create our first file index.ts
```ts
const world = 'm3';
export function hello(word: string = world): string {
  return `Hello ${world}! `;
}
```
Now if we want to compile it let's run tsc:
```sh
$ tsc
# or locally
$ npx tsc
```

If we want to watch
```sh
$ tsc -w
# or, for local tsc:
$ npx tsc -w
```

### Let's add linter
```sh
# global:
$ yarn global add tslint

# or local:
$ yarn add tslint --dev
```
With tslint install let's initialize it:
```sh
# if using global tslint:
$ tslint --init

# if using local tslint:
$ npx tslint --init
```
This will add a tslint.json file to your project with the following default configuration:

```json
{
  "defaultSeverity": "error",
  "extends": [
    "tslint:recommended"
  ],
  "jsRules": {},
  "rules": {},
  "rulesDirectory": []
}
```
We can add all the rules we want but for this project we'll be using airbnb's config:
```sh
$ yarn add tslint-config-airbnb --dev
```
Our ```tslint.json``` would be:
```json
{
    "defaultSeverity": "error",
    "extends": "tslint-config-airbnb",
    "jsRules": {},
    "rules": {
        "eofline": false
    },
    "rulesDirectory": []
}
```



