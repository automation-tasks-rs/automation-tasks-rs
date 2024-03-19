# automation_tasks_rs

***Automation tasks coded in Rust language for the workflow of Rust projects***

 ![maintained](https://img.shields.io/badge/maintained-green)
 ![ready-for-use](https://img.shields.io/badge/ready_for_use-green)
 ![rustlang](https://img.shields.io/badge/rustlang-orange)
 ![make](https://img.shields.io/badge/make-orange)

 ![logo](https://raw.githubusercontent.com/automation-tasks-rs/cargo-auto/main/images/logo/logo_cargo_auto.svg)
 automation-tasks-rs is a "GitHub organization" that groups [multiple repositories](https://github.com/orgs/automation-tasks-rs/repositories?q=sort%3Aname-asc) together

Cargo is a great tool for building Rust projects. It has all the basics: `cargo build`, `cargo build --release`, `cargo fmt`, `cargo test`, `cargo doc`,...

But sometimes we need to do more things like copying some files, publishing to FTP, or entering long commands. These repetitive tasks must be automated.  
Task automation makes work easier and faster, and simplifies the workflow while improving the consistency and accuracy of workflows.  
This is also sometimes referred to as "workflow automation."  
There are many different build systems and task runners there: `make`, `cmake`, `shell scripts`, `cargo-xtask`, `cargo-make`, `cargo-task`, `cargo-script`, `cargo-run-script`, `runner`, `python scripts`, `powershell scripts`, `cmd prompt scripts`, ...  
Sadly there is no standard in the Rust community for now.  

But I don't want to learn another metalanguage with weird syntax that is difficult to debug.  
I want something similar to [build.rs](https://doc.rust-lang.org/cargo/reference/build-scripts.html), so I can write my "automation tasks" in pure Rust.  
Some kind of Rust scripting language for workflow automation.   
  
Enter `cargo-auto`, `cargo_auto_lib`, `dev_bestia_cargo_completion` and `automation_tasks_rs`.  
A simple system for workflow automation in pure Rust.  

## CRDE - Containerized Rust Development Environment

I recommend using the CRDE - Containerized Rust Development Environment to write Rust projects.  
Follow the instructions here  
<https://github.com/CRUSTDE-Containerized-Rust-Dev-Env/docker_rust_development>.  

It is an isolated development environment that will not mess with your system.  
It will work on Linux (tested on Debian) and inside WSL (Windows Subsystem for Linux).

You just need to install the newer alternative to Docker: [podman](https://podman.io/). Then you download the prepared container image from DockerHub (3GB). And then a little juggling with ssh keys. All this is simplified by running a few bash scripts. Just follow the easy instructions.  

The container image contains cargo, rustc, wasm-pack, basic-http-server, cargo-auto and other utils that a Rust project needs.  

## cargo auto new_cli

Use `cargo auto new_cli hello_world` to create a fully functional Rust project.  
It has a moderately complex structure for real life Rust CLI projects. It includes the automation_tasks_rs workflow.

## Workflow with automation_tasks_rs

Automation tasks are already coded in the sub-project `automation_tasks_rs`. This is a basic workflow:

```bash
cargo auto build
cargo auto release
cargo auto doc
cargo auto test
cargo auto commit_and push
cargo auto publish_to_crates_io
cargo auto github_new_release
```

Every task finishes with instructions how to proceed.  
The [cargo-auto](https://github.com/automation-tasks-rs/cargo-auto) and [dev_bestia_cargo_completion](https://github.com/automation-tasks-rs/dev_bestia_cargo_completion) are already installed inside the CRDE container.

You can open the automation sub-project in VSCode and then code your own tasks in Rust.

```bash
code automation_tasks_rs
```

## Based on simple functions

All the functions of `cargo_auto_lib` have extensive help/docs to describe how they work.  
This is very nice when you use a code editor with Rust-analyzer.  
Inside the `automation_tasks_rs` you can write your own code. 

No limits there. It is just Rust.  
