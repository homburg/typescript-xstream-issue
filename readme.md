# ISSUE

When importing `xstream/extra/fromEvent` with typescript 2.1.x, I get a 89 type errors.

AFAICT it's caused by the triple typing reference in [`fromEvent.ts`](https://github.com/staltz/xstream/blob/v10.1.0/src/extra/fromEvent.ts#L1])


```
> typescript-xstream-issue@1.0.0 build /Users/tbh/code/typescript-xstream-issue
> webpack


[at-loader] Using typescript@2.1.5 from typescript and "tsconfig.json" from /Users/tbh/code/typescript-xstream-issue/tsconfig.json.


[at-loader] Checking started in a separate process...
Hash: f67c3f5ebab4ed97dc98
Version: webpack 2.2.1
Time: 1186ms
             Asset     Size  Chunks             Chunk Names
    dist/bundle.js  65.2 kB       0  [emitted]  main
dist/bundle.js.map  79.9 kB       0  [emitted]  main
   [0] ./~/xstream/extra/fromEvent.js 4.29 kB {0} [built]
   [1] ./~/symbol-observable/index.js 41 bytes {0} [built]
   [2] ./~/symbol-observable/lib/index.js 661 bytes {0} [built]
   [3] ./~/symbol-observable/lib/ponyfill.js 449 bytes {0} [built]
   [4] (webpack)/buildin/global.js 509 bytes {0} [built]
   [5] (webpack)/buildin/module.js 517 bytes {0} [built]
   [6] ./~/xstream/index.js 55.3 kB {0} [built]
   [7] ./src/app.ts 143 bytes {0} [built]

ERROR in [at-loader] node_modules/@types/node/index.d.ts:70:5 
    Subsequent variable declarations must have the same type.  Variable 'main' must be of type 'any', but here has type 'NodeModule | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:81:5 
    Subsequent variable declarations must have the same type.  Variable 'parent' must be of type 'any', but here has type 'NodeModule | null'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:82:5 
    Subsequent variable declarations must have the same type.  Variable 'children' must be of type 'any[]', but here has type 'NodeModule[]'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:110:13 
    Subsequent variable declarations must have the same type.  Variable 'Buffer' must be of type '{ new (str: string, encoding?: string | undefined): Buffer; new (size: number): Buffer; new (arra...', but here has type '{ new (str: string, encoding?: string | undefined): Buffer; new (size: number): Buffer; new (arra...'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:380:9 
    Subsequent variable declarations must have the same type.  Variable 'versions' must be of type '{ http_parser: string; node: string; v8: string; ares: string; uv: string; zlib: string; openssl:...', but here has type 'ProcessVersions'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:411:9 
    Subsequent variable declarations must have the same type.  Variable 'platform' must be of type 'string', but here has type 'Platform'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:569:26 
    Duplicate identifier 'Buffer'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:569:50 
    Duplicate identifier 'SlowBuffer'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:613:5 
    An export assignment cannot be used in a module with other exported elements.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:759:18 
    Duplicate identifier 'Agent'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:817:18 
    Duplicate identifier 'Worker'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:975:16 
    Subsequent variable declarations must have the same type.  Variable 'workers' must be of type 'Worker[]', but here has type '{ [index: string]: Worker; }'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:1346:9 
    Subsequent variable declarations must have the same type.  Variable 'SNICallback' must be of type '((servername: string) => any) | undefined', but here has type '((servername: string, cb: (err: Error, ctx: SecureContext) => any) => any) | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:1374:16 
    Subsequent variable declarations must have the same type.  Variable 'Agent' must be of type 'new (options?: RequestOptions | undefined) => Agent', but here has type 'new (options?: AgentOptions | undefined) => Agent'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:1546:17 
    Duplicate identifier 'CompleterResult'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:1606:9 
    Subsequent variable declarations must have the same type.  Variable 'stdio' must be of type '(Readable | Writable)[]', but here has type '[Writable, Readable, Readable]'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:2828:16 
    Subsequent variable declarations must have the same type.  Variable 'StringDecoder' must be of type 'new (encoding: string) => NodeStringDecoder', but here has type 'new (encoding?: string | undefined) => NodeStringDecoder'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3076:9 
    Subsequent variable declarations must have the same type.  Variable 'pfx' must be of type 'any', but here has type 'string | Buffer[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3077:9 
    Subsequent variable declarations must have the same type.  Variable 'key' must be of type 'any', but here has type 'string | any[] | Buffer | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3079:9 
    Subsequent variable declarations must have the same type.  Variable 'cert' must be of type 'any', but here has type 'string | Buffer | Buffer[] | string[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3080:9 
    Subsequent variable declarations must have the same type.  Variable 'ca' must be of type 'any', but here has type 'string | Buffer | Buffer[] | string[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3081:9 
    Subsequent variable declarations must have the same type.  Variable 'crl' must be of type 'any', but here has type 'string | string[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3083:9 
    Subsequent variable declarations must have the same type.  Variable 'honorCipherOrder' must be of type 'any', but here has type 'boolean | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3086:9 
    Subsequent variable declarations must have the same type.  Variable 'NPNProtocols' must be of type 'any', but here has type 'Buffer | string[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3087:9 
    Subsequent variable declarations must have the same type.  Variable 'SNICallback' must be of type '((servername: string) => any) | undefined', but here has type '((servername: string, cb: (err: Error, ctx: SecureContext) => any) => any) | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3102:9 
    Subsequent variable declarations must have the same type.  Variable 'pfx' must be of type 'any', but here has type 'string | Buffer | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3103:9 
    Subsequent variable declarations must have the same type.  Variable 'key' must be of type 'any', but here has type 'string | Buffer | Buffer[] | string[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3105:9 
    Subsequent variable declarations must have the same type.  Variable 'cert' must be of type 'any', but here has type 'string | Buffer | Buffer[] | string[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3106:9 
    Subsequent variable declarations must have the same type.  Variable 'ca' must be of type 'any', but here has type 'string | Buffer | (string | Buffer)[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3108:9 
    Subsequent variable declarations must have the same type.  Variable 'NPNProtocols' must be of type 'any', but here has type '(string | Buffer)[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3204:9 
    Subsequent variable declarations must have the same type.  Variable 'pfx' must be of type 'any', but here has type 'string | Buffer | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3205:9 
    Subsequent variable declarations must have the same type.  Variable 'key' must be of type 'any', but here has type 'string | Buffer | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3207:9 
    Subsequent variable declarations must have the same type.  Variable 'cert' must be of type 'any', but here has type 'string | Buffer | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3208:9 
    Subsequent variable declarations must have the same type.  Variable 'ca' must be of type 'any', but here has type 'string | Buffer | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3209:9 
    Subsequent variable declarations must have the same type.  Variable 'crl' must be of type 'any', but here has type 'string | string[] | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3244:9 
    Subsequent variable declarations must have the same type.  Variable 'ca' must be of type 'any', but here has type 'string | string[]'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3245:9 
    Subsequent variable declarations must have the same type.  Variable 'crl' must be of type 'any', but here has type 'string | string[]'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3345:9 
    Subsequent variable declarations must have the same type.  Variable 'padding' must be of type 'any', but here has type 'number | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3350:9 
    Subsequent variable declarations must have the same type.  Variable 'padding' must be of type 'any', but here has type 'number | undefined'.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3610:5 
    An export assignment cannot be used in a module with other exported elements.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3693:5 
    Duplicate identifier 'export='.

ERROR in [at-loader] node_modules/@types/node/index.d.ts:3715:18 
    Duplicate identifier 'Domain'.

ERROR in [at-loader] node_modules/xstream/index.d.ts:178:27 
    Cannot find name 'Promise'.

ERROR in [at-loader] node_modules/xstream/index.d.ts:229:36 
    Cannot find name 'Promise'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:406:9 
    'BuffType' is referenced directly or indirectly in its own type annotation.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:407:9 
    'SlowBuffType' is referenced directly or indirectly in its own type annotation.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:408:26 
    Duplicate identifier 'Buffer'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:408:50 
    Duplicate identifier 'SlowBuffer'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:429:18 
    Class 'EventEmitter' incorrectly implements interface 'NodeJS.EventEmitter'.
  Types of property 'addListener' are incompatible.
    Type '(event: string, listener: Function) => EventEmitter' is not assignable to type '{ (event: string, listener: Function): EventEmitter; (event: string | symbol, listener: Function)...'.
      Type 'EventEmitter' is not assignable to type 'NodeJS.EventEmitter'.
        Property 'prependListener' is missing in type 'EventEmitter'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:467:22 
    Interface 'Server' cannot simultaneously extend types 'EventEmitter' and 'Server'.
  Named property 'addListener' of types 'EventEmitter' and 'Server' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:467:22 
    Interface 'Server' cannot simultaneously extend types 'EventEmitter' and 'Server'.
  Named property 'emit' of types 'EventEmitter' and 'Server' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:467:22 
    Interface 'Server' cannot simultaneously extend types 'EventEmitter' and 'Server'.
  Named property 'on' of types 'EventEmitter' and 'Server' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:467:22 
    Interface 'Server' cannot simultaneously extend types 'EventEmitter' and 'Server'.
  Named property 'once' of types 'EventEmitter' and 'Server' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:467:22 
    Interface 'Server' cannot simultaneously extend types 'EventEmitter' and 'Server'.
  Named property 'prependListener' of types 'EventEmitter' and 'Server' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:467:22 
    Interface 'Server' cannot simultaneously extend types 'EventEmitter' and 'Server'.
  Named property 'prependOnceListener' of types 'EventEmitter' and 'Server' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:467:22 
    Interface 'Server' cannot simultaneously extend types 'EventEmitter' and 'Server'.
  Named property 'removeListener' of types 'EventEmitter' and 'Server' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:482:22 
    Interface 'ServerResponse' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'addListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:482:22 
    Interface 'ServerResponse' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'emit' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:482:22 
    Interface 'ServerResponse' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'on' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:482:22 
    Interface 'ServerResponse' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'once' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:482:22 
    Interface 'ServerResponse' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'prependListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:482:22 
    Interface 'ServerResponse' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'prependOnceListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:482:22 
    Interface 'ServerResponse' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'removeListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:510:22 
    Interface 'ClientRequest' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'addListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:510:22 
    Interface 'ClientRequest' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'emit' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:510:22 
    Interface 'ClientRequest' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'on' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:510:22 
    Interface 'ClientRequest' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'once' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:510:22 
    Interface 'ClientRequest' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'prependListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:510:22 
    Interface 'ClientRequest' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'prependOnceListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:510:22 
    Interface 'ClientRequest' cannot simultaneously extend types 'EventEmitter' and 'Writable'.
  Named property 'removeListener' of types 'EventEmitter' and 'Writable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:531:22 
    Interface 'IncomingMessage' cannot simultaneously extend types 'EventEmitter' and 'Readable'.
  Named property 'addListener' of types 'EventEmitter' and 'Readable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:531:22 
    Interface 'IncomingMessage' cannot simultaneously extend types 'EventEmitter' and 'Readable'.
  Named property 'emit' of types 'EventEmitter' and 'Readable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:531:22 
    Interface 'IncomingMessage' cannot simultaneously extend types 'EventEmitter' and 'Readable'.
  Named property 'on' of types 'EventEmitter' and 'Readable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:531:22 
    Interface 'IncomingMessage' cannot simultaneously extend types 'EventEmitter' and 'Readable'.
  Named property 'once' of types 'EventEmitter' and 'Readable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:531:22 
    Interface 'IncomingMessage' cannot simultaneously extend types 'EventEmitter' and 'Readable'.
  Named property 'prependListener' of types 'EventEmitter' and 'Readable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:531:22 
    Interface 'IncomingMessage' cannot simultaneously extend types 'EventEmitter' and 'Readable'.
  Named property 'prependOnceListener' of types 'EventEmitter' and 'Readable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:531:22 
    Interface 'IncomingMessage' cannot simultaneously extend types 'EventEmitter' and 'Readable'.
  Named property 'removeListener' of types 'EventEmitter' and 'Readable' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:581:18 
    Duplicate identifier 'Agent'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:620:18 
    Duplicate identifier 'Worker'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:868:22 
    Duplicate identifier 'CompleterResult'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1088:22 
    Interface 'Server' cannot simultaneously extend types 'Socket' and 'EventEmitter'.
  Named property 'removeListener' of types 'Socket' and 'EventEmitter' are not identical.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1616:22 
    Interface 'Server' incorrectly extends interface 'Server'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1616:22 
    Interface 'Server' incorrectly extends interface 'Server'.
  Types of property 'listen' are incompatible.
    Type '{ (port: number, host?: string | undefined, backlog?: number | undefined, listeningListener?: Fun...' is not assignable to type '{ (port: number, host?: string | undefined, backlog?: number | undefined, listeningListener?: Fun...'. Two different types with this name exist, but they are unrelated.
      Type 'Server' is not assignable to type 'Server'. Two different types with this name exist, but they are unrelated.
        Types of property 'listen' are incompatible.
          Type '{ (port: number, host?: string | undefined, backlog?: number | undefined, listeningListener?: Fun...' is not assignable to type '{ (port: number, host?: string | undefined, backlog?: number | undefined, listeningListener?: Fun...'. Two different types with this name exist, but they are unrelated.
            Types of parameters 'host' and 'backlog' are incompatible.
              Type 'number | undefined' is not assignable to type 'string | undefined'.
                Type 'number' is not assignable to type 'string | undefined'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1781:18 
    Class 'Readable' incorrectly implements interface 'ReadableStream'.
  Types of property 'pause' are incompatible.
    Type '() => void' is not assignable to type '{ (): void; (): ReadableStream; }'.
      Type 'void' is not assignable to type 'ReadableStream'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1818:18 
    Class 'Duplex' incorrectly implements interface 'ReadWriteStream'.
  Types of property 'pause' are incompatible.
    Type '() => void' is not assignable to type '() => ReadWriteStream'.
      Type 'void' is not assignable to type 'ReadWriteStream'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1832:18 
    Class 'Transform' incorrectly implements interface 'ReadWriteStream'.
  Types of property 'pause' are incompatible.
    Type '() => void' is not assignable to type '() => ReadWriteStream'.
      Type 'void' is not assignable to type 'ReadWriteStream'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1923:5 
    Duplicate identifier 'export='.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1945:18 
    Duplicate identifier 'Domain'.

ERROR in [at-loader] node_modules/xstream/typings/globals/node/index.d.ts:1945:18 
    Class 'Domain' incorrectly extends base class 'EventEmitter'.
  Types of property 'addListener' are incompatible.
    Type '(event: string, listener: Function) => Domain' is not assignable to type '(event: string | symbol, listener: Function) => this'.
      Type 'Domain' is not assignable to type 'this'.

```
