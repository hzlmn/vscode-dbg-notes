### VSCode debugging

#### TypeScript

`launch.json`

```js
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Run", // just a debugging task name
            "type": "node", // define environment in which you want to debug
            "request": "launch",
            "program": "${workspaceRoot}/src/esprima.ts", // src to program
            "stopOnEntry": true,
            "args": [],
            "cwd": "${workspaceRoot}",
            "preLaunchTask": "compile",
            "runtimeExecutable": null,
            "runtimeArgs": [
                "--nolazy"
            ],
            "env": {
                "NODE_ENV": "development"
            },
            "console": "integratedTerminal",
            "sourceMaps": true  // if source maps define use them to debug
        }
    ]
}

```

`tasks.json`

```js
{
    "version": "0.1.0",
    "command": "npm",
    "isShellCommand": true,
    "showOutput": "always",
    "suppressTaskName": true,
    "tasks": [
        {
            "taskName": "install",
            "args": ["install"]
        },
        {
            "taskName": "update",
            "args": ["update"]
        },
        {
            "taskName": "test",
            "args": ["run", "test"]
        },
        {
            "taskName": "compile",
            "args": ["run", "compile"]
        }
    ]
}

```