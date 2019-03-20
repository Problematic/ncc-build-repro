https://zeit.co/problematic/ncc-build-repro/deployment/5uaokkbrh/logs

```shell
[15:21:56] ~/dev/projects/ncc-build-repro (master)
$ yarn install
yarn install v1.15.2
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 🔨  Building fresh packages...
✨  Done in 0.17s.

[15:22:04] ~/dev/projects/ncc-build-repro (master)
$ ncc build first/index.ts
ncc: Using typescript@3.2.2 (ncc built-in)
ncc: Module directory "/Users/problematic/dev/projects/ncc-build-repro/first" attempted to require "lodash" but could not be resolved, assuming external.
Error: Hash: c6009c97d70ec0e81948
Version: webpack 5.0.0-alpha.9
Time: 837ms
Built at: 03/20/2019 3:22:08 PM
   Asset      Size  Chunks  Chunk Names
index.js  3.46 KiB   {404}  main
Entrypoint main = index.js
[182] ./first/index.ts 52 bytes {404} [not cacheable] [built] [failed] [1 error]
[399] external "lodash" 42 bytes {404} [built]
    + 3 hidden modules

ERROR in /Users/problematic/dev/projects/ncc-build-repro/first/index.ts
./first/index.ts
[tsl] ERROR in /Users/problematic/dev/projects/ncc-build-repro/first/index.ts(1,20)
      TS2307: Cannot find module 'lodash'.

ERROR in /Users/problematic/dev/projects/ncc-build-repro/second/index.ts
[tsl] ERROR in /Users/problematic/dev/projects/ncc-build-repro/second/index.ts(1,21)
      TS2307: Cannot find module 'express'.

    at compiler.close.n (evalmachine.<anonymous>:3:1349875)
    at _promise0.then._result0 (eval at create (evalmachine.<anonymous>:1:349386), <anonymous>:13:1)
    at process._tickCallback (internal/process/next_tick.js:68:7)
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.

[15:22:08] ~/dev/projects/ncc-build-repro (master)

$ cd first && yarn install
yarn install v1.15.2
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 🔨  Building fresh packages...
✨  Done in 0.75s.

[15:23:32] ~/dev/projects/ncc-build-repro/first (master)
$ cd ..

[15:23:33] ~/dev/projects/ncc-build-repro (master)
$ ncc build first/index.ts
ncc: Using typescript@3.2.2 (ncc built-in)
Error: Hash: 204254a89fa4f8e01b1a
Version: webpack 5.0.0-alpha.9
Time: 734ms
Built at: 03/20/2019 3:23:36 PM
   Asset     Size  Chunks  Chunk Names
index.js  531 KiB   {404}  main
Entrypoint main = index.js
[182] ./first/index.ts 52 bytes {404} [not cacheable] [built]
[838] ./first/node_modules/lodash/lodash.js 527 KiB {404}
    + 4 hidden modules

ERROR in /Users/problematic/dev/projects/ncc-build-repro/second/index.ts
[tsl] ERROR in /Users/problematic/dev/projects/ncc-build-repro/second/index.ts(1,21)
      TS2307: Cannot find module 'express'.

    at compiler.close.n (evalmachine.<anonymous>:3:1349875)
    at _promise0.then._result0 (eval at create (evalmachine.<anonymous>:1:349386), <anonymous>:13:1)
    at process._tickCallback (internal/process/next_tick.js:68:7)
error Command failed with exit code 1.
info Visit https://yarnpkg.com/en/docs/cli/run for documentation about this command.

[15:23:37] ~/dev/projects/ncc-build-repro (master)
$ cd second && yarn install
yarn install v1.15.2
[1/4] 🔍  Resolving packages...
[2/4] 🚚  Fetching packages...
[3/4] 🔗  Linking dependencies...
[4/4] 🔨  Building fresh packages...
✨  Done in 0.42s.

[15:23:42] ~/dev/projects/ncc-build-repro/second (master)
$ cd ..

[15:23:44] ~/dev/projects/ncc-build-repro (master)
$ ncc build first/index.ts
ncc: Using typescript@3.2.2 (ncc built-in)
531kB  dist/index.js
531kB  [1596ms] - ncc 0.16.1
✨  Done in 1.85s.

[15:23:47] ~/dev/projects/ncc-build-repro (master)
$
```
