# Debugger Tools

## xdebug_control_session
Controls the execution of a debug session. Enables stepping, resuming, pausing, or stopping with
support for breakpoint management and event draining.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `action` (string, required): Action — `STEP_INTO`, `STEP_OVER`, `STEP_OUT`, `RESUME`, `PAUSE`, `STOP`, `WAIT_FOR_PAUSE`, `DRAIN_EVENTS`.
- `timeout` (integer, optional): Timeout in milliseconds; defaults to 30000.
- `eventsLimit` (integer, optional): Maximum latest events to drain; defaults to 100.
- `clearEventsAfterRead` (boolean, optional): Compatibility flag.
- `projectPath`

## xdebug_evaluate_expression
Evaluates an expression in the context of the current stack frame. Computes values, invokes
methods, or inspects expressions during active debugging.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `frameIndex` (integer, optional): Stack frame index; defaults to null (top frame).
- `expression` (string, required): Expression to evaluate in current context.
- `depth` (integer, optional): Maximum depth for expanding children; defaults to 0.
- `projectPath`

## xdebug_get_debugger_status
Returns the current status of the debugger including all active debug sessions. Provides overview
of running sessions and their operational states.

Parameters:
- `projectPath`

## xdebug_get_frame_values
Returns the values visible in the specified stack frame as a tree structure. Inspects local
variables, parameters, fields, and other accessible values.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `frameIndex` (integer, optional): Stack frame index; defaults to null (top frame).
- `depth` (integer, optional): Maximum depth for expanding children; defaults to 0.
- `projectPath`

## xdebug_get_stack
Returns the call stack for a thread in the debug session. Shows method invocation sequence
leading to current execution point.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `threadId` (string, optional): Thread ID to get stack for; defaults to null.
- `limit` (integer, optional): Maximum frames to return; defaults to 200.
- `offset` (integer, optional): Page offset; defaults to 0.
- `projectPath`

## xdebug_get_threads
Returns the list of threads in the debug session. Displays all threads with their current status
and stack information.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `limit` (integer, optional): Page size; defaults to 50, max 200.
- `offset` (integer, optional): Page offset; defaults to 0.
- `projectPath`

## xdebug_get_value_by_path
Gets the value of a nested object by following a path of property names. Drills into complex
objects inspecting nested properties systematically.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `frameIndex` (integer, optional): Stack frame index; defaults to null (top frame).
- `path` (array, required): List of child names to navigate through.
- `depth` (integer, optional): Maximum depth for expanding children; defaults to 0.
- `projectPath`

## xdebug_list_breakpoints
Lists all breakpoints in the project or in a specific file. Displays current breakpoint
configurations and their properties.

Parameters:
- `filePath` (string, optional): Optional file path to filter breakpoints.
- `projectPath`

## xdebug_remove_breakpoint
Removes breakpoints filtered by owner and optional selectors. Eliminates previously configured
breakpoints using various filter criteria.

Parameters:
- `breakpointId` (string, optional): Canonical breakpoint ID.
- `filePath` (string, optional): Optional file path to filter breakpoints.
- `line` (integer, optional): 1-based line number.
- `owner` (string, optional): Breakpoint owner filter; defaults to agent.
- `projectPath`

## xdebug_run_to_line
Resumes execution to a target line. Runs until reaching a specific source position without manual
stepping.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `filePath` (string, required): Path relative to project root.
- `line` (integer, required): Target line number (1-based).
- `timeout` (integer, optional): Timeout waiting for result; defaults to 30000.
- `projectPath`

## xdebug_set_breakpoint
Creates or updates a breakpoint. Establishes line breakpoints and configures tracepoint/logging
behavior.

Parameters:
- `breakpointId` (string, optional): Canonical breakpoint ID for update mode.
- `filePath` (string, optional): Path relative to project root.
- `line` (integer, optional): 1-based line number; required in location mode.
- `condition` (string, optional): Optional condition expression; defaults to null.
- `isLogMessage` (boolean, optional): Log breakpoint hit position; defaults to false.
- `isLogStack` (boolean, optional): Log stack trace on hit; defaults to false.
- `temporary` (boolean, optional): Remove after first hit; defaults to false.
- `suspendPolicy` (string, optional): Suspend policy — `ALL`, `THREAD`, `NONE`; defaults to `ALL`.
- `enabled` (boolean, optional): Whether breakpoint is enabled; defaults to true.
- `projectPath`

## xdebug_set_variable
Mutates a variable value by path in the selected stack frame. Changes state during debugging
sessions.

Parameters:
- `sessionId` (string, optional): Debug session ID; defaults to null.
- `frameIndex` (integer, optional): Stack frame index; defaults to null (top frame).
- `path` (array, required): Path to target value, same format as `xdebug_get_value_by_path`.
- `newValue` (string, required): New value expression to assign.
- `projectPath`

## xdebug_start_debugger_session
Start a debugger session for either an existing run configuration by name or a code location.
Initiates debugging with optional launch overrides.

Parameters:
- `configurationName` (string, optional): Name of existing run configuration.
- `filePath` (string, optional): File path relative to project root.
- `line` (integer, optional): 1-based line number for `filePath`.
- `timeout` (integer, optional): Timeout waiting for session start; defaults to 60000.
- `graceWaitMs` (integer, optional): Grace wait after session starts; defaults to 2000.
- `programArguments` (string, optional): Program arguments override for this launch.
- `workingDirectory` (string, optional): Working directory override for this launch.
- `envs` (object, optional): Environment variable overrides for this launch.
- `projectPath`
