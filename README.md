# log-report (fixed)

A small [Harbor](https://github.com/laude-institute/harbor) benchmark task: parse an Apache-style access log and write a JSON summary (request count, unique clients, most popular paths).

This is the corrected version of the original `dynamo/log-report` task.

```
environment/   Dockerfile, access.log, solution_hint.py
solution/      reference solution (solve.py / solve.sh)
tests/         pytest verifier (test_outputs.py, test.sh)
task.toml      task metadata and limits
instruction.md what the agent is told
```

## Run the tests against the reference solution

```bash
docker build -t log-report environment
docker run --rm -v "$PWD/solution:/solution" -v "$PWD/tests:/tests" log-report \
  bash -c "bash /solution/solve.sh && bash /tests/test.sh"
```
