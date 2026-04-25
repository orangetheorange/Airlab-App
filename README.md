# AirLab — Closed Alpha

> The fastest way for students to write, share, and study notes — together.

🌐 **Live app:** [www.air-lab.app](https://www.air-lab.app)
💻 **Source:** [github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App)
📧 **Support:** support.airlab@gmail.com

---


# Special Thanks

### Special thanks to team-selected testers:

@MrCohen

@comPY-V2

@Jolyne_xoxo

@colinnt

### Thank you for submitting feedbacks to initialize this project


## What is AirLab?

AirLab is a collaborative study-notes platform built for students, study groups, and classrooms. Think of it as a shared notebook with rich text, organized subjects, real-time group chat, and an AI study companion — all designed around the way real classes actually work.

The app lives at **[www.air-lab.app](https://www.air-lab.app)**. The codebase is open and lives at **[github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App)**.

## Status: Closed Alpha

AirLab is currently in **closed alpha** — invite-only access for a small cohort of testers. Only emails on the alpha allowlist can sign up. If you're reading this and want to participate, request access at the email below; we add new testers in batches as we stabilize the feature surface.

During the alpha:

- Every workspace gets full **PRO-tier** access. Billing is intentionally disabled while we iterate.
- The **AI study companion** is wired up but held back behind a flag. We'll switch it on once we're confident in cost and quality controls.
- **Translation** is built but disabled in the UI for the same reason.
- Data lives in a managed Postgres database hosted on DigitalOcean. Notes, workspaces, organizations, and chat history persist across deploys.

⚠️ Disclaimer ⚠️

The purpose of closed alpha is to debug and improve the application, not to experience pro features for free, the tester needs to actively debug and submit feedback / suggestions through the support page in the app. If a tester does not submit any feedback or comments within a period of time, he will be removed from the tester list. 

## Features

### Notes
- Full rich text editor (headings, lists, code blocks, blockquotes, links).
- Organized by **subject** within a **workspace** — every note belongs to a workspace and optionally a subject.
- **Visibility** controls per note: private to you, shared with the workspace, or open to anyone with the share link.
- Markdown export for every note.

### Workspaces & Organizations
- A **workspace** is one notebook with its own notes, subjects, and chat. PRO-tier supports up to 5 workspaces, 5,000 notes per workspace, and 200 subjects per workspace.
- An **organization** groups testers — your school, study group, or club. Workspace invites are restricted to people you share an organization with.
- Invitations require explicit accept/decline. You'll see pending invites prominently when you visit the Organizations or Workspaces page; the invitee can accept or decline before any membership becomes active.

### Group chat
- Each workspace has its own real-time group chat. Members get bell-icon notifications when there's a new message.
- Messages render with avatars, timestamps, and bubble layout.

### Other
- Tools tab includes a **calculator** and **translator** scaffold.
- Profile dropdown has a **Contact support** action that pre-fills a bug-report email.
- **Dark mode** with smooth transitions; the rich-text editor surface is always light for legibility.
- Mobile-responsive throughout.

## For Testers

### Getting started

1. Make sure your email is on the alpha allowlist. (If you got an invitation email from us, you are.)
2. Open **[www.air-lab.app](https://www.air-lab.app)**.
3. Click **Get started** and sign up with the email address you were invited under. The signup form will reject any other email.
4. AirLab creates a default personal organization and workspace for you. You can rename them, create more, or accept invites from other testers.

### What to test (in priority order)

1. **Notes flow** — Create a note, add some rich text, add a subject, share via link, edit, export to markdown. The note editor lives at `/notes/editor` (opens in a new tab from the Notes view).
2. **Invitations** — Invite another tester to your organization, then to a workspace. Confirm both directions: accepting and declining. Confirm that workspace invites only show your organization's members in the picker.
3. **Group chat** — Send messages back and forth between two browsers. Confirm Enter sends, Shift+Enter inserts a newline, and bell badges update.
4. **Subjects** — Create subjects, file notes under them, filter the Notes view by subject.
5. **Edge cases** — Try unusual usernames (special characters, very long), oversized notes (10,000 characters), rapid switching between workspaces.

### Reporting issues

Hit the profile avatar (left-bottom) → **Contact support**. That opens an email pre-filled with a bug-report template; just fill in what you were doing, what happened, and what you expected. Replies usually come within a day or two during alpha hours.

If support isn't loading or you're locked out: email **support.airlab@gmail.com** directly.

Or, submit a new Issue to this repository: https://github.com/orangetheorange/Airlab-App/issues/new

### What not to test

- Payment / upgrade flows — disabled during alpha; every workspace is treated as PRO.
- AI prompts — the AI panel is visible but the engine is held back; expect a "temporarily disabled" message.
- Translation — same as AI; deliberately off.

## Roadmap

| Phase           | What ships                                                                 |
|-----------------|----------------------------------------------------------------------------|
| **Closed alpha** *(now)* | Notes, subjects, workspaces, organizations, invitations, chat, sharing |
| Open beta       | AI study companion turned on, translation, payment + plan tiers           |
| GA              | Mobile apps, classroom-wide dashboards, school-tier billing               |

## Tech stack

- **Backend:** Spring Boot 4 + Spring Security on Java 21
- **Frontend:** Vaadin Flow 25 (server-side Java + Web Components)
- **Auth:** Appwrite (REST API for password + email-link sign-in)
- **Database:** PostgreSQL (managed by DigitalOcean)
- **Hosting:** DigitalOcean App Platform
- **AI:** OpenAI-compatible chat-completions endpoint (gated behind a feature flag)

The full source — including the build pipeline, JPA entities, and frontend bundle config — is at [github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App).

## Privacy & data handling

During closed alpha:

- Email addresses, usernames, and avatar uploads are stored to identify you across sessions.
- Notes, subjects, workspaces, and chat messages are stored with the user account that created them.
- We do not sell, share, or analyze your notes for advertising purposes.
- Authentication is handled by Appwrite Cloud; their infrastructure receives your email and password.
- The AI panel is currently disabled; when enabled, prompts and note context will be sent to the configured OpenAI-compatible endpoint to generate responses.
- You can request full deletion of your account and all associated data by emailing **support.airlab@gmail.com**.

A formal Privacy Policy and Terms of Service will publish before open beta.

## License

Closed alpha access is granted under a tester agreement. The source repository's licensing is documented at [github.com/orangetheorange/Airlab-App](https://github.com/orangetheorange/Airlab-App).

---

**Questions, bugs, ideas?** Email **support.airlab@gmail.com** or use **Contact support** in the app.
