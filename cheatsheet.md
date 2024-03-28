# Vault Command (CLI) Cheat Sheet

Caveat: This is a community-developed work in progress.

## Definitions and Conventions

| Term                                 | Definition                                                                                                                                                                 |
|--------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| CLI                                  | Command Line Interface. Usually used from a terminal.                                                                                                                      |
| Environment variables (aka env vars) | Information stored in your terminal environment that is sent to the CLI when needed. You can check these with the command `env` on bash and zsh terminals.                 |
| GET, POST, PUT, DELETE               | These are types of REST API calls. For more information, see the REST API docs.                                                                                            |
| arg                                  | A command-line argument. Sometimes these are positional, meaning they have to be before or after other specific command arguments.                                         |
| cas                                  | Check and Set (kv engine: send current parameter before changing it)                                                                                                       |
| boolean                              | Enter a true or false value as fits your situation                                                                                                                         |
| NULL                                 | No values to input                                                                                                                                                         |
| OMIT                                 | If left out, this parameter will be set to the default value. Commonly used in `vault secrets enable` examples, where the engine path defaults to aws, database, gcp, etc. |
| slice                                | Most commonly in this reference, a slice is a comma-separated list of values. It can also be a more complex set of commands (such as sql to create users).                 |

| Convention       | Definition                                                                                                                                     |   |
|------------------|------------------------------------------------------------------------------------------------------------------------------------------------|---|
| \| (pipe symbol) | A \| (pipe) symbol means ‘or’. Example: `OMIT \| -path <path>` means to either omit path entirely or specify a custom path with the -path arg. |   |
| $CAPS (env vars) | Words in all caps with a $, such as $VAULT_ADDR, refer to environment variables that are read by vault CLI when they are set.                  |   |
| \`command\` (backticks) | Backticks (\`) are used to indicate a command to run in a terminal, such as `env \| grep VAULT` . | |
| … (ellipses)          | Ellipses (...) are used to indicate there are additional options, subcommands, or more information.                                                                    |                 |
| \<variable\> (carets)   | Carets (<>) are used to indicate a variable, where yours may be different for your situation, such as a filename. When entering a variable, do not include the carets. |                 |
| [ ] (brackets)        | Brackets ([ ]) are used to indicate that whatever is in them is not always required.                                                                                   |                 |
| @\<file\>             | The @\<file\> syntax is used to load a file into configuration, rather than typing configuration on the command line.                                                    |                 |
