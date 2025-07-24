```
pnpm install
pnpm run preview
```

Then observe error:

```
service core:user:my-react-app: Uncaught Error: No such module "dist/server/chunks/chunk-DgBTj3OE.js".
  imported from "dist/server/entries/pages_about.mjs"

MiniflareCoreError [ERR_RUNTIME_FAILURE]: The Workers runtime failed to start. There is likely additional logging output above.
    at _Miniflare.#assembleAndUpdateConfig (/home/rom/tmp/repro_vite-plugin-cloudflare_no-such-module/node_modules/.pnpm/miniflare@https+++pkg.pr.new+cloudflare+workers-sdk+miniflare@31c94b7/node_modules/miniflare/src/index.ts:2028:10)
    at processTicksAndRejections (node:internal/process/task_queues:105:5)
    at Mutex.runWith (/home/rom/tmp/repro_vite-plugin-cloudflare_no-such-module/node_modules/.pnpm/miniflare@https+++pkg.pr.new+cloudflare+workers-sdk+miniflare@31c94b7/node_modules/miniflare/src/workers/shared/sync.ts:66:45)
```

The file `dist/server/chunks/chunk-DgBTj3OE.js` does exist and the import path inside `dist/server/entries/pages_about.mjs` is correct.
