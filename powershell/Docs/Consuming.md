# Consuming the SDK

## Dependencies
* The SDK requires PowerShell 3 or higher.
* The SDK is designed for use with PowerShell.exe (Console Host).

## Where to get it

```Batchfile
npm install vsts-task-sdk
```

or install a specific version:

```Batchfile
npm install vsts-task-sdk@0.5.0
```

## task.json modifications
Use the PowerShell3 execution handler and set the target to the entry PS1 script. The entry PS1 script should be located in the root of the task folder.
```JSON
{
    "execution": {
        "PowerShell3": {
            "target": "MyTask.ps1"
        },
    }
}
```

## Package the SDK with the task
The SDK should be packaged with the task in a ps_modules folder. The ps_modules folder should be in the root of the task folder.

Example layout: Consider the following layout where "MyTask" is the root folder for the task.
```
MyTask
|   MyTask.ps1
│   task.json
└───ps_modules
    └───VstsTaskSdk
            [...]
            VstsTaskSdk.psd1
```
