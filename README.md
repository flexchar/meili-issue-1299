# meili-issue-1299

This is a little reproducible to illustrate an issue with `crypto` when using Meilisearch Client and Algolia's Widget library for Instant Search within VueJS.

Ref: https://github.com/meilisearch/meilisearch-js-plugins/issues/1299

```bash
git clone https://github.com/flexchar/meili-issue-1299
cd meili-issue-1299
npm install
npm run build
npm run preview

```

See `Uncaught TypeError: Failed to resolve module specifier "crypto". Relative references must start with either "/", "./", or "../".` error in the browser console.
