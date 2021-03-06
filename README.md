rollup-plugin-alias-module-specifiers
===

Rollup plugin to alias module specifiers (named specifiers and paths).

# install
```
$ npm install -D rollup-plugin-alias-module-specifiers
```

# example

```js
import tool from 'utility/tool.js';
```

turns into

```js
import tool from './third-party/some-utils/tool.js';
```

with a rollup config of

```js
import aliasModuleSpecifiers from 'rollup-plugin-alias-module-specifiers';

export default {
    entry: 'index.js',
    plugins: [
        aliasModuleSpecifiers({
            'utility/': './third-party/some-util/'
        })
    ]
};
```

The options passed to `aliasModuleSpecifiers` are used to match the specifier by key and replace it with the given value. Keys must match from the start of the specifier and only the matched part is replaced.
