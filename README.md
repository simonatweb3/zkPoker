## Prerequisite

**Setup Yarn v2 to enable workspace feature**
> Note: you need to migrate to Yarn v2 if not already, guide [here](https://yarnpkg.com/getting-started/migration). 
Follow the [Yarn official instruction](https://yarnpkg.com/getting-started/install)
`npm i -g corepack`
`corepack prepare yarn@stable --activate`
`yarn plugin import workspace-tools`
Now we can use yarn workspace commands, [more info](https://yarnpkg.com/cli/workspace)

**Install**

`yarn`

After installation, the dependencies of all the packages will be installed.

**Compile all packages**

`yarn workspaces foreach run compile`

**Test all packages**

`yarn workspaces foreach run test`

## Packages

**`💡 @zk-shuffle/circuits`**

This package contains all the Circom circuit components with related unit test cases. Circuit integrators can directly import the circuits in this package.

**Install**

`yarn install @zk-shuffle/circuits`

If you want to develop based on this package, it's highly recommended to change the default `ptau` setting in `hardhat.config.ts` to your own generated trust setup.

**Compile**

`yarn compile`

After running compilation, zkey files, wasm files, verifier Solidity contracts will be generated, and can be imported by JavaScript users and contract users.

**Testing**

`yarn test`

**`⛓ @zk-shuffle/contracts`**

This package depends on circuit package and its generated verifier contracts. It extends the contract of verifier contracts and can be integrated by user-end developers.

**Install**

`yarn install @zk-shuffle/contracts`

**Compile**

`yarn compile`

**Testing**

`yarn test`

The unit tests in contracts package use proof generation utilities from `proof` package and perform some e2e tests.

**`🛠 @zk-shuffle/jssdk`**

**Install**

`yarn install @zk-shuffle/jssdk`


**`🧾 @zk-shuffle/proof`**

This package provides some utilities for generating zk proofs and is depended by contracts package to do some unit tests.

**Install**

`yarn install @zk-shuffle/proof`

**Compile**

`yarn compile`
