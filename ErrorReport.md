# Error Report

## Errors Overview

### Error in `autoAccessorDisallowedModifiers.ts`

**Command:**
```sh
tsc autoAccessorDisallowedModifiers.ts
```
**Error Massage:**

/usr/lib/node_modules/typescript/lib/tsc.js:118651
      throw e;
      ^

Error: Debug Failure. Use `modifierVisitor` instead.
    at visitor (/usr/lib/node_modules/typescript/lib/tsc.js:90424:22)
    at visitArrayWorker (/usr/lib/node_modules/typescript/lib/tsc.js:85608:49)
    at visitNodes2 (/usr/lib/node_modules/typescript/lib/tsc.js:85579:19)
    at visitEachChildOfVariableStatement (/usr/lib/node_modules/typescript/lib/tsc.js:86379:7)
    at visitEachChild (/usr/lib/node_modules/typescript/lib/tsc.js:85796:33)
    at visitVariableStatement (/usr/lib/node_modules/typescript/lib/tsc.js:90639:25)
    at visitor (/usr/lib/node_modules/typescript/lib/tsc.js:90435:16)
    at visitArrayWorker (/usr/lib/node_modules/typescript/lib/tsc.js:85608:49)
    at visitNodes2 (/usr/lib/node_modules/typescript/lib/tsc.js:85579:19)
    at visitLexicalEnvironment (/usr/lib/node_modules/typescript/lib/tsc.js:85635:16)

Node.js v20.14.0

### Error in importHelpersNoHelpers.ts

**Command:**
```sh
tsc importHelpersNoHelpers.ts
```
**Error Massage:**

/usr/lib/node_modules/typescript/lib/tsc.js:118651
      throw e;
      ^

Error: Debug Failure.
    at partialTransformClassElement (/usr/lib/node_modules/typescript/lib/tsc.js:94407:15)
    at visitMethodDeclaration (/usr/lib/node_modules/typescript/lib/tsc.js:94459:49)
    at classElementVisitor (/usr/lib/node_modules/typescript/lib/tsc.js:93682:16)
    at /usr/lib/node_modules/typescript/lib/tsc.js:93898:89
    at visitArrayWorker (/usr/lib/node_modules/typescript/lib/tsc.js:85608:49)
    at visitNodes2 (/usr/lib/node_modules/typescript/lib/tsc.js:85579:19)
    at transformClassLike (/usr/lib/node_modules/typescript/lib/tsc.js:93898:15)
    at visitClassDeclaration (/usr/lib/node_modules/typescript/lib/tsc.js:94183:22)
    at visitor (/usr/lib/node_modules/typescript/lib/tsc.js:93583:16)
    at fallbackVisitor (/usr/lib/node_modules/typescript/lib/tsc.js:93666:16)

Node.js v20.14.0

