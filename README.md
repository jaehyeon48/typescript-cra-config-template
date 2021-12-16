# `ESLint`, `Prettier` and `TypeScript` config file templates for TypeScript CRA project

## npm dependencies

- @typescript-eslint/parser
- @typescript-eslint/eslint-plugin
- eslint-config-airbnb
- eslint-config-airbnb-typescript
- prettier
- eslint-config-prettier
- eslint-plugin-prettier
- eslint-plugin-react
- eslint-plugin-react-hooks
- eslint-plugin-jsx-a11y
- eslint-plugin-import
- eslint-plugin-jest
- eslint-plugin-jest-dom
- eslint-plugin-testing-library

```sh
npm i -D @typescript-eslint/parser @typescript-eslint/eslint-plugin eslint-config-airbnb eslint-config-airbnb-typescript prettier eslint-config-prettier eslint-plugin-prettier eslint-plugin-react eslint-plugin-react-hooks eslint-plugin-jsx-a11y eslint-plugin-import eslint-plugin-jest eslint-plugin-jest-dom eslint-plugin-testing-library
```

## `eslintrc.json`

```json
{
	"extends": [
		"eslint:recommended",
		"plugin:@typescript-eslint/recommended",
		"airbnb",
		"airbnb/hooks",
		"airbnb-typescript",
		"plugin:jest/recommended",
		"plugin:jest-dom/recommended",
		"plugin:testing-library/react",
		"plugin:prettier/recommended"
	],
	"plugins": ["react", "@typescript-eslint", "jest", "jest-dom", "prettier"],
	"env": {
		"browser": true,
		"es2021": true,
		"jest": true
	},
	"parser": "@typescript-eslint/parser",
	"parserOptions": {
		"ecmaFeatures": {
			"jsx": true
		},
		"ecmaVersion": 12,
		"sourceType": "module",
		"project": "./tsconfig.json"
	},
	"rules": {
		"react/react-in-jsx-scope": "off"
	}
}
```

## `.prettierrc.json`

```json
{
	"singleQuote": true,
	"semi": true,
	"useTabs": true,
	"tabWidth": 2,
	"trailingComma": "none",
	"printWidth": 100,
	"arrowParens": "avoid",
	"endOfLine": "auto",
	"bracketSameLine": true
}
```

## `tsconfig.json`

```json
{
	"compilerOptions": {
		"target": "es6",
		"lib": ["dom", "dom.iterable", "esnext"],
		"allowJs": true,
		"skipLibCheck": true,
		"esModuleInterop": true,
		"allowSyntheticDefaultImports": true,
		"strict": true,
		"forceConsistentCasingInFileNames": true,
		"noFallthroughCasesInSwitch": true,
		"module": "esnext",
		"moduleResolution": "node",
		"resolveJsonModule": true,
		"isolatedModules": true,
		"noEmit": true,
		"jsx": "react-jsx"
	},
	"include": ["src"],
	"exclude": ["node_modules"]
}
```

## etc

```json
// package.json

"scripts": {
	// ...
	"format": "prettier --check ./src",
	"format:fix": "prettier --write ./src",
	"lint": "eslint ./src",
	"lint:fix": "eslint --fix ./src"
}
```
