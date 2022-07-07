<template>
  <pre>
    <code>module.exports = {
    // 현재 eslintrc 파일을 기준으로 ESLint 규칙을 적용
    root: true,
    // 추가적인 규칙들을 적용
    extends: [
        "eslint:recommended",
        "plugin:vue/essential",
        "prettier",
        "plugin:prettier/recommended",
    ],
    // 코드 정리 플러그인 추가
    plugins: ["prettier"],
    // 사용자 편의 규칙 추가
    rules: {
        "prettier/prettier": [
            "error",
            // 아래 규칙들은 개인 선호에 따라 prettier 문법 적용
            // https://prettier.io/docs/en/options.html
            {
                singleQuote: false,
                semi: true,
                useTabs: false,
                tabWidth: 4,
                trailingComma: "all",
                printWidth: 200,
                bracketSpacing: true,
                arrowParens: "avoid",
            },
        ],
        "no-console": process.env.NODE_ENV === "production" ? "error" : "off",
    },
    "parser": "babel-eslint",
    "parserOptions": {
        "ecmaVersion": 2019,
        "ecmaFeatures": {
            "jsx": true,
            "modules": true,
        },
        "sourceType": module,
        "allowImportExportEverywhere": true,
    },
    "env": {
        "es6": true,
    }
};
// .prettierrc.js
module.exports = {
  printWidth: 120, // [Default: 80] Specify the line length that the printer will wrap on.
  tabWidth: 2, // [Default: 2] Specify the number of spaces per indentation-level.
  useTabs: false, // [Default: false] Indent lines with tabs instead of spaces.
  semi: true, // [Default: true] Print semicolons at the ends of statements.
  singleQuote: true, // [Default: false] Use single quotes instead of double quotes.
  quoteProps: 'as-needed', // [Default: 'as-needed'] Change when properties in objects are quoted.
  jsxSingleQuote: false, // [Default: false] Use single quotes instead of double quotes in JSX.
  trailingComma: 'es5', // [Default: 'es5'] Print trailing commas wherever possible in multi-line comma-separated syntactic structures.
  bracketSpacing: true, // [Default: true] Print spaces between brackets in object literals.
  bracketSameLine: false, // [Default: false] Put the > of a multi-line HTML (HTML, JSX, Vue, Angular) element at the end of the last line instead of being alone on the next line (does not apply to self closing elements).
  arrowParens: 'always', // [Default: 'always'] Include parentheses around a sole arrow function parameter.
};
// package.jcon
"eslintConfig": {
    "root": true,
    "env": {
      "node": true
    },
    "extends": [
      "plugin:vue/vue3-essential",
      "eslint:recommended"
    ],
    "parserOptions": {
      "parser": "babel-eslint"
    },
    "rules": {}
  },
  "browserslist": [
    "> 1%",
    "last 2 versions",
    "not dead"
  ]
// vue.config.js
module.exports = {
  lintOnSave: false,
  devServer: {
    port: process.env.VUE_APP_SERVER_PORT,
    https: false,
    overlay: false,
    disableHostCheck: true,
  },
  configureWebpack: {
    resolve: {
      alias: {
        '@': path.resolve(__dirname, 'src/'),
        '@@': path.resolve(__dirname, 'src/app/'),
      },
    },
    devtool: 'source-map',
  },
  css: {
    extract: true,
    sourceMap: true,
  },
  runtimeCompiler: true,
};</code>
  </pre>
</template>

<script>
export default {

}
</script>

<style>

</style>