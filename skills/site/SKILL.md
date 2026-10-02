---
name: site
description: Build a website with 8B. Use when the user asks to make, create or design a website, landing page or homepage for a business, project, event or person, or wants to see what their site could look like.
---

# Build a site with 8B

1. Work out what the site is for, the name of the business or project, and the language of the site (the user's language unless they say otherwise; if the business is in a country with another language, ask once). If the name is missing, ask once; if the user doesn't care, use a short working name. Don't ask for more: write the rest so the site looks finished (see texts below), and list what you made up for the user to replace.
2. Call `explore_designs` and choose the design whose `fits` and `style` suit the business best. Every section of a design stays on the page, so also check the sections listed in its `summary`. Say in one line what look you chose and why, describing the look itself (colors, type, mood) rather than the design id.
3. Call `get_design_brief` for it with `language` set to the site's language code (for example `"de"`), so the length limits fit that language. Write the whole site for the user's business:
   - **texts**: a new value for every field, following each field's `hint` and `max`; where a field has `word`, no word may be longer than that. Keep `{1:...}` markers. Details the user did not give (reviews and reviewers' names, team members, key figures, prices, opening hours) are written to look real for this business, and you list every one of them for the user to replace before publishing. Contacts are the exception: a phone the user did not give is written in the country's format with zeros (`+351 000 000 000`), an email as `hello@example.com`, and the address as only the city the user named. A section that doesn't fit the business is written for the nearest thing the business has; don't empty it.
   - **colors**: a palette that suits the business, derived from the design's palette so the layout still works. Keep the readable pairs named in each color's `role`.
   - **fonts**: map a family named in the brief to a Google Fonts spec. If the site is not in Latin script, replace every font with `cyrillic: false` by a family with the needed glyphs and a similar character. Otherwise change fonts only if the business needs a different mood.
   - **images**: for each photo, following its `hint`, an English Unsplash search query and a short description of the photo in the site's language: `{"query": "...", "alt": "..."}`. Photos of the same kind share one query (all team portraits, all product shots): each place still gets a different photo. Usually 3–8 distinct queries cover the whole site. Where portraits must match the names on the page, split the query: "male … portrait" or "female … portrait".
4. Call `generate_site` with `design_id`, `site_name`, `language`, `texts`, `colors`, `fonts` and `images`. If the result lists warnings (length, long words, fields not filled, photos not found), send just those values again with `base_preview_id`. Never shorten the brand name or text the user dictated on your own: tell the user instead.
5. Show the result:
   - Where the client shows a preview card, tell the user that **Open preview** shows the live site full screen.
   - Otherwise give `preview_url` as a link. If a browser tool is available, open `preview_url` in it so the user sees the site with its animations. Anyone with the link can open the preview.
6. Mention once that the finished site can be downloaded as one HTML file (the **Download site** button, or `download_url`); in a coding project you can save it with `curl -L -o <file>.html <download_url>`. Don't repeat the link in later messages unless the user asks.
7. For changes ("warmer colors", "another headline", "the clinic is in another city"), call `generate_site` with `base_preview_id` set to the `id` of the newest preview, and only the values that change. Everything else is kept, so don't send the other texts again.

Full reference (tools, limits, errors, license): https://8b.com/mcp/index.md
