# Execution Tools

## execute_run_configuration
Run either an existing run configuration by name or a temporary run configuration created from a
code location, then wait up to the specified timeout for it to finish.

Parameters:
- `configurationName` (string, optional): Name of existing run configuration.
- `filePath` (string, optional): File path relative to project root.
- `line` (integer, optional): 1-based line number for `filePath`.
- `timeout` (integer, optional): Timeout in milliseconds.
- `waitForExit` (boolean, optional): Whether to wait for process termination.
- `programArguments` (string, optional): Program arguments override for this launch.
- `workingDirectory` (string, optional): Working directory override for this launch.
- `envs` (object, optional): Environment variable overrides for this launch.
- `projectPath`

## get_run_configurations
Returns either project run configurations or executable code locations, depending on the input.
Discovers run points like test methods and entry points.

Parameters:
- `filePath` (string, optional): File path relative to project root.
- `projectPath`
