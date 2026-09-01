# Code Insight Tools

## get_symbol_info
Retrieves information about the symbol at the specified position in the specified file.

If the position references a symbol, the tool will return a code snippet with the symbol's 
declaration, if available.

The information may include the symbol's name, signature, type, documentation, 
and other details, depending on the programming language.

Parameters:
- `filePath` (string, required): Path relative to project root.
- `line` (integer, required): 1-based line number.
- `column` (integer, required): 1-based column number.
- `projectPath`
