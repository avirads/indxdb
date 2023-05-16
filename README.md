# indxdb
compiling surreal's indxdb to wasm https://github.com/surrealdb/indxdb

Install rust using recommended procedure
    https://www.rust-lang.org/tools/install

Install wasm toolchain
    rustup target add wasm32-unknown-unknown

Create a new lib project
    cargo new idb --lib
    cd idb

Add the SurrealDB indxdb crate: https://crates.io/crates/indxdb
    cargo add indxdb

Open Cargo.toml and add below lines to the bottom and save
    [lib]
    crate-type = ["cdylib"]

Compile the project to Wasm
    cargo build --target wasm32-unknown-unknown --release

Copy the created idb.wasm file in the directory target/wasm32-unknown-unknown/release/idb.wasm into the webserver html directory

Open the console and observe the instance output

    Instance {exports: {…}}
    exports
    : 
    {memory: Memory(16), __data_end: Global, __heap_base: Global}
    [[Prototype]]
    : 
    WebAssembly.Instance
    [[Module]]
    : 
    Module
    [[Globals]]
    : 
    Globals
    [[Memories]]
    : 
    Memories
    [[Tables]]
    : 
    Tables

