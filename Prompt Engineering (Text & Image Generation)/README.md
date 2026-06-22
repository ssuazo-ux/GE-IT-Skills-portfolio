# The Davao Sari-Sari Digital Payment Literacy Prompt System

**Goal:** Engineer a reusable text-generation system prompt and accompanying vector icon that establishes an operational workflow for promoting digital payment adoption (GCash/Maya QR) among sari-sari store vendors in Davao City.

**Role:** Digital Solutions Architect consulting for a social enterprise / LGU livelihood program in Davao City, supporting the shift from cash-only to digital transactions among micro-retailers.

**Audience:** LGU Technical Working Group, who will test this prompt system to generate localized vendor communication scripts and barangay-level training materials.

**Situation:** Generic AI tools produce Western-centric fintech messaging ("seamless digital transformation," "empower your business") that means nothing to a sari-sari store owner managing ₵5–₵20 transactions out of a small barangay stall. This playbook locks the AI into a Davao-specific, accounting-literate, low-jargon voice so the output is something a barangay treasurer or cooperative officer could actually hand to a vendor.

\---

## 1\. System Prompt Template (Final, V3)

```
Act as a Community Finance Literacy Officer working with barangay-level
cooperatives in Davao City to help sari-sari store owners adopt QR-based
digital payments (GCash/Maya). Your objective is to draft a 200-word vendor
briefing explaining why and how to start accepting digital payments alongside
cash.

Context: Most sari-sari stores in Davao City barangays handle small daily
transactions (₱5–₱50) and are wary of digital payments due to fear of fees,
unfamiliarity with QR scanning, and distrust of "losing track" of sales
compared to a cash drawer or notebook (talaan).

Constraints:
- Use a respectful, peer-to-peer tone — speak as someone from the
  cooperative, not a bank or fintech company.
- Do NOT use corporate fintech jargon ("seamless," "ecosystem," "digital
  transformation," "empower").
- Do NOT discuss interest rates, loans, or investment products — payments
  literacy only.
- Frame digital payments as a supplement to the vendor's existing cash
  record-keeping habits (talaan), not a replacement.

Format: Output in Markdown, under 200 words, with exactly three numbered
steps under the heading "### Paano Magsimula (How to Start)".
```

\---

## 2\. Prompt Battle Table

|Version|Prompt Modifier Added|Output Quality Reflection|
|-|-|-|
|**V1**|*"Explain the benefits of digital payments for small businesses."*|Generic fintech-brochure tone. Used buzzwords like "seamless" and "empower," and assumed an audience already comfortable with apps — completely mismatched for a sari-sari vendor on a barangay budget.|
|**V2**|Added vendor persona, named local context (sari-sari store, barangay cooperative), and Davao City setting.|More relevant, but the model defaulted to comparing digital payments favorably *against* cash record-keeping — which read as dismissive of the vendor's existing talaan system and risked sounding condescending.|
|**V3**|Added explicit instruction to frame digital payments as a *supplement* to existing cash habits, banned fintech jargon outright, and capped output at 200 words with a fixed Filipino-language heading.|Target hit. Tone is respectful and peer-level, the talaan isn't dismissed, and the format is short enough to actually hand to a vendor as a flyer insert.|

\---

## 3\. Visual Branding Asset

* **Engine used:** Claude (Anthropic) — SVG code generation (chosen for clean scaling on printed barangay flyers and digital posts alike)
* **Visual prompt used as design brief:** *"A flat minimalist vector icon of a sari-sari store stall with a striped awning, a smartphone displaying a QR code at the counter, and a peso coin beside it — community/livelihood tone, no fintech-app clichés, flat color blocks, legible at small sizes for flyers."*
* **Style constraints enforced:** max 6 flat colors, no gradients or photographic textures, must remain legible at 32x32px, must visually center the *physical sari-sari stall* (not a generic phone-and-app graphic) so vendors recognize themselves in it rather than seeing a bank ad.
* **File:** `sarisari-icon.svg`

[View Icon: sarisari-icon.svg](sarisari-icon.svg)

\---

## Why This Works for the LGU Technical Working Group

* **Locked audience:** The persona (cooperative officer speaking peer-to-peer, not a bank) is what kept the tone respectful instead of sounding like an ad.
* **Locked local behavior:** Naming the talaan (cash notebook) habit explicitly is what stopped the AI from writing dismissive "upgrade from cash" messaging — V2's main flaw.
* **Locked format:** The word cap and bilingual heading are what make the V3 output genuinely deployable as a flyer insert, not just an essay about fintech adoption.

