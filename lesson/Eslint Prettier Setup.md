Next 14 Eslint and Prettier install and setup

1. npx create-next-app@latest next14cicd

2.

```

npm i --save-dev prettier eslint-config-prettier

npm i husky --save-dev lint-staged

npm i --save-dev eslint-plugin-prettier

```

3. .eslintrc.json

```
{
    "extends": ["eslint:recommended", "next", "next/core-web-vitals", "prettier"],
    "plugins": ["prettier],
    "rules": {
        "prettier/prettier": "error"
    }
}
```

4.  create a file .prettierrc and edit

.prettierrc
{
"semi": true,
"singleQuote": true,
"printWidth": 80,
"tabWidth": 2,
"useTabs": false,
"trailingComma": "es5",
"bracketSpacing": true
}

5. .prettierignore

```
.next/

package-lock.json
```
