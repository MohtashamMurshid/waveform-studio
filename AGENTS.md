# AGENTS.md

## Cursor Cloud specific instructions

**Waveform Studio** is a client-side-only Next.js 16 application (no backend, no database, no external services). The only service to run is the Next.js dev server.

### Quick reference

| Task | Command |
|------|---------|
| Install deps | `npm install` |
| Dev server | `npm run dev` (serves on `localhost:3000`) |
| Lint | `npm run lint` |
| Build | `npm run build` |

### Notes

- `react-resizable-panels` is a required dependency used by `components/ui/resizable.tsx`. It was missing from `package.json` but is present in `package-lock.json` after initial install. If you see a "Module not found: Can't resolve 'react-resizable-panels'" error during build, run `npm install react-resizable-panels`.
- The app is entirely client-side; all DSP processing runs in the browser. There are no API routes, environment variables, or secrets required.
- Two routes exist: `/` (landing page) and `/studio` (the main workbench).
- To test the studio, import any raw unsigned 8-bit `.bin` file (each byte is a waveform sample). The app defaults to 8000 Hz sample rate.
