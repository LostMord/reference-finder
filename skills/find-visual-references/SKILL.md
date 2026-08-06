---
name: find-visual-references
description: Find, shortlist, and compare visual references from Pinterest for websites, landing pages, product interfaces, individual UI sections, responsive layouts, typography, color, imagery, and motion direction. Use when the user explicitly asks for Pinterest inspiration, references, a moodboard, or examples; or before a substantial new visual design or redesign when no approved visual direction exists and preference calibration would materially improve the result. Do not use for backend work, bug fixes, narrow styling adjustments, or an already approved or frozen design direction.
---

# Find Visual References

Use an authenticated Pinterest session in a supported interactive browser to turn visual research into a user-approved design direction. Keep research separate from implementation.

## Guardrails

- Do not edit project files, generate assets, or begin a redesign while collecting references.
- Do not inspect or extract passwords, cookies, local storage, session files, or authentication tokens.
- When Pinterest requires sign-in, CAPTCHA, or two-factor authentication, ask the user to complete it directly in the selected browser and continue after confirmation.
- Do not reproduce a reference pixel-for-pixel or reuse protected imagery without permission. Extract principles and combine them into an original direction.
- Preserve an existing approved design, brand system, or responsive state. Do not invoke this workflow to reopen settled choices unless the user requests it.

## Workflow

### 1. Frame the research target

Infer the target from the request and available project context whenever safe. Identify:

- page, section, component, or interaction being designed;
- product type and audience;
- desktop, mobile, or responsive emphasis;
- existing brand constraints and elements that must remain;
- visual qualities to explore or avoid.

Ask one concise question only when a missing answer would materially change the search. Otherwise proceed with stated assumptions.

### 2. Build focused queries

Create three to five queries that vary the direction rather than repeating synonyms. Combine the most useful terms from:

- industry or product type;
- page or component type;
- desired visual character;
- layout, typography, imagery, interaction, or device pattern.

Prefer concise English queries for broader visual coverage, but include the project's language or regional terms when relevant. Example patterns:

- `premium lighting ecommerce product page editorial`
- `dark architecture portfolio mobile navigation`
- `minimal SaaS dashboard onboarding typography`

### 3. Search through Pinterest

Use Pinterest as the primary source. Use another source only when the user requests it or explicitly accepts a fallback.

Use the browser integration available in the current host and follow its control instructions:

- In Codex, use the supported Browser integration and let the runtime select the browser for the Pinterest URL unless the user chose one explicitly.
- In Claude Code, use Claude in Chrome so Pinterest opens with the user's existing signed-in session. If Chrome tools are unavailable, ask the user to enable `/chrome` or restart with `claude --chrome`, then continue after the connection is ready.
- In another Agent Skills host, use an interactive browser that supports the user's authenticated session and screenshots.

Open Pinterest directly. Do not replace an unavailable authenticated browser with credential scraping or an unrelated source.

Collect approximately 12 to 20 viable candidates before shortlisting. Prefer specific Pin pages over search-result URLs. Record only information visible on Pinterest and keep the direct Pin URL for each candidate.

If no supported interactive browser is available, state that the authenticated Pinterest workflow requires one. Do not imitate browser access by reading profiles, cookies, session files, or credentials. Offer a domain-filtered public web search only as an explicitly labeled fallback.

### 4. Curate a diverse shortlist

Reduce the candidates to six to nine strong references. Ensure the set explores meaningfully different choices, such as:

- composition and hierarchy;
- typography and density;
- color and contrast;
- imagery and art direction;
- navigation and interaction;
- mobile treatment or motion behavior.

Remove duplicates, near-duplicates, inaccessible Pins, generic filler, and examples unrelated to the requested surface. Do not invent titles, authors, or explanations.

### 5. Present the choice

Show a compact numbered selection. Prefer a visual grid with readable thumbnails when the current interface supports it; otherwise use numbered previews or screenshots with direct Pin links. For each reference include:

- its number;
- a direct Pinterest link;
- one short note explaining the relevant design idea;
- the main dimension it represents, such as composition, typography, color, or motion.

### Deliver previews reliably

- Do not embed Pinterest CDN URLs, including `i.pinimg.com` URLs, as Markdown images. The chat renderer does not share the authenticated browser session, so these images can appear as broken placeholders.
- Capture each shortlisted Pin or its visible search-result card with the browser's screenshot capability while Pinterest is open in the authenticated session.
- Return captured screenshots through the host's native image-output mechanism. Forward image bytes directly when the browser tool returns image content; do not convert them into remote Markdown URLs.
- In Codex, follow the Browser integration's image-forwarding instructions. In Claude Code, use Claude in Chrome screenshots; if the current Claude surface cannot display them inline, save the screenshots to a task-scoped directory and provide their local paths beside the numbered Pin links.
- Place the direct Pinterest Pin link in the accompanying numbered text. The screenshot is the preview; the Pin URL is the source link.
- Before presenting the shortlist, confirm that every candidate has both a captured preview and a specific Pin URL.
- If screenshots cannot be captured or attached, present a link-only shortlist and explicitly say that previews are unavailable. Never send broken remote-image placeholders as a fallback.

Do not overwhelm the user with the full research pool or long design commentary.

Ask the user to select up to three references and say what they like or dislike. A good prompt is: `Какие номера ближе? Что именно берем: композицию, типографику, цвет, атмосферу или механику? Что точно не использовать?`

### 6. Convert the selection into direction

After the user chooses, summarize the approved direction under these headings:

- structure and hierarchy;
- typography;
- palette and contrast;
- imagery;
- interaction or motion;
- explicit exclusions.

Separate direct user choices from reasonable inferences. Resolve conflicts with one concise question. Do not create a design-direction file unless the user asks to persist the result.

### 7. Require the implementation handoff

Wait for explicit approval before changing the site or generating visual assets. When approval arrives, treat the direction summary and selected references as constraints, not as permission to copy them literally.

## Completion standard

Consider the research complete only when:

- every shortlisted item has a working, specific Pinterest link;
- the shortlist is visually diverse and relevant;
- the user has made or declined a selection;
- the resulting direction clearly records both desired qualities and exclusions;
- no project files or external Pinterest content were changed during research.

