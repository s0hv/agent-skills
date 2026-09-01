# Terminal Tools

## execute_terminal_command
Executes a specified shell command in the IDE's integrated terminal. Runs shell commands within
IDE environment with output limits and timeout handling.

Parameters:
- `command` (string, required): Shell command to execute.
- `executeInShell` (boolean, optional): Execute in default shell or as process.
- `reuseExistingTerminalWindow` (boolean, optional): Reuse existing terminal window.
- `timeout` (integer, optional): Timeout in milliseconds.
- `maxLinesCount` (integer, optional): Maximum lines to return.
- `truncateMode` (string, optional): How to truncate — from start, middle, end, or not at all.
- `projectPath`
