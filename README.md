# qe

Copilot plugin for QE work. This version creates and continues Playwright frameworks. Later skills will cover the path from a Jira item through acceptance, a manual run, a regression update, automation, and merge.

## Mount a session

```bash
copilot --plugin-dir <path-to-this-repo> --agent qe:author
```

The agent reads `skills/playwright-session/SKILL.md` from that folder. That flow reads `skills/playwright-doctrine/SKILL.md`. A live browser flow then follows `skills/playwright-golden/SKILL.md`.

A lasting install uses `copilot plugin install dotts-h/copilot-qe`. After that install, the agent id is still `qe:author`.

## Skills in the Copilot app

Select `qe:author` for the session. The skills set `disable-model-invocation` to true, so the model skill tool can return not found. Whether Copilot Desktop 1.1.32 hides them in the skill menu was not reproduced. The agent still reads the files by path. Leave the flag in place.

## License

MIT
