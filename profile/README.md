# 🐚 Minishell Organization

Welcome to the **Minishell Organization** – a collaborative effort to build a fully functional shell in C as part of the 42 school curriculum.

## 🎯 Project Overview

Minishell is a simplified Unix shell designed to mimic the behavior of `/bin/bash`. It supports command parsing, input/output redirections, pipelines, environment variable expansion.

This organization splits the project into two main components to support clean development and collaboration:

### 🔧 Repositories

#### 1. [Minishell Parsing](https://github.com/your-org/minishell-parsing)
> **Owner:** _[Hamza Wahmane](https://github.com/Wahmane-Hamza)_

This repository focuses on the **parsing logic**, including:
- Lexical analysis and tokenization
- Grammar parsing (AST generation)
- Command and redirections arrange
- `&&` and `||` with `()` for priorities
- Quote and escape handling
- Syntax validation and error handling

#### 2. [Minishell Execution](https://github.com/your-org/minishell-execution)
> **Owner:** _[Abdellah Nsila](https://github.com/Abdellah-Nsila)_

This repository handles the **execution engine** of the shell. It is responsible for:
- Dollar `$` expansion (`$VAR`, `$?`)
- Wildcard `*` expansion (`*`, `ls *`)
- Process forking and `execve` calls
- Built-in command handling
- Redirections (`<`, `>`, `>>`, `<<`)
- Pipes (`|`)
- Subshells and grouping
- Environment management
- File descriptor restoration and isolation



---

## 🔗 Collaboration Workflow

We follow a modular development approach:

1. **Parsing** builds the AST (Abstract Syntax Tree) and handles all user input processing.
2. **Execution** receives the AST and interprets it to run commands accurately.

Communication between the two repositories happens through a shared structure (AST nodes and enums) and clearly defined interfaces.

---

## 📦 Building the Shell

Each repository can be compiled separately, but to run the shell completely:
- Link the parser output into the executor.
- Use `Makefile` coordination or a script to compile and merge both.

---

## ✅ Features (in progress or complete)

- [x] Tokenization and Parsing
- [x] AST Generation
- [x] Built-in Commands (`cd`, `echo`, `export`, etc.)
- [x] Input/Output Redirections
- [x] Heredoc (`<<`)
- [x] Pipes (`|`)
- [x] Subshells (`(cmd)`)
- [x] Manage fds, filesm redirs (`(<, <<, >, >>)`)
- [x] Environment Variable Expansion
- [x] Wildcard expansion (`*`) *(optional)*
- [x] Signal handling refinement
- [x] Exit code manipulation
- [ ] Test complex commands
- [x] Join Parsing with execution
- [ ] Error and memory management
- [ ] Optimize, clean up files and stream logic

---

## 👥 Contributors

- [Hamza Wahmane](https://github.com/Wahmane-Hamza) – Parsing Logic
- [Abdellah Nsila](https://github.com/Abdellah-Nsila) – Execution Logic

---

## 📚 License

This project is developed as part of the 42 School curriculum. All code is original and follows the guidelines set by the 42 Network.

---

## 🧠 Note

This shell is educational and built under restricted conditions:
- No use of external libraries
- Limited standard C functions
- Manual memory and error management

> The goal is to deeply understand how a real shell works internally.

---

Happy Hacking 💻
