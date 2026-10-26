---
name: playwright-golden
description: Drive one Playwright business flow on a connected PWX session. Use when authoring or repairing a live flow with project page objects and the project expect.
disable-model-invocation: true
---

# Golden flow

Use connected eval --file for project POMs and project expect.

Explicitly enable native tracing. This installed PWX start adds --trace=off, so pass -- --trace=on.

Preserve the failed receipt and inspect the same owned page before teardown.

Do not replay the failed flow or restart the session to obtain evidence.

After inspection, explicitly stop the owned host and retain the native assertion trace.

Keep the original flow failed even when inspection and cleanup succeed.

Do not add expect to run-code, named-step resume, or an OpenFin launcher.

The probe used the unauthenticated Workspace login page. It does not qualify authenticated-shell behavior, crashes, arbitrary timeouts, or trace export while keeping the host running.

## Command

Start the owned connected session with `-- --trace=on`.

```bash
pwx --cwd "<project>" eval --file "<flow>" -s <session> --owner <owner> --json
```

The eval file imports the project's page objects and expect. It is not a `run-code` function expression.

On failure, keep the receipt. Inspect with a new eval on that same session. Then stop the owned host.

```bash
pwx --cwd "<project>" stop -s <session> --owner <owner>
```

The trace ZIP from that stop is the evidence. `retain-on-failure` does not keep it, because the hosting test can still pass.
