Iron Fish is a Layer 1 blockchain that provides the strongest privacy guarantees on every single transaction. Leveraging zero-knowledge proofs (zk-SNARKs), and the highest industry standards for encryption.

See https://ironfish.network

Developer Install
The following steps should only be used to install if you are planning on contributing to the Iron Fish codebase. Otherwise, we strongly recommend using the installation methods here: https://ironfish.network/docs/onboarding/installation-iron-fish

Install Node.js 16.x

Install Rust.

Install Yarn.

Windows:

Install the current version of Python from the Microsoft Store package.
Install Visual C++ Build Environment: Visual Studio Build Tools (using "Visual C++ build tools" or "Desktop development with C++" workload)
If the above steps didn't work for you, please visit Microsoft's Node.js Guidelines for Windows for additional tips.

Run yarn install from the root directory to install packages.

If yarn install fails with an error that includes "Failed to build cmake", you may need to first install cmake. For example, on macOS:

Run brew install cmake, you'll need cmake version 3.15 or higher.
If yarn install fails with an error that includes "Could NOT find OpenSSL", you may need to first install OpenSSL and add an environment variable. For example, on macOS:

Run brew install openssl
Run export OPENSSL_ROOT_DIR=`brew --prefix openssl`
Run yarn install again.
If yarn install fails with an error that includes "Error: not found: make", "make: cc: Command not found", or "make: g++: Command not found", you may need to install a C/C++ compiler toolchain.

On Ubuntu: apt install build-essential
On Amazon Linux: sudo yum groupinstall "Development Tools"
If yarn install fails with an error that includes "Error: Could not find any Python installation to use", you may need to install Python3 (required by node-gyp). on macOS:

Run brew install python
Usage
Once your environment is set up - you can run the CLI by following these directions.

Running Tests
To test the entire monorepo:
Run yarn test at the root of the repository
Run yarn test:slow in ./ironfish/ to run slow tests
Run yarn test:coverage at the root of the repository for tests and coverage
To test a specific project
Run yarn test at the root of the project
Run yarn test:watch in ./ironfish or ./ironfish-cli if you want the tests to run on change
Run yarn test:coverage:html if you want to export the coverage in an easy-to-use format (open the index.html file in the coverage folder of the project)
Structure of the repository
ironfish: The library that contains the IronfishSDK and all Ironfish code written in TypeScript.
ironfish-cli: The main client for Iron Fish as of today. It is a command-line interface built on Node. More details in our documentation.
ironfish-rust: Core API for interacting with the transactions and chain and using ZKP.
ironfish-rust-nodejs: Wrapper for ironfish-rust as a native NodeJS addon.
Contributing Code
If you want to contribute code, you must first read our contributing guidelines or risk having your pull request closed.

Other Repositories
iron-fish/homebrew-brew: Contains brew formula for installing via the Brew package manager
iron-fish/website: The repo that powers ironfish.network
iron-fish/website-testnet: The repo that powers testnet.ironfish.network
iron-fish/ironfish-api: The repository that powers most Iron Fish API services.
iron-fish/chain-explorer: A visual tool to explore the block chain and all of its forks.
Licensing
This code base and any contributions will be under the MPL-2.0 Software License.
