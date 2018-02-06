# tsc -w problem

## Clone + install

1. `git clone https://github.com/marianmeres/typescript-2.7.1-issue.git`
2. `cd typescript-2.7.1-issue && npm install`

## Regular (first run) compilation:

1. do `npm run build` (runs `tsc`) or `npm run watch` (runs `tsc -w`)
2. `node dist/`

Console output:
```
a
b
```

## Watch mode with actual edit compilation:

1. `npm run watch` (runs `tsc -w`)
2. do any dummy edit (add comment) in `b.ts`
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
a
b
```


## Notes

Everything works fine with version 2.6.2 