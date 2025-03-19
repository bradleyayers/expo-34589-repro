# reproduction steps

```
npm install
npm run repro
```

then run

```
% curl -X POST -H "Content-Type: application/json" http://localhost:3000/api
A server error has occurred

FUNCTION_INVOCATION_FAILEDcurl -X POST -H "Content-Type: application/json" http://localhost:3000/api
```

and in the logs of the vercel dev server

```
Vercel CLI 41.4.1
> Ready! Available at http://localhost:3000
(node:1906) [DEP0060] DeprecationWarning: The `util._extend` API is deprecated. Please use Object.assign() instead.

/Users/brad/src/expo-34589-repro/node_modules/undici/lib/web/fetch/body.js:211
      throw new TypeError(
            ^
TypeError: Response body object should not be disturbed or locked
    at extractBody (/Users/brad/src/expo-34589-repro/node_modules/undici/lib/web/fetch/body.js:211:13)
    at new Request (/Users/brad/src/expo-34589-repro/node_modules/undici/lib/web/fetch/request.js:516:44)
    at convertRequest (/Users/brad/src/expo-34589-repro/node_modules/@expo/server/src/vendor/vercel.ts:72:10)
    at /Users/brad/src/expo-34589-repro/node_modules/@expo/server/src/vendor/vercel.ts:21:45
    at Server.<anonymous> (file:///Users/brad/src/expo-34589-repro/.vercel/builders/node_modules/@vercel/node/dist/dev-server.mjs:1133:12)
    at processTicksAndRejections (node:internal/process/task_queues:105:5)
```
