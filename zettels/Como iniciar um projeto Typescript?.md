120220241500
Status: #idea #Fleeting 
Tags: #Programação #Javascript 
# Como iniciar um projeto Typescript?
Requisitos principais são ter o node.js instalado em sua máquina e uma gerenciador de dependências como yarn, ou pnpm.

### Primeiro passo
```pnpm init ```
Esse comando criar um package.json

### Segundo  passo
```pnpm i -D @types/node @types/express typescript ts-node```
Esse comando instala o typescipt e os types do ts para o expresss.

### Terceiro passo
```pnpm tsc --init```
Esse comando criar um tsconfig.json. Arquivo para configurar o typescript

### Quarto passo 
```
pnpm add -D eslint prettier eslint-config-prettier eslint-plugin-prettier @typescript-eslint/eslint-plugin @typescript-eslint/parser
```
Instalar esllint o prettier e seus plugins para o typescript.
### Quinto passo
```
const path = require('path');

module.exports = {
  parser: '@typescript-eslint/parser',
  extends: [
    'plugin:prettier/recommended',
    'prettier',
    'eslint:recommended'
  ],
  plugins: ['@typescript-eslint'],
  parserOptions: {
    ecmaVersion: 2022,
    sourceType: 'module',
    project: path.resolve(__dirname, './tsconfig.json'),
  },
  env: {
    es6: true,
    node: true,
  },
  rules: {
    'no-var': 'error',
    semi: 'error',
    indent: ['error', 2, { SwitchCase: 1 }],
    'no-multi-spaces': 'error',
    'space-in-parens': 'error',
    'no-multiple-empty-lines': 'error',
    'prefer-const': 'error',
  },
};
```
Criar um arquivo de configuração para o eslint. O nome do arquivo tem que ser .eslintrc.js"

### Sexto passo
```
module.exports = { semi: true, trailingComma: 'all', singleQuote: true, printWidth: 150, tabWidth: 2, };
```
Crie um arquivo de configuração para o prettier chamado .prettierrc.js

### Sétimo passo
```
dist
.eslintrc.js
.prettierrc.js
```
Crie um arquivo .eslintignore

### Oitavo passo
```
"scripts": { "lint": "eslint src/**/*.ts --fix" }
```
Adicione esse script no seu package.json

*
## References
https://blog.tericcabrel.com/set-up-a-nodejs-project-with-typescript-eslint-and-prettier/#:~:text=Configure%20ESLint%20and%20Prettier%201%20Configure%20Prettier%20Create,...%203%20Lint%20and%20format%20our%20code%20
*
