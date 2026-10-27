---
name: playwright-doctrine
description: Playwright framework doctrine for page objects, fixtures, and specs. Use when writing or reviewing a Playwright test, page object, fixture, or playwright.config.ts project.
disable-model-invocation: true
---

# Playwright doctrine

When the task drives a live browser flow, read `../playwright-golden/SKILL.md` and follow it.

## First increment

Make one Chrome project run one smoke test through a native fixture before you add another browser, Electron, OpenFin, or a second design. Do not spawn a child agent to compare architectures.

After that smoke passes, add the other accepted web projects in the same Playwright process. A desktop project stays blocked until that native runtime passes fresh authentication, the expected subject, shell readiness, the shared component contracts, a repeat run, and ownership-scoped teardown.

The ordinary command runs the verified web projects. A separate command runs the full matrix. A blocked desktop result stays a failure with its reason. Do not report it as a skip, a `test.fixme`, or a pass.

Do not rewrite the framework to add folders. Move a module only after the test that protects that behavior exists.

## Authentication state

A saved storage file is not a fresh login. A UUID from a protected endpoint is not an account binding. Prove a fresh login and bind the account to the subject before you trust cached state.

Keep a fresh-login smoke for each provider and runtime. After that binding exists, qualify restored state for one provider and one runtime at a time. Close the original browser. Open a new context with that state. Read the protected subject and the shell without typing a password. Accept or reject that pair on its own.

A miss or an expiry stays visible. Do not sign in again during an application test. Do not move state between Chrome and WebKit, or onto Electron or OpenFin. Keep the candidate in memory for the run.

Keep the two approved accounts. Tests that share a provider account run one at a time.

Do not pass a password or token as a command argument. Do not write those values, cookie headers, or raw page snapshots into the reply or a log.

After you choose a Playwright version, write that version into every brief you still follow.

## Layout

One project in `playwright.config.ts` is one setup. Specs do not call `test.use`.

Specs import `test` and `expect` only from the project's test module. A spec calls a fixture flow and a business expect. A spec does not take `page`, `context`, or `browser`. A spec does not call `getBy`, click, or wait.

Page objects live under `pages/`. A page imports only the directory one level under it, and files under `parts/`. Files under `parts/` import no page. A flow that uses two branches lives in a fixture.

Custom matchers are `expect.extend` in the project's expect module. Do not import `expect` from `@playwright/test` in any other file.

## Page methods

A page object is stateless. Assign locator fields in the constructor only.

A method that acts ends in one awaited hard expect. A second legal outcome is a second method. Do not use `expect.soft` in a page.

Locator order is `getByRole`, `getByText`, `getByLabel`, `getByPlaceholder`, `getByAltText`, `getByTitle`, then `getByTestId`. Do not use a CSS or XPath locator.

A documented main-frame handler that dismisses an overlay stays until a narrower handler passes on the same race.

## Status

A comment does not change the run.

- A failing test that should report when it starts passing is `test.fail`, with an annotation that names the issue.
- A test that cannot run yet, outside the full-matrix desktop projects, is `test.fixme`, with a reason.
- A test that does not apply on one setup is `test.skip` with a platform condition and a reason.
- A slow test is `test.slow`.
- A known flake is the tag `@flaky`. The gate command passes `--grep-invert @flaky`. A separate command runs only that tag.

## Hosts and accounts

Platform differences go through a port the fixture injects. A page does not branch on `browserName`.

Electron and OpenFin launch only inside host fixtures. Author a new flow on a verified web project until the desktop checklist above passes.

Do not invent an application switch. `--remote-debugging-port` does not select a Workspace profile. Do not run an installed runtime binary with `--help` to discover switches. Do not edit a signed or licensed manifest to force a port. Do not attach to a port this run does not own. Do not kill a shared runtime to close one application.

Read the installed app before you call a desktop flag unknown. For Electron, follow the bootstrap imports, the argument parser, and the packaged config. For OpenFin, read the manifest, then the installed runtime and the app files that consume those fields.

A value in the manifest or the app is a candidate. Label it as documented, seen in the installed app, verified on a live launch, or rejected. Infer a value only from one of those sources. A manifest field is not a launch fact until the app reads it.

If the required value is still missing, ask the operator and name the missing value. Do not close the desktop pass while an installed file that can hold the flag is unread, or while that question is unasked. Absence of a string in one binary does not prove the switch is unsupported.

Do not list the golden project as a dependency of the other projects.

A PWX session name is not an account lock. `browser close` and `pwx stop` do not prove the server released the account. `pwx stop` must not tear down a Workspace session the operator owns.

## Contracts

A foundation test passes with synthetic accounts and a temporary lock directory. It does not read the real `.env` or the home-directory locks.

Test a pure rule with a unit test. Test HTTP, files, and locks against a controlled stand-in. Test an observed shell action with an end-to-end spec. Do not add a test that only checks a mocked click.

Record identity and readiness once at the boundary that owns them. A later test calls an explicit recheck.
