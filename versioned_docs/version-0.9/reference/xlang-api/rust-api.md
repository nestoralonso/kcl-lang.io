---
sidebar_position: 7
---

# Rust API

## Installation

```shell
cargo add --git https://github.com/kcl-lang/lib
```

## Quick Start

```rust
use kcl_lang::*;
use anyhow::Result;

fn main() -> Result<()> {
    let api = API::default();
    let args = &ExecProgramArgs {
        k_filename_list: vec!["main.k".to_string()],
        k_code_list: vec!["a = 1".to_string()],
        ..Default::default()
    };
    let exec_result = api.exec_program(args)?;
    println!("{}", exec_result.yaml_result);
    Ok(())
}
```

More Rust APIs can be found [here](https://github.com/kcl-lang/kcl). If you want to use the sub crate of KCL Rust core, you can run the following command.

```shell
# Take the kclvm-runtime as an example.
cargo add --git https://github.com/kcl-lang/kcl kclvm-runtime
```
