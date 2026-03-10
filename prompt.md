## Prompts I Used

### 1) Scoped markdown edit
- Mode: Agent
- Model: GPT-5.3 Codex (Auto)

Edit only this markdown file at `<absolute_note_path>`, apply my instructions directly to that file, and do not create, delete, rename, or modify any other files; I want a clean in-place edit with no side effects and no unrelated changes.

### 2) Full markdown rewrite output
- Mode: Agent
- Model: GPT-5.3 Codex (Auto)

You are acting as a markdown editor, so edit the note content according to my instructions and return only the complete final markdown with no explanations, no commentary, and no code fences, because I want output that can be written back to file directly.

### 3) Tauri command wiring
- Mode: Agent
- Model: GPT-5.3 Codex (Auto)

Add a new Tauri command in `src-tauri/src/lib.rs`, register it in `tauri::generate_handler!`, add or update the typed frontend wrapper in `src/services/notes.ts`, and wire the call in `src/context/NotesContext.tsx`; keep Rust error handling in `Result<..., String>` style, preserve existing markdown path validation behavior, and avoid touching unrelated commands.

### 4) Chat tool extension end-to-end
- Mode: Agent
- Model: GPT-5.3 Codex (Auto)

Extend chat tooling end-to-end across `workers/chat-agent/src/server.ts`, `src/components/chat/chat-tools.ts`, and `src/components/chat/ChatView.tsx` by adding a zod-typed tool contract, implementing handler logic, and rendering tool states correctly, while keeping full compatibility with `searchNotes`, `readNote`, and `proposeNoteEdit`.

### 5) Home ingestion pipeline refactor
- Mode: Agent
- Model: GPT-5.3 Codex (Auto)

Refactor URL and book ingestion across `src/components/home/HomePage.tsx`, `src/components/home/UrlInputModal.tsx`, `src/services/urlMetadata.ts`, and `src/context/NotesContext.tsx` if needed, with normalization of `title`, `author`, `publication`, `publishedAt`, and `coverUrl`, while preserving markdown metadata comments like `<!-- cover: ... -->` and `<!-- link: ... -->`, existing tags such as `#to-read` and `#technical`, and adding solid fallbacks for missing metadata.

### 6) Performance + type-safety cleanup
- Mode: Agent
- Model: GPT-5.3 Codex (Auto)

Refactor `src/components/command-palette/CommandPalette.tsx` and `src/components/editor/Editor.tsx` to reduce unnecessary rerenders and tighten TypeScript safety, keep imports at the top of each file, use exhaustive handling for unions or switches where relevant, and preserve all current keyboard shortcuts and UI behavior.

### 7) Chat system prompt hardening
- Mode: Agent
- Model: Opus 4.6

Update the system prompt in `workers/chat-agent/src/server.ts` so the assistant uses `searchNotes` before answering note-specific questions, uses `readNote` before detailed claims, uses `proposeNoteEdit` for edits without pretending edits were already applied, references note titles when helpful, and responds honestly when no results are found.

### 8) Release-readiness pass
- Mode: Plan
- Model: Opus 4.6

Create a release-readiness checklist and risk review for the current changes by checking frontend impact in `src/App.tsx`, `src/components/**`, and `src/services/**`, Rust impact in `src-tauri/src/lib.rs` and `src-tauri/Cargo.toml`, Tauri configuration in `src-tauri/tauri.conf.json`, and icon consistency in `src-tauri/icons/**`, then return blockers, high-risk areas, first files to patch, and verification commands.

### 9) Commit + remote sync execution
- Mode: Agent
- Model: GPT-5.3 Codex (Auto)

Initialize or verify repo state, stage the relevant changes, create a clean commit message, add the remote `https://github.com/Shayaan-Azeem/cf_ai_shayaan_azeem_think.git`, and push `main`, while not altering existing remotes unless required, and return the final commit hash plus remote tracking status.

