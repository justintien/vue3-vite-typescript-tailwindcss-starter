# 🛠️ 專案初始化流程 Project Setup Guide

> 本文件說明如何建立並初始化本專案，包含開發環境安裝、專案建置、風格工具設定等。

---

## 📦 建立 Vue 3 專案

使用官方 CLI 工具建立專案：

```bash
npm init vue@latest
```

建議勾選以下功能：

- ✅ TypeScript
- ✅ Router（單頁應用程式開發）
- ✅ Pinia（狀態管理）
- ✅ Vitest（單元測試）
- ✅ 端對端測試
- ✅ ESLint（錯誤預防）
- ✅ Prettier（程式碼格式化）

選擇一個端對端測試框架：

- ✅ Playwright

是否引入 Oxlint 以加快檢測？（試驗性功能）

- ✅ No

---

## 📁 進入專案資料夾並安裝套件

```bash
cd <your-project-name>
npm install
```

---

## 💅 設定 ESLint 與 Prettier

### `eslint.config.ts`

預設配置其實已經非常 合理、精簡、可維護，只要你不特別要加強 lint 效果，完全可以照用，不需要改。但如果你有 下面這些需求，可以在這之上調整：

```js
// ⬇️ chatgpt 建議的額外補強規則（可選）
{
    files: ['**/*.{ts,mts,tsx,vue}'],
    rules: {
        'vue/multi-word-component-names': 'off',
        '@typescript-eslint/no-unused-vars': ['warn'],
        '@typescript-eslint/no-explicit-any': 'off',
        'prettier/prettier': ['error'],
    },
}
```

### `.prettierrc.json`

```json
{
  "semi": false,
  "singleQuote": true,
  "printWidth": 100,
  "tabWidth": 2,
  "trailingComma": "es5",
  "bracketSpacing": true,
  "arrowParens": "avoid",
  "endOfLine": "auto"
}
```

---

## 🌈 設定 Tailwind CSS

安裝 TailwindCSS (Using PostCSS)

```bash
npm install tailwindcss @tailwindcss/postcss postcss
```

Add Tailwind to your PostCSS configuration

- `postcss.config.mjs`

```js
export default {
  plugins: {
    '@tailwindcss/postcss': {},
  },
}
```

設定 `src/assets/main.css`

```css
@import 'tailwindcss';
```

---

## 🚀 開始開發

```bash
npm run dev
```

## 設定 git

```bash
git init && git add -A && git commit -m "initial commit"
```

---

## 🔧 常用指令

| 指令            | 說明                 |
| --------------- | -------------------- |
| `npm run dev`   | 啟動本地開發伺服器   |
| `npm run lint`  | 執行 ESLint 檢查     |
| `npm run build` | 建立專案             |
| `npm run test`  | 執行測試（如有設定） |

---

## 📁 推薦資料夾結構（可參考）

```
src/
  assets/
  components/
  layouts/
  pages/
  router/
  store/
  views/
```
