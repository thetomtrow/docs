# Setting Up Your Environment

:::info
The environment will be setup for you automatically if you use [Fluence CLI](../fluence-cli)
:::

In order to develop within the Fluence solution, [Node](https://nodejs.org/en/), [Rust](https://www.rust-lang.org/tools/install) and small number of tools are required.

## Node.js

[Download the installer](https://nodejs.org/en/download/) for your platform and follow the instructions.

## Rust

If you're on Linux, MacOS or other Unix-like, you can install Rust like this:
<!-- cSpell:disable -->
```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
<!-- cSpell:enable -->

If you're on other platform, please see [rustup.rs](https://rustup.rs) for instructions.

Once Rust is installed, we need to expand the toolchain and include [nightly build](https://rust-lang.github.io/rustup/concepts/channels.html) and the [Wasm](https://doc.rust-lang.org/stable/nightly-rustc/rustc_target/spec/wasm32_wasi/index.html) compile target.

```sh
rustup install nightly
rustup target add wasm32-wasi
```

To keep Rust and the toolchains updated:

```sh
rustup self update
rustup update
```

There are a number of good Rust installation and IDE integration tutorials available. [DuckDuckGo](https://duckduckgo.com) is your friend but if that's too much effort, have a look at [koderhq](https://www.koderhq.com/tutorial/rust/environment-setup/). Please note, however, that currently only VSCode is supported with Aqua syntax support.

## Aqua Tools

The Aqua compiler and standard library and be installed via npm:

```sh
npm -g install @fluencelabs/aqua
npm -g install @fluencelabs/aqua-lib
```

If you are a VSCode user, note that am Aqua syntax-highlighting extension is available. In VSCode, click on the Extensions button, search for `aqua` and install the extension.

Moreover, the aqua-playground provides a ready to go Typescript template and Aqua example. In a directory of you choice:

```sh
git clone git@github.com:fluencelabs/aqua-playground.git
```

## Marine Tools

Fluence provides several tools to support developers. `marine` is the command line compiler required to compile Rust modules to the necessary wasm32-wasi target. `mrepl`, on the other hand, is a command line  tool providing access to the Marine runtime to test and experiment with marine modules and services locally:

```sh
cargo install marine 
cargo +nightly install mrepl
```

## Aqua Compiler And CLI Tool

Fluence `aqua` provides both compile and cli tools for the lifecycle manage management of distributed services including deployment and execution tools.

```
npm -g install @fluencelabs/aqua
```

## Fluence JS

[Fluence JS](https://github.com/fluencelabs/fluence-js) is currently the favored, and only, tool for frontend development.

```sh
npm install @fluencelabs/fluence
```
