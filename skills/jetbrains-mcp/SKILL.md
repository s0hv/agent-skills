---
name: jetbrains-mcp
description: Use when a JetBrains IDE (IntelliJ, PyCharm, etc.) is available via its MCP server.
  Lists every supported MCP tool with a short note on when to reach for it instead of a generic shell/grep/file equivalent.
---

# When to use

The JetBrains MCP server should be used when possible instead of generic command-line tools
such as `grep` and `find`. Here are some example situations when to use the MCP server:
- Use when searching for a file, symbol or just text
  - `search_file`
  - `search_symbol`
  - `search_text`
  - `search_regex`
- When requiring documentation for a symbol. Works for packages and own code.
  - `get_symbol_info`
- When trying to find out where some code is used
  - `analyze_calls`
- When renaming a symbol
  - `rename_refactoring`
- When listing files
  - `list_directory_tree`

For other use cases, see if the tool name could fit the use-case and read the reference for more information.

# Constraints
- The `projectPath` should always be passed as an argument to prevent ambiguity.
- The tools operate only on project files
- In some cases the user might have disabled some of the MCP server endpoints.
Treat those situations as if you are not supposed to use those tools. If you
still require the tool, ask the user for clarification.
- Control the output manually to prevent the tool output from being too long or taking too long to process.

# Tools available
The following sections either list tools explicitly or provide a short not on 
when to reach for them in the reference file. The reference files contain a complete
overview of all that is available. If a section could contain the tool, you should load it and check.

## reference/analysis-tools.md
Contains tools that are used to analyze the project structure and code.
Tools available:
- `analyze_calls`
- `build_project`
- `get_file_problems`
- `get_project_dependencies`
- `get_project_modules`
- `lint_files`

## reference/code-insight-tools.md
- `get_symbol_info`

## reference/database-tools.md
Database tools to interact with the database of a project.
Only use this with permission as the tools could cause data loss.

## reference/debugger-tools.md
Tools to help read and manipulate an active debugger session. Only use when
told that an active debugger session exists.

## reference/execution-tools.md
Tools to run different run configurations. Use this only when the user 
has asked to use run configurations.
- `execute_run_configuration`
- `get_run_configurations`

## reference/file-tools.md
- `create_new_file`
- `get_all_open_file_paths`
- `list_directory_tree`
- `open_file_in_editor`

## reference/formatting-tools.md
- `reformat_file`

## reference/read-tools.md
- `read_file`

## reference/refactoring-tools.md
- `rename_refactoring`

## reference/search-tools.md
- `search_file`
- `search_regex`
- `search_symbol`
- `search_text`

## reference/terminal-tools.md
- `execute_terminal_command`
