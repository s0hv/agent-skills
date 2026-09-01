# Analysis Tools

## analyze_calls
Builds the IDE Call Hierarchy tree for a method, function, constructor, or supported type target.
Examines incoming or outgoing call relationships using IDE data rather than text search for
improved precision.

Prefer this tool over usage search, text search, or regex search when evaluating dependencies 
by actual calls. It uses IDE call hierarchy data, so it provides more precise call relationships 
with less noise and fewer follow-up calls than primitive searches.

Parameters:
- `symbolFqn` (string, required): Plain fully qualified symbol name, or an exact signature returned by an ambiguity error.
Examples: `com.example.Service.run`, `com.example.Service.run(String)`
- `analysisKind` (string, required): Call direction — `INCOMING_CALLS` or `OUTGOING_CALLS`.
- `depth` (integer, optional): Maximum call levels to render; defaults to 5.
- `maxChildren` (integer, optional): Maximum direct children per node; defaults to 50.
- `maxNodes` (integer, optional): Maximum total rendered nodes; defaults to 1000.
- `treePath` (array, optional): Optional path to subtree root from previous results.
- `childOffset` (integer, optional): Offset for paging children; defaults to 0.
- `timeout` (integer, optional): Timeout in milliseconds.
- `projectPath`

## build_project
Triggers building of the project or specified files, waits for completion, and returns build
errors. Essential for validating code modifications through compilation.

Parameters:
- `rebuild` (boolean, optional): Whether to perform full rebuild; defaults to false.
- `filesToRebuild` (array, optional): Files to compile if specified.
- `timeout` (integer, optional): Timeout in milliseconds.
- `projectPath`

## get_file_problems
Analyzes the specified file for errors and warnings using IntelliJ inspections. Identifies syntax
issues and coding problems at the file level using IDE inspection capabilities.

Line and column numbers are 1-based.

Parameters:
- `filePath` (string, required): Path relative to project root.
- `errorsOnly` (boolean, optional): Include only errors or both errors and warnings.
- `timeout` (integer, optional): Timeout in milliseconds.
- `projectPath`

## get_project_dependencies
Returns a list of all dependencies defined in the project. Provides structured information about
library names and their relationships.

Parameters:
- `projectPath`

## get_project_modules
Returns a list of all modules in the project with their types. Delivers structured module
information including names and classifications.

Parameters:
- `projectPath`

## lint_files
Analyzes the specified files for errors and warnings using IntelliJ inspections. Processes
multiple files simultaneously, returning per-file problems with location data.

Parameters:
- `files` (array, required): List of project-relative files to analyze.
- `min_severity` (string, optional): Minimum severity — `warning` or `error`; defaults to `warning`.
- `timeout` (integer, optional): Timeout in milliseconds.
- `projectPath`
