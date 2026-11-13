# React + TypeScript + Vite

## Tic Nova authentication and scoring

Tic Nova now uses a MySQL-backed API for accounts and scores. Create the database and
users table by running [`database/schema.sql`](./database/schema.sql) in MySQL.

1. Copy `.env.example` to `.env` and set the MySQL credentials and a long `JWT_SECRET`.
2. Start the API with `npm run server`.
3. In another terminal, start the Vite app with `npm run dev`.

The app awards one point only when the logged-in human player (`X`) wins a
player-versus-AI game. Player-versus-player games never update points. Scores are
stored per account in the `users.points` column and are shown in the start screen
and game header.

This template provides a minimal setup to get React working in Vite with HMR and some Oxlint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Oxc](https://oxc.rs)
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/)

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the Oxlint configuration

If you are developing a production application, we recommend enabling type-aware lint rules by installing `oxlint-tsgolint` and editing `.oxlintrc.json`:

```json
{
  "$schema": "./node_modules/oxlint/configuration_schema.json",
  "plugins": ["react", "typescript", "oxc"],
  "options": {
    "typeAware": true
  },
  "rules": {
    "react/rules-of-hooks": "error",
    "react/only-export-components": ["warn", { "allowConstantExport": true }]
  }
}
```

See the [Oxlint rules documentation](https://oxc.rs/docs/guide/usage/linter/rules) for the full list of rules and categories.
