# 🧩 Libconfig

```ascii
┏┓━━━┏┓━━━━━━━━━━━━━━━┏━┓━━━━━━
┃┃━━━┃┃━━━━━━━━━━━━━━━┃┏┛━━━━━━
┃┃━┏┓┃┗━┓┏━━┓┏━━┓┏━┓━┏┛┗┓┏┓┏━━┓
┃┃━┣┫┃┏┓┃┃┏━┛┃┏┓┃┃┏┓┓┗┓┏┛┣┫┃┏┓┃
┃┗┓┃┃┃┗┛┃┃┗━┓┃┗┛┃┃┃┃┃━┃┃━┃┃┃┗┛┃
┗━┛┗┛┗━━┛┗━━┛┗━━┛┗┛┗┛━┗┛━┗┛┗━┓┃
━━━━━━━━━━━━━━━━━━━━━━━━━━━┏━┛┃
━━━━━━━━━━━━━━━━━━━━━━━━━━━┗━━┛
```

> A centralized collection of reusable configuration presets for tools across the JavaScript ecosystem.<br>
> Currently includes support for Biome and TypeScript.

## 📦 Packages

### 1. @libconfig/biome

This package exports a baseline Biome configuration file. You can extend it in your root `biome.json` so that all Biome-powered tooling (formatting, linting, etc.) uses a consistent set of rules.

- **Installation** (dev dependency)
  ```bash
  [p]npm i -D @libconfig/biome
  ```
  or
  ```bash
  yarn add --dev @libconfig/biome
  ```

- **Usage**
  Create (or update) your `biome.json`:
  ```jsonc
  {
    "extends": ["@libconfig/biome"]
  }
  ```
  Biome (formerly Deno fmt/lint successor) will automatically pick up this config.

### 2. @libconfig/typescript

This package offers a variety of `tsconfig` presets for different TypeScript workflows—library builds, Vite apps, Solid.js with Vite, etc. Simply extend one of the provided JSON files in your project’s `tsconfig.json`.

- **Installation** (dev dependency)
  ```bash
  [p]npm i -D @libconfig/typescript
  ```
  or
  ```bash
  yarn add --dev @libconfig/typescript
  ```

- **Available Presets**
  Under `@libconfig/typescript`, you’ll find the following configuration files:

  ```
  tsconfig.lib.json            // Recommended for building TypeScript libraries
  tsconfig.vite.json           // Base TS config for a Vite project
  tsconfig.vite-solid.json     // Base TS config for a Vite + Solid.js project
  tsconfig.json                // (Alias) Default tsconfig (can be customized further)
  ```

- **Usage Examples**

  1. **Basic Vite Project**
     In your project’s root:
     ```jsonc
     // tsconfig.json
     {
       "extends": "@libconfig/typescript/tsconfig.vite.json",
       "compilerOptions": {
         // you can override or add more options here
       }
     }
     ```

  2. **Vite + Solid.js**
     ```jsonc
     // tsconfig.json
     {
       "extends": "@libconfig/typescript/tsconfig.vite-solid.json",
       "compilerOptions": {
         // additional overrides as needed
       }
     }
     ```

  3. **Library (Node/Browser) Build**
     ```jsonc
     // tsconfig.json
     {
       "extends": "@libconfig/typescript/tsconfig.lib.json",
       "compilerOptions": {
         // for example, "declaration": true, "outDir": "./dist"
       }
     }
     ```

---

## 📜 Contributing

1. **Fork** this repository.
2. Create a new branch:
   ```bash
   git checkout -b feat/your-feature
   ```
3. Make your changes in the appropriate package folder (`packages/biome` or `packages/typescript`).
4. Add or update tests (if applicable).
5. Commit & push:
   ```bash
   git commit -m "feat: add XYZ support to tsconfig"
   git push origin feat/your-feature
   ```
6. Open a Pull Request against `main`.
   Please describe your change, the motivation, and any migration steps if necessary.

---

## ⚖️ License

This project is licensed under the [MIT License](LICENSE).

---

## 🔗 Related Links

- **Biome** documentation: <https://docs.biomejs.dev>
- **TypeScript** handbook: <https://www.typescriptlang.org/docs/>

---

> _Maintained with ❤️ by the libconfig-dev team._
> If you find any issues or have suggestions, please open an issue on GitHub.
