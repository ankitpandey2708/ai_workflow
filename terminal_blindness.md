---
description: "SAFE MODE: Run any terminal command on Windows to ensure output visibility"
---

# Windows Safe Run Protocol

Use this workflow for ALL shell commands on Windows to avoid "terminal blindness" (empty output).
This applies to `npm`, `npx`, `yarn`, `git` (if verbose), and any long-running process.

## 1. Start Interactive Shell
Start a persistent background `cmd.exe` process.
*   **Command**: `cmd`
*   **Wait**: `500ms`
*   **Safe**: `true`

```javascript
run_command(CommandLine="cmd", Cwd="<working_directory>", WaitMsBeforeAsync=500, SafeToAutoRun=true)
```

## 2. Execute Command
Send your actual command string to the running shell.
*   **Input**: The command you want to run (e.g., `npm install`, `npx ...`).
*   **Wait**: `1000ms` (or more for long tasks)

```javascript
// turbo
send_command_input(CommandId="<ProcessID_from_step_1>", Input="<YOUR_COMMAND_HERE>", SafeToAutoRun=true, WaitMs=1000)
```

## 3. Monitor & Verify
Check the status to read the output.
*   Repeat this step if the command is still running.

```javascript
command_status(CommandId="<ProcessID_from_step_1>", WaitDurationSeconds=5)
```

## 4. Terminate Shell
When the task is complete, close the shell to free resources.

```javascript
send_command_input(CommandId="<ProcessID_from_step_1>", Terminate=true)
```
