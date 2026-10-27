---
name: playwright-doctrine
description: Playwright framework doctrine for page objects, fixtures, and specs. Use when writing or reviewing a Playwright test, page object, fixture, or playwright.config.ts project.
disable-model-invocation: true
---

# Playwright doctrine

When the task drives a live browser flow, read `../playwright-golden/SKILL.md` and follow it.

The rules below apply to any product and any host. Specialize a rule only from evidence in the product in front of you. Do not copy a previous product's flags, accounts, or window names into a new target.

## Read the app

Before the first business assertion, map the running product in one pass. Name the outer host, the frame that owns the shell, the persistent chrome, and the area where a feature loads. Open one control in the area you were asked about and record where it lands. Same page, new route, dialog, or new page.

Use the accessible name the snapshot shows. Do not wait for a label you have not seen. Do not ask the operator to explain a control you have not opened.

After a click, the next observation is the destination. A new route is a state of that frame. It is not a missing frame. Do not continue a predicate on the parent after a new page has opened.

## First increment

Make one host run one smoke test through a native fixture before you add another host or a second design. Do not spawn a child agent to compare architectures.

After that smoke passes, add the other accepted hosts in the same process. An unqualified host stays blocked until that host passes fresh authentication, the expected identity, a ready application surface, the shared component contracts, a repeat run, and ownership-scoped teardown.

The ordinary command runs the verified hosts. A separate command runs the full matrix. A blocked host stays a failure with its reason. Do not report it as a skip, a `test.fixme`, or a pass.

Do not rewrite the framework to add folders. Move a module only after the test that protects that behavior exists.

## Authentication state

A saved storage file is not a fresh login. An identifier from a protected endpoint is not an account binding. Prove a fresh login and bind the account to that identity before you trust cached state.

Keep the sign-in principal, the application identity, the display name, and the contact email as separate fields. Assert that two of them are equal only after evidence for that provider shows the equality. A match on one provider does not establish the match on another.

After two failed checks of the same premise, write that premise down. The next action is one observation that could show the premise is false. Do not log in again, and do not patch the assertion, until that observation is recorded.

Keep a fresh-login smoke for each account provider and host. After that binding exists, qualify restored state for one provider and one host at a time. Close the original context. Open a new context with that state. Read the protected identity and the ready application surface without typing a password. Accept or reject that pair on its own.

A miss or an expiry stays visible. Do not sign in again during an application test. Do not move restored state from one host to another. Keep the candidate in memory for the run.

Use only the accounts the operator approved for this target. Tests that share an account run one at a time. Do not add an account to buy parallelism.

Do not pass a password or token as a command argument. Do not write those values, cookie headers, or raw page snapshots into the reply or a log.

After you choose a Playwright version, write that version into every brief you still follow.

## Authoring loop

Report authentication, identity, application checks, and cleanup as four separate outcomes. A passed hosting test does not pass a failed authoring check.

A setting that exists only in an authoring adapter is not part of the framework. Put it in the native config before a component uses it.

After you edit a class the held worker constructs, confirm the worker is running that edit. Restart the worker once when fixture setup must change. Do not discover the stale class through another business action. A selector failure is not a reason to start a new login.

## Layout

One project in `playwright.config.ts` is one setup. Specs do not call `test.use`.

Specs import `test` and `expect` only from the project's test module. A spec calls a fixture flow and a business expect. A spec does not take `page`, `context`, or `browser`. A spec does not call `getBy`, click, or wait.

Page objects live under `pages/`. A page imports only the directory one level under it, and files under `parts/`. Files under `parts/` import no page. A flow that uses two branches lives in a fixture.

Custom matchers are `expect.extend` in the project's expect module. Do not import `expect` from `@playwright/test` in any other file.

## Dig order

Look in this order. Use the first source that identifies the control.

1. List the frames. Act in the frame that owns the surface. Stop when that frame is detached.
2. Read the accessibility snapshot of that frame. Use roles, names, and states.
3. Use the locator order in Page methods, inside that frame. An open shadow root stays on that order.
4. Read a label, a placeholder, or a test id when the snapshot omitted it and the locator order allows it.
5. Read the network log and the console for a failure the tree does not show.
6. Take a screenshot only when the paint and the tree disagree, or the surface is a canvas. A screenshot is the last resort. Do not write a locator from it. Do not keep a picture of a login screen.

A closed shadow root, or a frame the browser will not expose, has no locator inside it. Use the outer control's accessible name, or ask the operator.

## Page methods

A page object is stateless. Assign locator fields in the constructor only.

A method that acts ends in one awaited hard expect. A second legal outcome is a second method. Do not use `expect.soft` in a page.

Locator order is `getByRole`, `getByText`, `getByLabel`, `getByPlaceholder`, `getByAltText`, `getByTitle`, then `getByTestId`. Do not use a CSS or XPath locator.

A documented handler that dismisses an overlay stays until a narrower handler passes on the same race.

## Status

A comment does not change the run.

- A failing test that should report when it starts passing is `test.fail`, with an annotation that names the issue.
- A test that cannot run yet, outside an unqualified host in the full matrix, is `test.fixme`, with a reason.
- A test that does not apply on one setup is `test.skip` with a platform condition and a reason.
- A slow test is `test.slow`.
- A known flake is the tag `@flaky`. The gate command passes `--grep-invert @flaky`. A separate command runs only that tag.

## Hosts and accounts

Platform differences go through a port the fixture injects. A page does not branch on the host name.

Use the host tool's launch path for a platform it already supports. Do not invent a second launcher. An unqualified host stays inside the host fixture. Author a new flow on a verified host until that host passes the checklist above.

When the generic launch does not supply a product-specific value, read that product. Start from the config it ships, then the installed files that consume the config. Follow imports, argument parsing, and packaged config until the value is found or the readable files are exhausted.

A value in a config file is a candidate. Label it as documented, seen in the installed product, verified on a live launch, or rejected. Infer a value only from one of those sources. A config field is not a launch fact until the product reads it.

Do not invent a switch. A generic runtime switch is not a product setting. Do not pass `--help` to a runtime binary when that starts the product. Do not edit a signed or licensed config to force a port. Do not attach to a port this run does not own. Do not kill a shared runtime to close one application.

If the required value is still missing, ask the operator and name the missing value. Do not close the pass while an installed file that can hold the value is unread, or while that question is unasked. Absence of a string in one file does not prove the switch is unsupported.

Do not list the golden project as a dependency of the other projects.

A host session name is not an account lock. Closing the browser or stopping the host does not prove the server released the account. Do not tear down a session the operator owns outside this run.

## Contracts

A foundation test passes with synthetic accounts and a temporary lock directory. It does not read the real environment file or the home-directory locks.

Test a pure rule with a unit test. Test HTTP, files, and locks against a controlled stand-in. Test an observed product action with an end-to-end spec. Do not add a test that only checks a mocked click.

Record identity and readiness once at the boundary that owns them. A later test calls an explicit recheck.
