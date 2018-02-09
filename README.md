# Typescript 2.7.1 watch mode missing import bug

## Clone + install

1. `git clone https://github.com/marianmeres/typescript-2.7.1-issue.git`
2. `cd typescript-2.7.1-issue && npm install`

## Regular (first run) compilation:

1. do `npm run build` (runs `tsc`) or `npm run watch` (runs `tsc -w`)
2. `node dist/`

Console output:
```
b
a
```

## Watch mode (with actual edit) compilation:

1. `npm run watch` (runs `tsc -w`)
2. do any dummy edit (e.g. add comment) in `a.ts`
3. `node dist/`

Console output:
```
.../typescript-2.7.1-issue/dist/a.js:4
    console.log(b_1.b);
                ^

ReferenceError: b_1 is not defined
...
```

Expected output:
```
b
a
```


## Notes

Everything works fine with version 2.6.2 

---

## Update

Bug should be fixed in 2.7.2. Related links:

https://github.com/Microsoft/TypeScript/issues/21478  
https://github.com/Microsoft/TypeScript/issues/21713  

