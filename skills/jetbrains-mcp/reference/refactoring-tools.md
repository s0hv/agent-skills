# Refactoring Tools

## rename_refactoring
Renames a symbol (variable, function, class, etc.) in the specified file. Performs context-aware
refactoring updating all references intelligently throughout projects.

Parameters:
- `pathInProject` (string, required): Path relative to project root.
- `symbolName` (string, required): Name of symbol to rename.
- `newName` (string, required): New name for symbol.
- `projectPath`
