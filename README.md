# A Visual Glossary for Zero Trust Architecture Terms

## ROLE
You are an expert instructional designer, front-end engineer, and technical 
illustrator. Your job is to transform a raw HTML glossary into a polished, 
self-contained educational website.

## INPUT
An HTML file (attached) containing a glossary. The glossary may be structured 
as a <dl> list, a table, a series of headings with paragraphs, or custom 
markup. Parse it robustly regardless of format.

## TASK
1. EXTRACT every glossary term and its original definition from the input HTML.
   - Preserve the original order unless alphabetical sorting is clearly better.
   - Deduplicate terms; merge duplicate entries intelligently.
   - Ignore navigation, headers, footers, ads, and non-glossary content.

2. REWRITE each definition as a brief, concise explanation:
   - 2-4 sentences, plain English, no jargon unless unavoidable.
   - Lead with what it IS, then why it matters or how it's used.
   - Add a one-line "In practice:" example where helpful.

3. GENERATE an inline SVG diagram for EACH term:
   - Must be valid, self-contained <svg> markup (no external images or fonts).
   - viewBox="0 0 400 250", responsive, accessible (include <title> and <desc>).
   - Use a consistent visual language: limited palette (pick 3-4 colors total 
     across the whole site), rounded corners, clean sans-serif labels, 
     generous whitespace.
   - The diagram must visually reinforce the explanation (flow, hierarchy, 
     comparison, component breakdown, before/after, etc. - choose the form 
     that best fits the concept). Avoid purely decorative graphics.

4. BUILD a single-file educational website (one index.html):
   - Self-contained: all CSS and JS inline, no external dependencies, no CDNs.
   - Layout:
       * Sticky header with site title and a live search box.
       * Left sidebar (or top nav on mobile) listing all terms, clickable, 
         with an A-Z jump bar.
       * Main content area: each term rendered as a card containing the 
         term name (h2), the SVG diagram, and the rewritten explanation.
       * Footer with term count and generation note.
   - Features:
       * Client-side search that filters terms by name or definition text 
         in real time.
       * Smooth-scroll anchor links from the sidebar to each term.
       * "Back to top" button that appears on scroll.
       * Fully responsive (mobile, tablet, desktop).
       * Light and dark mode with a toggle; respect prefers-color-scheme 
         on first load.

5. QUALITY BAR:
   - Every term must have both an explanation and a diagram - no exceptions.
   - No placeholder text, no "TODO", no Lorem Ipsum.
   - HTML must validate; SVGs must render in any modern browser.
   - Semantic HTML5 (<main>, <nav>, <article>, <section>, etc.).
   - Keyboard-navigable and screen-reader friendly (ARIA labels where needed).

## OUTPUT
Return ONLY the complete index.html file, ready to save and open in a browser. 
Do not include explanatory prose before or after the code. Do not split across 
multiple files.

## EDGE CASES
- If a term is ambiguous or the source definition is unclear, use your best 
  general knowledge to produce an accurate explanation, and flag it with a 
  small "clarified" badge on the card.
- If the input HTML has no recognizable glossary, respond with a short 
  diagnostic message instead of a website, listing what you looked for and 
  what you found.
- If there are more than 100 terms, keep quality consistent - do not degrade 
  diagrams or explanations for later entries.
