# File Tools

## create_new_file
Creates a new file at the specified path within the project directory. Automatically generates
parent directories and optionally writes initial content.

Parameters:
- `pathInProject` (string, required): Path relative to project root.
- `text` (string, optional): Content to write into new file.
- `overwrite` (boolean, optional): Overwrite existing file if true.
- `projectPath`

## get_all_open_file_paths
Returns the paths of all files opened for editing in the active editor or any other open editors.
Explores currently open editor contents.

Parameters:
- `projectPath`

## list_directory_tree
Provides a tree representation of the specified directory in the pseudo-graphic format, similar
to the tree utility. Explores directory and project contents hierarchically.

Parameters:
- `directoryPath` (string, required): Path relative to project root.
- `maxDepth` (integer, optional): Maximum recursion depth.
- `timeout` (integer, optional): Timeout in milliseconds.
- `projectPath`

## open_file_in_editor
Opens the specified file in the JetBrains IDE editor. Loads files for viewing or editing using
absolute or project-relative paths.

Parameters:
- `filePath` (string, required): Path relative to project root.
- `projectPath`
