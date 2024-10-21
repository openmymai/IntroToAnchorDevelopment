## Intro to Anchor Development

- **Programs** on Solana have **instruction handlers**, which are functions that take arguments from incoming instructions. They are the entry point for any operation in a program.
- **Rust** is the most common language for building Solana programs. The **Anchor** framework takes care of common grunt work - like reading data from incoming instructions, and checking the right accounts are provided - so you can focus on building your Solana program.

## What is Anchor?
Anchor makes writing Solana programs easier, faster, and more secure, making it the "go-to" framework for Solana development. It makes it easier to organize and reason about your code, implements common security checks automatically, and removes a significant amount of boilerplate code that is otherwise associated with writing a Solana program.

## Anchor program structure
Anchor uses macros and traits to simplify Rust code for you. These provide a clear structure to your program so you can focus more on its functionality.

Some important macros provided by Anchor are:

- declare_id! - a macro for declaring the program’s onchain address
- #[program] - an attribute macro used to denote the module containing the program’s instruction handlers.
- Accounts - a trait applied to structs representing the list of accounts required for an instruction.
- #[account] - an attribute macro used to define custom account types for the program.
