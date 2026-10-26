---
name: playwright-doctrine
description: Playwright framework doctrine for page objects, fixtures, and specs. Use when writing or reviewing a Playwright test, page object, fixture, or playwright.config.ts project.
disable-model-invocation: true
---

# Playwright doctrine

When the task drives a live browser flow, read `../playwright-golden/SKILL.md` and follow it.

## First increment

Make one Chrome project run one smoke test through a native fixture before you add another browser, Electron, OpenFin, or a second design. Do not spawn a child agent to compare architectures.

A saved storage file is not a fresh login. A UUID from a protected endpoint is not an account binding. Prove a fresh login and bind the account to the subject before you trust cached state.

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

## Status

A comment does not change the run.

- A failing test that should report when it starts passing is `test.fail`, with an annotation that names the issue.
- A blocked test is `test.fixme`, with a reason.
- A test that does not apply on one setup is `test.skip` with a platform condition and a reason.
- A slow test is `test.slow`.
- A known flake is the tag `@flaky`. The gate command passes `--grep-invert @flaky`. A separate command runs only that tag.

## Hosts and accounts

Platform differences go through a port the fixture injects. A page does not branch on `browserName`.

Electron and OpenFin launch only inside host fixtures. Live authoring uses web Chrome until those hosts are qualified.

Do not list the golden project as a dependency of the other projects.

Give each setup that writes server state its own account. A PWX session name is not an account lock. `browser close` and `pwx stop` do not prove the server released the account. `pwx stop` must not tear down a Workspace session the operator owns.
