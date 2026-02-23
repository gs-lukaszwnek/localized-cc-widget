# Localized Community Widget

A multi-language widget for Gainsight Customer Communities that automatically detects the user's language and renders localized content. Built with React, Vite, and the Widget SDK.

## Supported Languages

- English (en)
- Español (es)
- Français (fr)
- Deutsch (de)
- Português (pt)

## How It Works

The platform sets `<html lang="de">` based on the user's language preference. The widget reads this attribute at render time and picks the matching translation set. If the detected language isn't supported, it falls back to English.

## Development

```bash
yarn install
yarn dev
```

Change the `lang` attribute in `index.html` to test different languages locally.

## Build

```bash
yarn build
```

Output lands in `dist/` — `widget.js`, `widget.css`, and `index.html` that references them.

## Project Structure

```
src/
├── main.tsx          # Widget SDK entry point (exports init)
├── App.tsx           # React component
├── translations.ts   # Translation strings + locale detection
├── types.ts          # WidgetSDK and Locale types
├── widget.css        # Styles
├── dev.tsx           # Local dev harness with mock SDK
└── global.d.ts       # Vite type reference
```

## Adding a Language

1. Add the locale code to the `Locale` union in `src/types.ts`
2. Add the translation strings to `TRANSLATIONS` in `src/translations.ts`

## Publishing

Place `widget.json` and the `dist/` folder in a widget repository connected to your community. The widget type is derived from the directory name.
