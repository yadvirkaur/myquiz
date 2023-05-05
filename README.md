Documentation for CRA with Eslint using Airbnb and Prettier

CRA (Create React App) is a great way to start building a new React project quickly. Eslint is a popular tool for linting JavaScript code, and Airbnb provides a widely-used set of style guidelines. Prettier is a code formatter that can be integrated with Eslint. Here are the steps to configure your CRA project with Eslint using Airbnb and Prettier:

1. Install peer dependencies
   Use the following command to install the peer dependencies required for Airbnb configuration:

```
npx install-peerdeps --dev eslint-config-airbnb
```

2. Initialize Eslint
   Use the following command to initialize Eslint configuration:

```
eslint --init
```

Answer the questions as per your requirement. You can choose "React" as a framework while configuring.

3. Install Prettier
   Use the following command to install Prettier:

```
npm install prettier --save-dev
```

4. Install eslint-config-prettier
   Use the following command to install eslint-config-prettier:

```
npm install eslint-config-prettier --save-dev
```

5. Install eslint-plugin-prettier
   Use the following command to install eslint-plugin-prettier:

```
npm install eslint-plugin-prettier --save-dev
```

6. Update the .eslintrc.json file
   Update the .eslintrc.json file in your project root directory with the following content:

```
{
  "env": {
    "browser": true,
    "es6": true,
    "node": true
  },
  "extends": [
    "react-app",
    "react-app/jest",
    "plugin:react/recommended",
    "airbnb",
    "plugin:jsx-a11y/recommended",
    "plugin:prettier/recommended"
  ],
  "rules": {
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }],
    "react/prop-types": "error",
    "prettier/prettier": [
      "error",
      {
        "semi": false,
        "singleQuote": true,
        "trailingComma": "none"
      }
    ]
  }
}
```

This configuration extends the "airbnb" rules and also includes the "prettier" plugin for formatting.

7. Run Eslint and Prettier
   Use the following commands to run Eslint and Prettier:

```
npx prettier --write .
eslint .
```

This command will format all files in the project using Prettier and then run Eslint to check for any linting errors.

8. Merge Prettier configurations
   If you want to merge and override any config set with .prettierrc files, use the following option in your .eslintrc.json file:

```
{
  "prettier/prettier": [
    "error",
    {
      "singleQuote": true,
      "parser": "flow"
    }
  ]
}
```

9. Temporarily disable prettier rule
   If you're fixing large amounts of previously unformatted code, consider temporarily disabling the prettier/prettier rule and running Eslint and Prettier separately with the following commands:

```
eslint --fix .
npx prettier --write .
```

That's it! Your CRA project is now configured with Eslint using Airbnb and Prettier.
