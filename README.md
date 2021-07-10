# tkn-runner

Tekton Pipelines ClI plugin just running pipeline/task interactively.


Install
--------

Copy `tkn-runner` file under any $PATH directory. `chmod +x tkn-runner` is also needed.

To use tkn-runner, [tkn](https://github.com/tektoncd/cli) & [jq](https://stedolan.github.io/jq/) need to be installed.


Usage
--------

`tkn-runner` lists registered Pipelines from current namespace.  
Select a pipeline, then lists filtered PipelineRuns.  
After your selection, the pipeline will start.

```bash
$ tkn runner

1) pipeline-a
2) pipeline-b
Select Pipeline (or 'q' to quit)> 1

1) pipelinerun-a1
2) pipelinerun-a2
Select PipelineRun (or 'q' to quit)> 2
PipelineRun started: pipelinerun-a2-k72wz
```

If you want to run Task & TaskRun, use `-t` option.

```bash
$ tkn runner -t
```

Optionally, You can specify Pipeline/Task name.


FAQ
--------

* PipelineRun/TaskRun doesn't list.
  * `tkn runner` only lists which are created with `kubectl apply`. Duplicated PipelineRuns/TaskRuns will be filtered by design.
