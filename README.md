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


1. Setup
   
Create a new project called anchor-counter by running anchor init:
```
anchor init anchor-counter
```
Change into the new directory, then run anchor build
```
cd anchor-counter
anchor build
```
Anchor build will also generate a keypair for your new program - the keys are saved in the target/deploy directory.
Open the file lib.rs and look at declare_id!:
```
declare_id!("BouTUP7a3MZLtXqMAm1NrkJSKwAjmid8abqiNjUyBJSr");
```
and then run
```
anchor keys sync
```
You'll see the Anchor updates both:

- The key used in declare_id!() in lib.rs
- The key in Anchor.toml

To match the key generated during anchor build:
```
Found incorrect program id declaration in "anchor-counter/programs/anchor-counter/src/lib.rs"
Updated to BouTUP7a3MZLtXqMAm1NrkJSKwAjmid8abqiNjUyBJSr
 
Found incorrect program id declaration in Anchor.toml for the program `anchor_counter`
Updated to BouTUP7a3MZLtXqMAm1NrkJSKwAjmid8abqiNjUyBJSr
 
All program id declarations are synced.
```
Finally, delete the default code in lib.rs until all that is left is the following:
```
use anchor_lang::prelude::*;
 
declare_id!("onchain-program-address");
 
#[program]
pub mod anchor_counter {
    use super::*;
}
```

Read more [Solana Course](https://solana.com/developers/courses/onchain-development/intro-to-anchor)
