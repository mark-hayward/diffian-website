# Site positioning — draft revisions

Proposed copy changes to move diffian.com from reading as a transport supplier to
"anywhere your organisation speaks". Current copy shown alongside so the change is
reviewable rather than a rewrite.

**Not applied to `index.html` yet.** Nothing here is live.

Guardrails this draft sticks to:

- **Not translation.** We do speech, not English→Welsh text translation. Leading on
  "translations" sets an expectation the first discovery call has to correct.
- **Not "any Welsh text".** The corpus is short, formulaic service messages. Strongest
  there, weaker on long-form. Widen to *service messages across every channel*.
- **Transport becomes proof, not pitch.** The 23,928-clip corpus is the best evidence we
  have; it currently reads as a product category.

---

## 1. Hero demo — swap the anchor

The hero is the single strongest signal of who we're for. It's currently a bus stop.

**Now**

> Announcement · Bronwen · live
> ▶ CY Yn cyrraedd Caerfyrddin nawr.
> ▶ EN Now arriving at Carmarthen.

**Proposed**

> Service message · Bronwen · live
> ▶ CY Pwyswch un am wasanaeth yn Gymraeg.
> ▶ EN Press one for service in Welsh.

*Why:* every organisation with a phone number needs this line. A bus stop excludes
everyone who isn't a bus operator. The audio already exists — it's one of the current
"Hear it" samples.

---

## 2. Sub-headline — widen the frame

**Now**

> Diffian is a bilingual Welsh and English text-to-speech service for the organisations
> that serve Wales: councils, health boards, contact centres and transport operators.

**Proposed**

> Diffian is a bilingual Welsh and English text-to-speech service for the organisations
> that serve Wales. Phone lines, appointment reminders, announcements, accessible
> information — wherever your service speaks, it can speak Welsh properly.

*Why:* the sector list makes people check whether they're on it. Naming the *content
types* lets everyone recognise themselves immediately, and the sector list still appears
lower down.

---

## 3. "Hear it" samples — rebalance

Three of four are currently transport. Proposed mix keeps one and adds breadth. All four
should be regenerated with the current engine so the phonetics shown are accurate.

| Keep / change | Language | Line | Demonstrates |
|---|---|---|---|
| **Keep** | CY | `Pwyswch un am wasanaeth yn Gymraeg.` | IVR — the universal case |
| **New** | EN | `Your appointment is at the Heath, Cardiff, on the fourth of March.` | English carrier, Welsh place name, spoken date |
| **Keep** | CY | `Croeso i Gaerdydd.` | Mutation — *Caerdydd* → *Gaerdydd* |
| **Keep (reframed)** | EN | `This service calls at Llanelli, Machynlleth, and Aberystwyth.` | Three hard place names in one English sentence |

*Note:* the appointment line needs generating and listening to before it ships —
particularly the date expansion. Don't publish phonetics we haven't checked.

---

## 4. Compliance — reorder

**Now:** Welsh Language Standards, then PSV Accessible Information Regulations 2023.

**Proposed order**

1. **Welsh Language Standards** — applies to every public body in Wales. Keep first,
   expand slightly: name telephone and automated services explicitly, since that's where
   organisations struggle most.
2. **Accessible information** — spoken versions of written information for people with
   sight loss or who find print difficult. *Describe it; don't name the instrument until
   the exact title and status are confirmed.*
3. **PSV Accessible Information Regulations 2023** — move to third and label it clearly
   as applying to local bus services, so it reads as one sector's requirement rather than
   our whole reason for existing.

Keep the existing honest note that no supplier can certify compliance. It builds more
trust with public-sector buyers than a compliance badge would.

---

## 5. National corpus — reframe as proof

This is the highest-leverage change. Same numbers, different job.

**Now** — presented under Sectors → Public transport, reading as "buses are what we do".

**Proposed** — its own short band, above Sectors:

> ### We proved it on the hardest case first.
>
> Before selling this to anyone, we generated bilingual audio for **every bus stop name in
> Wales** — 1,391 routes, 52,284 stop entries, 23,928 unique clips, on ordinary CPU.
>
> Not tuned on a demo sentence. Run across every settlement, street and interchange name
> in the country. That's why the place-name handling holds up on your names too.

*Why:* it converts the corpus from a category into credibility, and it's the one claim a
competitor can't match.

---

## 6. Sectors — add two, keep the rest

Current three (Councils & public bodies, Contact centres & IVR, Public transport) are
right. Proposed additions:

**Health boards.** Appointment reminders and automated calls, outpatient queue calling,
spoken patient information, Welsh-first telephone services. Patient-derived text never
has to leave your network — CPU-only self-hosting materially simplifies the DPIA.

**Digital services.** Read-aloud on public-facing web content and apps, so a Welsh speaker
gets Welsh audio rather than an English voice attempting it.

Also worth reordering so **Contact centres & IVR comes first** — it's the most universal
and the easiest yes.

---

## 7. Fix while we're in here

**The sub-second claim.** "A warm request generates a clip in well under a second" is a
local dev machine. Production measures ~2.4s for a short sentence and ~7s for a
105-character clip. A customer running the demo sees the real number.

Proposed: *"A sentence comes back in a few seconds, a full announcement set in minutes —
on ordinary CPU, with no GPU bill attached."*

Keeps the real point (cheap hardware, no GPU) without a figure that contradicts itself
on contact.

---

## Sequencing

1. §7 first — it's a correction, not a repositioning, and shouldn't wait
2. §1, §2, §5 — the actual reframe, and where most of the value is
3. §3 — needs new audio generated and listened to
4. §4, §6 — straightforward once the frame is agreed
5. Mirror everything into `cy/index.html`

The Welsh page has diverged before. Whatever ships, port it in the same change rather
than as a follow-up.
