# Claude Code instructions — GameBridge

## Product intent
Build a free, local-first Windows desktop app that helps the user inspect their existing Steam library without downloading games. The user's machine has limited SSD capacity, so never propose installing games as a prerequisite.

## First task
Implement only the project foundation and Steam-library metadata layer. Do not implement Discord automation.

### Requirements
- Python 3.12+, PySide6, SQLite, httpx, pytest.
- Clean modular structure under src/gamebridge/.
- Read configuration from environment variables or a local ignored .env; include .env.example with placeholders only.
- Never log secrets.
- Steam integration must be read-only and use documented Steam Web API endpoints.
- Support a public Steam profile / SteamID64 and API key supplied locally by the user. Do not ask the user to paste secrets into chat.
- Fetch owned games and available metadata (AppID, name, playtime, optional image URL).
- Do not assume every owned game is currently installable or supported.
- Local install status is a separate Windows/Steam-library inspection feature; make it optional and explain its limitations.
- Cache results in SQLite and provide refresh/error states.
- Add unit tests with mocked HTTP responses. Tests must not require a real API key or network.
- Add a concise README setup guide and safe .gitignore.

### UI
Create a clean dark PySide6 shell with:
- sidebar: Dashboard, Steam Library, Settings;
- Steam Library table/list: game name, AppID, playtime, install status;
- search and filters;
- loading, empty, and error states.
Do not invent game records when API access is unavailable.

### Security and scope
Strictly prohibited:
- collecting, extracting, storing, or transmitting Discord tokens/cookies/session credentials;
- Discord client injection, Webpack/internal module access, private Discord endpoints, or synthetic telemetry;
- fake game processes or fabricated play sessions;
- claiming that Rich Presence equals badge progress.

A future Discord section may document public, supported integration capabilities and clearly distinguish them from badge eligibility. Do not implement badge farming.

### Workflow
1. Inspect repository before editing.
2. Propose a short implementation plan.
3. Implement the foundation and Steam metadata importer.
4. Run tests and report exact commands/results.
5. Summarize changed files, limitations, and next steps.
6. Do not commit secrets or generated personal library data.
