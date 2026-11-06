# Contributing

Thanks for taking a look! This is a small fan plugin; issues and pull requests are both welcome.

## Reporting a bug

Open an issue with the **Bug report** template and include:

- your operating system and DeepSeek Harness version;
- whether the account is signed in (the widget shows a sign-in hint when it is not);
- what you expected, what happened, and a screenshot if the widget is visible;
- any console errors mentioning `[whale-companion]`.

Please do not paste tokens, account IDs or full balance screenshots with personal data.

## Suggesting a feature

Use the **Feature request** template. Good candidates: new expressions, layout options, accessibility fixes, translations.

## Pull requests

1. Keep the plugin dependency-free and build-free: plain JavaScript, no new npm packages, no bundler.
2. Import only `react` from the module table. Do not import Harness Client packages such as `@deepseek-ai/dsh-client-ui-primitives`; copy the small piece you need instead.
3. Style with the theme tokens listed by the Cordis `Theme` inspect provider (`--dsw-alias-*`). Literal colors are only acceptable inside artwork.
4. Render through slots. Do not append nodes to `document.body`, do not query another plugin's DOM, and clean up every timer/listener in `ctx.effect`.
5. Keep visible text in the locale dictionaries (`client.js` → `DICTS`) for both `en` and `zh`.
6. Run the syntax check before opening the PR:

   ```powershell
   node --check client.js
   node -e "JSON.parse(require('fs').readFileSync('package.json','utf8'))"
   ```

7. Do not commit `dist/` archives or the `.git` directory into the package.

### Adding an expression

- Square images are eligible as-is; non-square images are eligible only when their longer-to-shorter ratio is ≤ 1.2 and they are center-cropped.
- Use images from the [DeepSeek-chan meme pack](https://github.com/the-beating-light-of-the-nail/deepseek-chan-meme-pack) so the [NOTICE](NOTICE.md) stays accurate, or bring art you own or that is licensed for redistribution.
- Resize to 224×224, compress to WebP (quality ~80), and add the entry to `ARTS` in `client.js`; keep the array ordered by preview id.
- Mention the preview id in the PR so the notice list can be updated.

### Testing locally

1. Install the bundle from your working copy (Plugins → Add plugin → absolute path).
2. After editing `client.js`, remove and reinstall the bundle, then refresh the page: client bundles are cached per loader row.
3. Check light and dark themes, a narrow window, and the signed-out state.

## Commit messages

Short imperative subjects are enough: `Add 077 expression`, `Fix stale balance dimming`, `Translate bonus label`.
