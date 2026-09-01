# Read Tools

## read_file
Reads a file in the project directory or from any project dependency or other project source
root. Handles sources within Jar/Jrt files and decompiles Java classes with multiple read modes.

Parameters:
- `file_path` (string, required): Supports project-relative paths, paths with `..`, absolute paths, archive entries.
- `mode` (string, required): Read mode — `slice`, `lines`, `line_columns`, `offsets`, or `indentation`.
- `start_line` (integer, optional): 1-based line number to start reading.
- `max_lines` (integer, optional): Maximum lines to return.
- `end_line` (integer, optional): 1-based end line (inclusive for `lines` mode).
- `start_column` (integer, optional): 1-based start column for `line_columns` mode.
- `end_column` (integer, optional): 1-based end column (exclusive).
- `start_offset` (integer, optional): 0-based start offset for `offsets` mode.
- `end_offset` (integer, optional): 0-based end offset (exclusive).
- `context_lines` (integer, optional): Context lines around range.
- `max_levels` (integer, optional): Maximum indentation levels to include.
- `include_siblings` (boolean, optional): Include sibling blocks at same indentation.
- `include_header` (boolean, optional): Include header comments/annotations above anchor.
- `projectPath`
