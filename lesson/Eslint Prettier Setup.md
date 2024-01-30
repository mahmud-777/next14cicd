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

6. edit package.json file

```
{
  "name": "next14cicd",
  "version": "0.1.0",
  "private": true,
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start",
    "lint": "eslint src --ext ts,tsx,js,jsx --report-unused-disable-directives --max-warnings 0",
    "lint-fix": "eslint src --ext js, jsx,ts,tsx --fix",
    "format": "prettier --write 'src/**/*.{js,jsx,ts,tsx,css,html}'"
  },
  "dependencies": {
    "next": "14.1.0",
    "react": "^18",
    "react-dom": "^18"
  },
  "devDependencies": {
    "@types/node": "^20",
    "@types/react": "^18",
    "@types/react-dom": "^18",
    "autoprefixer": "^10.0.1",
    "eslint": "^8",
    "eslint-config-next": "14.1.0",
    "eslint-config-prettier": "^9.1.0",
    "eslint-plugin-prettier": "^5.1.3",
    "husky": "^9.0.7",
    "lint-staged": "^15.2.0",
    "postcss": "^8",
    "prettier": "^3.2.4",
    "tailwindcss": "^3.3.0",
    "typescript": "^5"
  },
  "husky": {
    "hooks": {
      "pre-commit": "lint-staged",
      "pre-push": "npm run lint && npm run format"
    }
  },
  "lint-staged": {
    "src/**/*.{ts,tsx,js,jsx}": [
      "npm run lint",
      "npm run format"
    ]
  }
}

```

7. npx husky install
