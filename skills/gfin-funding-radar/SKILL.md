---
name: gfin-funding-radar
description: Search public funding opportunities when the user asks about grants, funding, or what they could apply for. Use for a catalogue search, not for eligibility verdicts or private account data.
---

1. Call `search_opportunities` with the user's keywords and, when they name a US state, the two-letter
   state code. Omit a filter only when the user did not give one.
2. Read the returned rows before answering. Each row carries the funder, the stated amount, the
   deadline and the funder's own link. Link the funder page; do not invent one.
3. Treat `deadline.status` of `unknown` as "the source states no usable deadline". Never guess a date.
4. Call `get_opportunity` only when the user asks for detail on a row you already returned.
5. These tools read the public catalogue only. For an organization's own matches, saved items,
   pipeline or requirement checks, say plainly that it is a GFIN product capability and point to
   https://app.gofunditnow.com. Do not describe those as available here.
