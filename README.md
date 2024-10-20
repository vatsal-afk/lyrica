# Lyrica: Free Music Search and Playback Chrome Extension

Lyrica is a powerful Chrome extension that allows you to search for any song, play it using the Jamendo API, display live lyrics, and create custom playlists. All of this is available for free, right in your browser!

## Features

- **Song Search**: Easily find any song you want to listen to.
- **Music Playback**: Play songs directly in your browser using the Jamendo API.
- **Live Lyrics**: View synchronized lyrics as the song plays.
- **Playlist Creation**: Create and manage your own custom playlists.

## Technology Stack

This project is built using:

- React
- TypeScript
- Vite

This combination provides a minimal setup to get React working in Vite with HMR (Hot Module Replacement) and some ESLint rules for code quality.

## Getting Started

To get started with development:

1. Clone this repository
2. Run `npm install` to install dependencies
3. Use `npm run dev` to start the development server

## Build

To build the extension for production:

1. Run `npm run build`
2. The built files will be in the `dist` directory

## Loading the Extension in Chrome

1. Open Chrome and navigate to `chrome://extensions`
2. Enable "Developer mode" in the top right corner
3. Click "Load unpacked" and select the `dist` directory from your project

## Contributing

We welcome contributions! Please feel free to submit a Pull Request.

## License

This project is licensed under the [MIT License](LICENSE).

---

For more information on the core technologies used:

- [Vite](https://vitejs.dev/)
- [React](https://reactjs.org/)
- [TypeScript](https://www.typescriptlang.org/)

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

1. Configure the top-level `parserOptions` property like this:

```js
export default tseslint.config({
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

2. Replace `tseslint.configs.recommended` with `tseslint.configs.recommendedTypeChecked` or `tseslint.configs.strictTypeChecked`
3. Optionally add `...tseslint.configs.stylisticTypeChecked`
4. Install [eslint-plugin-react](https://github.com/jsx-eslint/eslint-plugin-react) and update the config:

```js
// eslint.config.js
import react from 'eslint-plugin-react'
export default tseslint.config({
  // Set the react version
  settings: { react: { version: '18.3' } },
  plugins: {
    // Add the react plugin
    react,
  },
  rules: {
    // other rules...
    // Enable its recommended rules
    ...react.configs.recommended.rules,
    ...react.configs['jsx-runtime'].rules,
  },
})
```