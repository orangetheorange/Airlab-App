## Website status: 
[![Better Stack Badge](https://uptime.betterstack.com/status-badges/v3/monitor/2kusj.svg)](https://uptime.betterstack.com/?utm_source=status_badge)




# AirLab — Closed Alpha

<img width="1935" height="813" alt="image" src="https://github.com/user-attachments/assets/4a804369-b039-4298-8837-b1091963ced2" />

#
🌐 **Live app:** [www.air-lab.app](https://www.air-lab.app)
💻 **Source:** [github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App)
📧 **Support:** support.airlab@gmail.com

---


## Special Thanks

### Special thanks to team-selected testers:
- [@MrCohen](https://github.com/MrCohen)
- [@comPY-V2](https://github.com/comPY-V2)
- [@Jolyne_xoxo](https://github.com/Jolyne_xoxo)
- [@colinnt](https://github.com/colinnt)
- [@bill090](https://github.com/bill090)

### Thank you for submitting feedbacks to initialize this project


## What is AirLab?

AirLab is a collaborative study-notes platform built for students, study groups, and classrooms. The centerpiece is the **Space** — a free-form canvas where you arrange notes, PDFs, web pages, AI chats, flashcard decks, and quick tools side-by-side, like a study desk you don't have to clean. Around that sit the things you'd expect from a study app: workspaces, organizations, real-time group chat, and an autonomous AI agent that can build a whole notebook + flashcards + quiz from one prompt.

The app lives at **[www.air-lab.app](https://www.air-lab.app)**. The codebase is open and lives at **[github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App)**.

## Status: Closed Alpha

AirLab is currently in **closed alpha** — invite-only access for a small cohort of testers. Only emails on the alpha allowlist can sign up. If you're reading this and want to participate, request access at the email below; we add new testers in batches as we stabilize the feature surface.

During the alpha:

- Every workspace gets full **PRO-tier** access. Billing is intentionally disabled while we iterate.
- The **AI study companion** is wired up but held back behind a flag. We'll switch it on once we're confident in cost and quality controls.
- **AirLab Agent** (autonomous research → notebook + flashcards + quiz) is admin-only while we cover compute costs. It opens to every alpha tester once our [Buy Me a Coffee fundraiser](https://buymeacoffee.com/airlab) hits its $5,000 goal.
- **Translation** is built but disabled in the UI for the same cost reason.
- Data lives in a managed Postgres database hosted on DigitalOcean. Notes, spaces, workspaces, organizations, and chat history persist across deploys.

⚠️ Disclaimer ⚠️

The purpose of closed alpha is to debug and improve the application, not to experience pro features for free, the tester needs to actively debug and submit feedback / suggestions through the support page in the app. If a tester does not submit any feedback or comments within a period of time, he will be removed from the tester list.

## Features

### Spaces — your study desk
- A **Space** is a single full-viewport canvas where you arrange floating windows however you want. Drag, resize, minimize, stack — like a desktop, not a list.
- One workspace can hold many spaces (think one per class, project, or exam).
- **Node types** you can drop on a canvas:
  - **Note** — full rich-text editor.
  - **Markdown** — live markdown notepad.
  - **Web** — embed any URL as a live iframe.
  - **Image** — display an image from a URL.
  - **PDF** — embed a PDF document. *(PRO)*
  - **AI Chat** — conversational AI tutor pinned to the canvas. *(PRO)*
  - **Quiz** — auto-generated practice questions. *(PRO)*
  - **Flashcards** — spaced-repetition card deck. *(PRO)*
- The toolbar also exposes ephemeral **tools** (calculator, translator) — they live as floating windows for the session and aren't saved with the space.

### Notes
- Full rich text editor (headings, lists, code blocks, blockquotes, links).
- Organized by **subject** within a **workspace** — every note belongs to a workspace and optionally a subject.
- **Visibility** controls per note: private to you, shared with the workspace, or open to anyone with the share link.
- Markdown export for every note.
- Notes can live as a Space node *or* be opened standalone — the editor surface is the same.

### AirLab Agent
- A standalone page that takes one prompt and runs an autonomous study agent (LangChain DeepAgents). It plans, researches the web, drafts a notebook, extracts a flashcard deck, and generates a quiz.
- Pick a mission template (research a topic, build a flashcard deck, plan an exam, generate a quiz) or write your own.
- The plan + tool calls + outputs stream into a run log so you can see what the agent did.
- **Currently admin-only.** Non-admins see a fundraiser panel — once we hit the [Buy Me a Coffee goal](https://buymeacoffee.com/airlab), the gate flips for every alpha tester.

### AI assistant + credits
- Per-prompt AI assistant for quick rewrites, summaries, and Q&A — separate from the Agent (which runs longer multi-step missions).
- Each workspace has an **AI credit balance**. Models are priced per call:
  - **Haiku 4.5** — 1 credit. Fast & cheap; short answers and quick rewrites.
  - **Sonnet 4.6** — 10 credits. Balanced; the default for most study tasks.
  - **Opus 4.7** — 50 credits. Deepest reasoning; use when you need it.
- AI features are gated by a global flag during alpha — when it's off you'll see a "temporarily disabled" message instead of a response.

### Workspaces & Organizations
- A **workspace** is one notebook with its own notes, subjects, spaces, and chat. PRO-tier supports up to 5 workspaces, 5,000 notes per workspace, and 200 subjects per workspace.
- An **organization** groups testers — your school, study group, or club. Workspace invites are restricted to people you share an organization with.
- Invitations require explicit accept/decline. You'll see pending invites prominently when you visit the Organizations or Workspaces page; the invitee can accept or decline before any membership becomes active.
- Quick **switch workspace** from the profile dropdown.

### Group chat
- Each workspace has its own real-time group chat. Members get bell-icon notifications when there's a new message.
- Messages render with avatars, timestamps, and bubble layout.

### Account & profile
- **Account settings** page with display-name, username, and avatar upload (avatars are stored on Appwrite Storage; the rest lives in Postgres).
- **Language settings** — pick the UI language; native names show alongside English so you don't have to guess.
- Profile dropdown collects: profile, workspace settings, language, switch workspace, manage subscription, contact support, sign out.

### Other
- **Floating feedback button** — bug-icon FAB pinned to the corner of every page. One click opens a typed feedback dialog (bug / feature / question) and forwards you to a pre-filled GitHub issue. Admins can hide the button from the admin console.
- **Contact support** still available from the profile dropdown if you'd rather email than file an issue.
- **Dark mode** with smooth transitions; the rich-text editor surface is always light for legibility.
- Mobile-responsive throughout.

## For Testers

### Getting started

1. Make sure your email is on the alpha allowlist. (If you got an invitation email from us, you are.)
2. Open **[www.air-lab.app](https://www.air-lab.app)**.
3. Click **Get started** and sign up with the email address you were invited under. The signup form will reject any other email.
4. AirLab creates a default personal organization and workspace for you. You can rename them, create more, or accept invites from other testers.

### What to test (in priority order)

1. **Spaces** — Create a space, drop several node types onto it (Note, Markdown, Web, Image), drag them around, resize, minimize, close. Reload the page and confirm node positions/sizes/z-order persisted. Create a second space and confirm spaces are isolated.
2. **Notes inside and outside a space** — Create a Note node on a canvas *and* open the standalone editor. Confirm rich-text formatting, subject assignment, share link, and markdown export all still work in both contexts.
3. **Invitations** — Invite another tester to your organization, then to a workspace. Confirm both directions: accepting and declining. Confirm that workspace invites only show your organization's members in the picker.
4. **Group chat** — Send messages back and forth between two browsers. Confirm Enter sends, Shift+Enter inserts a newline, and bell badges update.
5. **Account settings** — Upload an avatar (verify it shows in nav + chat + space cards), edit display name + username, change UI language.
6. **Switch workspace** flow — Create a second workspace, switch via the profile dropdown, confirm spaces / notes / chat are scoped per workspace.
7. **Feedback button** — Click the bug FAB in the corner, fill in the dialog, confirm it forwards to a pre-filled GitHub issue.
8. **Edge cases** — Try unusual usernames (special characters, very long), oversized notes (10,000 characters), rapid switching between workspaces, dropping 10+ nodes on one space.

### Reporting issues

Easiest: hit the **bug-shaped feedback button** floating in the corner of every page. Pick a type (bug / feature / question / other), describe what you saw, and submit — it'll open a pre-filled GitHub issue page in a new tab.

You can also use the profile avatar (left-bottom) → **Contact support** if you'd rather email; that opens an email pre-filled with a bug-report template. Replies usually come within a day or two during alpha hours.

If neither is loading or you're locked out: email **support.airlab@gmail.com** directly.

Or, submit a new Issue to this repository: https://github.com/orangetheorange/Airlab-App/issues/new

### What not to test

- Payment / upgrade flows — disabled during alpha; every workspace is treated as PRO.
- AI prompts — the AI panel is visible but the engine is held back; expect a "temporarily disabled" message.
- AirLab Agent — admin-only until the Buy Me a Coffee fundraiser hits its goal. Non-admins will see the fundraiser panel instead of the agent UI; that's expected.
- Translation — same as AI; deliberately off.

## Roadmap

| Phase           | What ships                                                                 |
|-----------------|----------------------------------------------------------------------------|
| **Closed alpha** *(now)* | Spaces canvas + node types, notes, subjects, workspaces, organizations, invitations, chat, sharing, feedback button |
| Closed alpha + | AirLab Agent opens to all alpha testers (after BMC fundraiser goal); AI assistant turned on under credit balance |
| Open beta       | Translation, payment + plan tiers, full PDF / quiz / flashcard nodes for everyone |
| GA              | Mobile apps, classroom-wide dashboards, school-tier billing               |

## Tech stack

- **Backend:** Spring Boot 4 + Spring Security on Java 21
- **Frontend:** Vaadin Flow 25 (server-side Java + Web Components)
- **Auth:** Appwrite (REST API for password + email-link sign-in)
- **Database:** PostgreSQL (managed by DigitalOcean)
- **Hosting:** DigitalOcean App Platform
- **AI:** OpenAI-compatible chat-completions endpoint for the assistant; LangChain DeepAgents for AirLab Agent. Both are gated behind feature flags during alpha.

The full source — including the build pipeline, JPA entities, and frontend bundle config — is at [github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App).

## Privacy & data handling

During closed alpha:

- Email addresses, usernames, and avatar uploads are stored to identify you across sessions. Avatars sit on Appwrite Storage; everything else is in Postgres.
- Notes, subjects, spaces, space nodes, workspaces, and chat messages are stored with the user account that created them.
- Feedback submitted via the in-app button is forwarded to a pre-filled GitHub issue — only the text *you* type into the dialog is sent, and only when you click submit.
- We do not sell, share, or analyze your notes for advertising purposes.
- Authentication is handled by Appwrite Cloud; their infrastructure receives your email and password.
- The AI panel and Agent are currently gated; when enabled, your prompt + relevant note/space context are sent to the configured OpenAI-compatible endpoint (assistant) or LangChain DeepAgents runtime (agent) to generate responses.
- You can request full deletion of your account and all associated data by emailing **support.airlab@gmail.com**.

A formal Privacy Policy and Terms of Service will publish before open beta.

## License

Closed alpha access is granted under a tester agreement. The source repository's licensing is documented at [github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App).

---

**Questions, bugs, ideas?** Email **support.airlab@gmail.com** or use **Contact support** in the app.
