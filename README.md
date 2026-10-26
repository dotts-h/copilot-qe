# qe

Copilot plugin for QE work. This version covers Playwright framework doctrine. Later skills will cover the path from a Jira item through acceptance, a manual run, a regression update, automation, and merge.

## Mount a session

```bash
copilot --plugin-dir <path-to-this-repo> --agent qe:author
```

The agent reads `skills/playwright-doctrine/SKILL.md` from that folder. A live browser flow then follows `skills/playwright-golden/SKILL.md`.

A lasting install uses `copilot plugin install dotts-h/copilot-qe`. After that install, the agent id is still `qe:author`.

## License

MIT
