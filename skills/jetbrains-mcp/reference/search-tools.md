# Search Tools

## search_file
Searches for files by glob pattern within the project. Matches file paths using glob syntax
relative to project root.

Parameters:
- `q` (string, required): Glob pattern to search for.
- `paths` (array, optional): Project-relative glob patterns to filter results.
- `includeExcluded` (boolean, optional): Include excluded/ignored files.
- `limit` (integer, optional): Maximum results to return.
- `projectPath`

## search_regex
Searches for regex matches within project files. Performs pattern matching returning snippet
results with location coordinates.

Parameters:
- `q` (string, required): Regex pattern to search for.
- `paths` (array, optional): Project-relative glob patterns to filter results.
- `limit` (integer, optional): Maximum results to return.
- `projectPath`

## search_symbol
Searches for symbols (classes, methods, fields). Provides semantic identifier lookup with
optional SDK and library inclusion.

Parameters:
- `q` (string, required): Symbol query text.
- `paths` (array, optional): Project-relative glob patterns to filter results.
- `include_external` (boolean, optional): Include SDK and library symbols.
- `limit` (integer, optional): Maximum results to return.
- `projectPath`

## search_text
Searches for a text substring within project files. Executes fast text matching delivering
snippet results with position data.

Parameters:
- `q` (string, required): Text substring to search for.
- `paths` (array, optional): Project-relative glob patterns to filter results.
- `limit` (integer, optional): Maximum results to return.
- `projectPath`
