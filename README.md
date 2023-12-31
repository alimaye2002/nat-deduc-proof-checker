## Natural-Deduction-Proof-Checker
The goal of the project is to develop a programming language that eases writing, automates validating and enables reusing Natural Deduction proofs. The built checker should be published as a Visual Studio Code plug-in/extension for open use.

#### Topics Involved
Discrete Mathematics, Compiler Construction, (some) Development

----

### Phases of the Project

#### 1. Getting equipped
- Understand **First Order Logic (FOL)** and the **Inference Rules** (CS'23 and 24 students must be familiar with this from the Discrete Structures course in 2-1).
- **Compiler Construction** - Understand how programming languages are designed:
    - Components of a compiler (on a high-level): Scanner and Parser
    - Context-Free Grammar (CFG)
    - Abstract Syntax Tree (AST)
- Get familiar with **SLY**, the Python language implementation of the tools used to write scanners and parsers.

#### 2. Building the language
- Aim to build a first version without involving quantifiers:
    - Design the **Syntactical structure** of the programming language, i.e., decide the format/syntax for writing the proofs.
    - Build the **Scanner** using SLY.
    - Define the Context-free **Grammar**, the set of instructions that help in building the AST.
    - Design the **Validation Logic**- need to check if each step of the proof is inferred correctly using the appropriate inference rules and valid referenced expressions.
    - Build the **Parser** based on the CFG and validation-logic using SLY. (Each step will be verified in the parser just as the statement is parsed)
- Incorporate proofs and rules with **Quantifiers**.
- Incoporate **Generic Inferences** - create something like a library that stores snippets of proofs of commonly used derivations for added convenience in terms of removed redundancy, increased readability and improved efficiency of writing a proof.

#### 3. VSCode Plug-in
- Publish the proof checker as a VSCode extension.
New to it too :/ But [this](https://www.freecodecamp.org/news/making-vscode-extension/) makes it look straightforward :)

#### 4. Usage
1. Copy the folder `extensions/nat-deduc-ext` into the directory `/Users/<user_name>/.vscode/extensions/`. This will enable the plug-ins such as syntax-highlighting and automatic snippet-completions for VS-code.
2. Create a python virtual environment and install sly package.
    1. Run `python3 venv -m <env_name>`
    2. Run `source <env_name>/bin/activate`
    3. Run `pip3 install sly`
3. Create your own proof-checking `.ndp` files inside the `proofs/inputs/` directory. To start the proof-checker, Run `make file=<file_name>.ndp` . The outputs will be stored inside the `proofs/outputs/` dirctory under the name `<file_name>_verified.txt`. A `sample.ndp` file has been provided for your reference. Run `make file=sample.ndp` to see the result stored in `proofs/outputs/sample_verified.txt`.
