---
name: feature-description
description: >-
  Creates structured feature descriptions, changelog release notes, and team announcement posts (e.g., Microsoft Teams) for new product features and versions. Use whenever writing, expanding, or formatting feature highlights, updating changelog markdown files, or drafting release announcements.
---

# Feature Description & Release Announcement Skill

This skill guides the creation of high-impact, user-focused feature descriptions and release announcements for SearchPoint and similar products, ensuring consistency across both repository changelog files (`changelog/<version>.md`) and team communication channels (Microsoft Teams, Slack, email).

---

## 1. The Core Feature Description Formula

Every feature description should follow this clear, structured framework:

1. **Feature Title & Badge**:
   - Clear, concise name indicating the capability (e.g., `OCR Image Search`, `Custom AI Renamer Rules`).
   - Include version tag where applicable (e.g., `(v0.30.0)`).
2. **Hook / High-Level Value**:
   - One direct sentence explaining what the user can now do and where.
   - Example: *"Take full control of how your files are organized with customizable AI renaming conventions!"*
3. **How It Works**:
   - Explain the mechanism in plain, accessible terms without unnecessary jargon.
   - Highlight on-device capabilities, privacy, speed, or configuration points.
   - Example: *"SearchPoint uses on-device Optical Character Recognition (OCR) to automatically extract and index text embedded in images, screenshots, and scanned documents."*
4. **Why It Matters (User Benefit)**:
   - State the tangible pain point resolved or productivity gain achieved.
   - Example: *"No more manually scrolling through hundreds of image files to find a specific receipt, diagram, infographic, or screenshot."*
5. **Visual Demo / Media**:
   - Attach or embed the relevant screen recording, animated GIF, or video.

---

## 2. Changelog Markdown File Format (`changelog/<version>.md`)

When updating or creating a changelog file, use the frontmatter and section layout:

```markdown
---
title: "<Short Descriptive Feature Name>"
version: "<version-semver>"
date: "<YYYY-MM-DD>"
---

SearchPoint <version> introduces <brief summary sentence>.

## <Feature Section Title>

<One-sentence hook or overview statement>

- **<Key aspect or configuration setting>**: <Explanation of how to use it, inputs, tags, etc.>
- **Why it matters**: <Direct user benefit and time saved>

<video src="./videos/<version>-<feature-slug>.mp4" autoPlay loop muted playsInline controls></video>
```

*(Note: If multiple features are included in a single release, duplicate the `## <Feature>` block for each feature).*

---

## 3. Microsoft Teams Announcement Post Format

When announcing one or multiple releases in a single channel post:

### Structure:
- **Title / Subject Line**: Engaging announcement headline with emojis and the highlighted feature names.
- **Greeting & Overview**: Friendly opening stating the version(s) covered and overall theme.
- **Feature Spotlights**: Dedicated block for each feature using the Core Formula (Hook + How it works + Why it matters).
- **Media / Demos**: Embedded inline or attached with clear references.
- **Call-to-Action / Feedback**: Prompting users to try it and leave feedback in the thread.

### Template:

```markdown
> **Subject / Title:** 🚀 What's New in SearchPoint: [Feature 1] & [Feature 2]!
>
> Hi everyone, 👋
>
> We're excited to highlight the latest update(s) to **SearchPoint** (v[X.Y.Z]) bringing [brief theme, e.g., smarter discovery and organization] to your files:
>
> ---
>
> ### 🔍 1. [Feature 1 Name] *(v[Version])*
> [One-sentence hook]
> - **How it works:** [Concise mechanism explanation]
> - **Why it matters:** [User benefit / pain point eliminated]
>
> ---
>
> ### 🏷️ 2. [Feature 2 Name] *(v[Version])*
> [One-sentence hook]
> - **Custom Rules / Controls:** [Explanation of options & configuration]
> - **Why it matters:** [User benefit / pain point eliminated]
>
> ---
>
> 💡 *Check out the demo videos attached below to see these features in action! Let us know your thoughts or feedback in the replies.* 👇
```

---

## 4. Media & Video Handling Guidelines for Teams

When assisting users with attaching or embedding demo videos in Teams posts:
- **Inline Auto-playing Demos**: Recommend converting short `.mp4` video recordings to `.gif` (e.g., using `ffmpeg -i demo.mp4 -vf "fps=15,scale=720:-1:flags=lanczos" demo.gif`) and pasting directly into the message body.
- **Playable Player**: Recommend uploading the `.mp4` to OneDrive/SharePoint/MS Stream and pasting the URL into the post content so Teams unfurls an inline interactive player.
- **File Attachments**: Point to repository video paths in `changelog/videos/<version>-<name>.mp4`.
