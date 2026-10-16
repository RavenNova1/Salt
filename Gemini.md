# salt.md
Go backend (server/) + React/Vite/BlockNote frontend (web/), embedded via go:embed.
Dev: backend `$env:DATA="./data"; go run .` (:8420); frontend `cd web && npm run dev`.
Before finishing any task: `cd web && npm run check` and `go test ./...`.
Known Windows-only false failures (do not "fix" them): check-i18n.mjs reports
Intl violations in format.ts/i18n.ts, and server/language_test.go fails on path
separators. Run the other check scripts individually to confirm everything else.
Rules: every UI string uses t('...') and must exist in locales/de.json and es.json;
no Intl/toLocale*/localeCompare outside format.ts and i18n.ts; all code and
comments in English; multilingual search aliases need `// i18n-ok: <reason>`.
Slash commands live in getSlashItems in web/src/components/Editor.tsx.
Do not edit web/scripts/ or generated files without asking.