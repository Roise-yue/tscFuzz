# TypeScript Debug Failure #58924

This repository contains two TypeScript programs that trigger the "Debug Failure #58924" issue. The following details describe the programs and the steps to reproduce the issue.

## Programs

### Program 1: `importHelpersNoHelpers.ts`

This program triggers the debug failure within class `C` and its interior.

#### Files and Code

- **importHelpersNoHelpers.ts**

    ```typescript
    // @importHelpers: true
    // @target: es5
    // @module: commonjs
    // @moduleResolution: classic
    // @experimentalDecorators: true
    // @emitDecoratorMetadata: true

    export * from "./other";
    export class A { }
    export class B extends A { }
    declare var dec: any;

    @dec
    class C {
        method(@dec x: number) { // Error location
        }
    }

    const o = { a: 1 };
    const y = { ...o };
    const { ...x } = y;

    // @filename: other.ts
    export const x = 1;

    // @filename: script.ts
    class A { }
    class B extends A { }
    declare var dec: any;

    @dec
    class C {
        method(@dec x: number) {
        }
    }

    // @filename: tslib.d.ts
    export {}
    ```

### Program 2: `autoAccessorDisallowedModifiers.ts`

This program triggers the debug failure on the line `accessor enum E1 {}`.

#### Files and Code

- **autoAccessorDisallowedModifiers.ts**

    ```typescript
    // @target: esnext
    // @noTypesAndSymbols: true

    abstract class C1 {
        accessor accessor a: any;
        readonly accessor b: any;
        declare accessor c: any;
        accessor public d: any;
        accessor private e: any;
        accessor protected f: any;
        accessor abstract g: any;
        accessor static h: any;
        accessor i() {}
        accessor get j() { return false; }
        accessor set k(v: any) {}
        accessor constructor() {}
        accessor l?: any;
        accessor readonly m: any;
        accessor declare n: any;
    }

    class C2 extends C1 {
        accessor override g: any;
    }

    interface I1 {
        accessor a: number;
    }

    accessor class C3 {}

    accessor interface I2 {}

    accessor namespace N1 {}

    accessor enum E1 {} // Error location

    accessor var V1: any;
    accessor type T1 = never;
    accessor function F1() {}
    accessor import "x";
    accessor import {} from "x";
    accessor export { V1 };
    accessor export default V1;
    accessor import N2 = N1;
    ```

## Reproducing the Issue

To reproduce the issue, you can use the provided Docker image and node.js/tsc configuration files.

### Setup

1. **Clone the repository:**

    ```sh
    git clone <repository-url>
    cd <repository-directory>
    ```

2. **Load the Docker image:**

    ```sh
    docker load -i y1_image.tar
    ```

3. **Run the Docker container:**

    ```sh
    docker run -it --name ts-debug-container y1_image
    ```

### Compile the Programs

Inside the Docker container, compile the TypeScript programs to observe the debug failures.

1. **Compile `importHelpersNoHelpers.ts`:**

    ```sh
    cd TSCFuzzer/tscFuzz
    tsc checked/importHelpersNoHelpers.ts
    ```

2. **Compile `autoAccessorDisallowedModifiers.ts`:**

    ```sh
    tsc autoAccessorDisallowedModifiers.ts
    ```

## Configuration Files

Ensure the configuration files are correctly set up in your environment.

