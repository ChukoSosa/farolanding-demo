# Recording guide — mctaski-chrome demo with Faro

## Setup before recording

1. **Initialize the Faro repo as a git repository**:
   ```bash
   mkdir faro-demo
   cd faro-demo
   cp ~/Downloads/faro-landing-en.html ./index.html
   git init
   git add .
   git commit -m "feat: initial landing page"
   git remote add origin <test-repo-on-github>
   git push -u origin main
   ```

2. **Start MCTASKI in the folder**:
   ```bash
   mctaski
   ```

3. **Serve the landing locally** (in a second tab). You can use:
   ```bash
   python3 -m http.server 8000
   ```
   Then open `http://localhost:8000`. This matters: the recording has more impact if the page has a real URL, not `file://`.

4. **Have the MCTASKI dashboard open in a third tab** (`http://localhost:7777`).

5. **mctaski-chrome should already be installed** and visible on the landing tab.

## Recording layout

Suggested layout for the video:
- **Main tab (visible)**: Faro landing with the widget visible.
- **Second monitor or picture-in-picture**: MCTASKI dashboard.
- Or alternatively: split screen with landing | dashboard side by side.

## The 5 intentional bugs on the page

| # | Where | What needs to be fixed |
|---|-------|------------------------|
| 1 | Hero, h1 | "intentioons" → "intentions" |
| 2 | "Get started" / "Create my account" buttons | Orange `#ff4500` doesn't fit the palette. Change to teal `var(--accent)` |
| 3 | Footer copyright | "© 2021" → "© 2026" |
| 4 | Features section, the 3 cards | The middle card has more text and breaks alignment. Make all 3 cards the same height |
| 5 | Navbar, links | Product/Features/Pricing/Blog have no hover state |

## Suggested tasks to dictate from the widget

These are the tasks you dictate during the recording, in order. Worded so the viewer understands what's being asked:

1. **Typo**:
   ```
   There's a typo in the hero headline. It says "intentioons" and should be "intentions" #copy #fix
   ```

2. **CTA color**:
   ```
   The primary CTA button "Get started" / "Create my account" uses a bright orange that doesn't match the rest of the palette. Change it to a teal that's consistent with the --accent variable #ui
   ```

3. **Footer year**:
   ```
   The copyright year in the footer says 2021. Update it to 2026 #fix
   ```

4. **Card alignment**:
   ```
   The 3 cards in the "Build habits without burning out" section have different heights because the middle card has more text. Make all 3 cards the same height regardless of content length #ui
   ```

5. **Navbar hover state**:
   ```
   The navbar links (Product, Features, Pricing, Blog) have no hover state. Add a smooth color transition on hover, using the teal --accent color as the destination #ux
   ```

## Suggested video structure

**Estimated total duration: 4-7 minutes**

### Part 1: setup (30 seconds)
- Show the Faro landing open in the browser.
- Voiceover: "I built this landing page and got 5 fixes from the client. Watch how I do them without touching the editor."
- Scroll through the page, briefly highlighting each bug (the typo, the orange button, the footer, etc.)

### Part 2: adding tasks from the widget (1-2 minutes)
- Click the mctaski-chrome FAB.
- Type each of the 5 tasks.
- Show how page context (URL + viewport) gets prepended automatically.
- Show the "Recent" list filling up.
- Switch to the dashboard tab: tasks already appear there too. **This is the key sync moment** — let it land.

### Part 3: hit Play (a few seconds)
- On the dashboard, click Play.
- Let it run.

### Part 4: execution (2-3 minutes, with cuts/timelapse)
- Show tasks executing one by one.
- Activity tab showing what Claude does (Read, Edit, Write).
- Each task ends and the commit SHA appears with the green pushed arrow.
- If you want to speed up, do timelapse here.

### Part 5: the reveal (30 seconds)
- Switch back to the landing tab.
- Refresh.
- Show the corrected page: typo fixed, button with the right color, year updated, cards aligned, hover working.
- Cut to GitHub → show the 5 clean commits with their messages.

### Part 6: outro
- "That's how I work with MCTASKI. If you want to try it: [link]."

## Recording tips

- **Voiceover** in your natural voice, casual tone — like you're showing a friend.
- **Don't explain how MCTASKI works technically** — show it. The magic is the viewer understanding just by watching the flow.
- **Showing the dashboard a couple of times** is important because it demonstrates real-time sync.
- **The final refresh is the money shot** — don't rush it.
- **Consider partial split screen** showing the MCTASKI dashboard while you type into the widget. This shows live sync.
- **The button color change from orange to teal** is the most visually satisfying transition. Lean into it.
- **Subtitles**: since you're recording in English with a Spanish base, plan to add Spanish subs in post. Consider also adding English subs (auto-generated, then cleaned up) — it's the single biggest accessibility win for international audiences and people who watch on mute.

## Edge cases to watch for

- **If Claude gets confused about what `var(--accent)` is**: the file has that variable defined in `:root`. It's fine.
- **If a task ends up blocked**: edit the prompt to clarify and hit Retry. Show that flow too — it's valuable for the viewer to see the system handles errors gracefully.
- **If you want a bug to be more obvious**: edit the HTML manually before recording. For example, you can exaggerate the typo, or make cards even more misaligned by adding more text to the middle one.

## Distribution variants to consider

- **30-second teaser for Twitter/X**: visible bug → click on widget → type task → cut → refresh with everything fixed. No explanation. Curious viewers go to the longer video.
- **Long version for YouTube/blog post**: full explanation, dashboard tour, GitHub history walk-through.
- **Silent version with music** for Instagram Reels / TikTok: rapid cuts, no voice, just music + visual storytelling. Different audience.

---

Good luck with the recording!
