# Diffian — Brochure Content

Source copy for a printed / PDF brochure. Audience: NHS Wales health boards first,
then councils, contact centres and transport operators.

**Voice name is Carys in all customer-facing material** (Ela / ElaV2 are internal
build names — never use them externally). Renamed from Bronwen on 2026-08-19: Carys
reads correctly on first sight in English and Welsh, is visibly Welsh (the *-ys*),
comes from *caru* ("to love"), and avoids confusion with the separate "Bronwyn"
assistant. If any old material says Bronwen, it's out of date.

**The product is Fi** — pronounced "vee", the Welsh word for "me" — decided 2026-08-19.
Three tiers, used consistently: **Diffian** the company, **Fi** the service/engine,
**Carys** (or the customer's own voice) the voice. Give the pronunciation at first
mention in anything English-facing. The name is the bespoke-voice pitch in one
syllable: a voice that is *me*. Clearance is still pending — see substantiation.

Every factual claim is listed in [Claim substantiation](#claim-substantiation) at the
end, marked verified or needs-checking. **Read that section before this goes to a
customer.** Two claims currently on the website don't survive checking.

---

## 1. Cover

> ### Llais Cymraeg i'ch gwasanaeth.
> ### A Welsh voice for your service.

Bilingual Welsh and English text-to-speech for the organisations that serve Wales.

Our own neural voice. Our own engine. Built for how Welsh is actually spoken.

*Fi, gan Diffian · Caerdydd · diffian.com*

---

## 2. The problem, in one page

**Welsh isn't English with different words.**

Real service content mixes both languages in a single sentence. A patient letter
references an English clinic name inside a Welsh sentence. A queue display calls a
Welsh place name from an English template. Generic speech engines read one of them
wrong every time — and Welsh speakers notice instantly.

Three failures happen over and over:

**Mixed-language sentences.** Appointment messages, IVR menus and announcements switch
between Welsh and English constantly. A single-language voice mangles whichever one it
wasn't built for.

**Place names.** *Llanelli. Pen-y-lan. Aberystwyth. Cwmbrân.* English voices don't have
the sounds. Welsh *ll* isn't an English L — it's a different consonant that English
simply doesn't contain.

**Mutations.** Welsh words change their first letter according to grammar. *Caerdydd*
becomes *Gaerdydd* or *Nghaerdydd* depending on the sentence around it. Engines that
only know dictionary forms get ordinary sentences wrong.

And there's a fourth problem, which is the reason we exist:

**You can't buy your way out of it.** We checked every major cloud vendor's
custom-voice programme. Welsh isn't in them. You can have a Welsh voice that belongs to
Microsoft, or a voice that belongs to you and can't speak Welsh. Not both.

---

## 3. What Fi is

Fi — say it "vee"; it's the Welsh word for "me" — is Diffian's bilingual Welsh and
English text-to-speech service, built around a neural voice we trained ourselves.
Fi is the engine; Carys is its voice.

**Carys, a voice you can own.** A custom-trained neural voice producing 24 kHz audio,
efficient enough to run on ordinary CPU servers. No GPU fleet. No per-character
licensing. No usage meter owned by someone else.

The selling point is the combination: the voice is *bilingual and brandable at once*.
One voice speaks both languages, so a branded voice doesn't force a choice between
sounding like your organisation and saying Welsh correctly — its English pronounces
Welsh place names properly because Welsh is native to the same voice. Lead with this;
the ownership economics are the supporting argument, not the headline.

**Bilingual by design.** Every word is classified before it reaches the voice, so Welsh
place names inside English sentences are read the Welsh way — one request, one voice,
both languages, correct.

**Editorial control that actually lands.** The engine exposes its phonetic decisions so
your Welsh language officer can inspect them and correct them word by word. Corrections
apply everywhere at once and regenerate in seconds.

**Deployed where your governance requires.** Managed API, self-hosted on your own
infrastructure, or pre-generated offline audio bundles. Content never has to leave your
estate.

---

## 4. For NHS Wales

Health boards are subject to the Welsh Language Standards, and few can staff every
telephone line and automated touchpoint with Welsh speakers. Recording a voice artist
for a library that changes every month isn't realistic either.

### Where it fits

**Appointment reminders and automated calls.** Outbound reminder calls and SMS-to-voice,
Welsh-first, with clinic and place names said properly. Generated from your existing
templates — no separate Welsh workflow to maintain.

**Telephone services and IVR.** Menus, queue messages, out-of-hours information and
hold messages in a fluent Welsh-first voice. Change the wording and regenerate the same
day, rather than rebooking a studio.

**Queue calling and waiting areas.** Outpatient and clinic calling systems, pharmacy
collection points, wayfinding announcements. Bilingual from one source, with local
place and department names correct.

**Accessible information.** Spoken versions of patient letters, leaflets and discharge
information for patients with sight loss or who find printed information difficult —
in the patient's language of choice.

**Digital services.** Read-aloud on public-facing web content and apps, so a Welsh
speaker gets Welsh audio rather than an English voice attempting it.

### Why this is different from a generic supplier

- **The voice can be yours.** The same pipeline that produced Carys can produce a
  bespoke voice for your health board — a distinct, consistent identity across every
  automated channel. And because it is trained bilingual like Carys, it is one voice
  in both languages: its English says your Welsh place and department names properly,
  and its Welsh is not a different speaker.
- **Nothing has to leave your network.** CPU-only self-hosting means patient-derived
  text never crosses a third-party boundary. That materially simplifies the DPIA.
- **No per-character meter.** Cost doesn't scale with how much Welsh you produce, which
  removes the perverse incentive to produce less of it.
- **Corrections are permanent.** A pronunciation your clinicians flag is fixed once and
  applies to every future clip, in every service.

---

## 5. Also built for

**Councils and public bodies.** Tannoy and wayfinding announcements, queue systems,
digital services — both languages from one source, with every place name in your area
said properly.

**Contact centres.** IVR menus, queue messages and automated lines with a genuine
Welsh-first voice, without recruiting for it.

**Public transport.** The Public Service Vehicles (Accessible Information) Regulations
2023 require audible next-stop announcements, with deadlines from October 2026. We
generate complete bilingual announcement sets packaged for standard on-vehicle
annunciator hardware, playing offline with no connectivity needed.

---

## 6. Proven at national scale

We built the hardest case first: every bus stop in Wales.

| | |
|---|---|
| Routes covered | **1,391** |
| Stop entries processed | **52,284** |
| Unique bilingual clips generated | **23,928** |
| Generated on | Ordinary CPU, no GPU |

Built from the national public transport dataset, with a stop-name disambiguator that
handles the real-world mess in that data — English names filed in Welsh columns and
vice versa.

That corpus is why the place-name handling works. It wasn't tuned on a demo sentence;
it was run across every settlement, street and interchange name in the country.

---

## 7. How it works

Enough detail to show the work is real, without needing a technical reader.

**Per-word language detection.** Each word is classified before synthesis, using a
curated Welsh lexicon, Welsh spelling patterns, and an English dictionary check so
names like *Penny*, *Lloyd* or *Trevor* aren't misread as Welsh. Hyphenated compounds
(*Pen-y-lan*) and the Welsh article are handled as single units.

**Genuine Welsh sounds.** Welsh has consonants English doesn't. The *ll* in *Llanelli*
is a voiceless lateral fricative — written **ɬ** — and it appears 577 times across our
place-name lexicon alone. An English-trained voice renders it as "l", "thl" or "cl".
Ours produces the actual sound.

**Mutation-aware pronunciation.** Pronunciation entries cover mutated forms explicitly,
so *Caerdydd*, *Gaerdydd*, *Nghaerdydd* and *Chaerdydd* are all said correctly.

**Welsh number and time grammar, written properly.** Welsh numbers carry grammatical
gender — *dau* and *dwy* are both "two", and which one is correct depends on the noun.
Traditional Welsh ordinals are vigesimal (counting in twenties). We implemented this
rather than transliterating English. Times follow the 24-hour convention your
timetables and appointment letters already use.

**Inspectable output.** Every request returns the phonetic transcription the engine
used. Corrections are precise rather than guesswork.

---

## 8. Three ways to deploy

**Managed API.** An HTTP endpoint: send text, receive audio. Generated clips are
cached, so repeated content returns in milliseconds. We run it, you integrate it.

**Self-hosted.** The full engine on your own servers. CPU-only, no GPU, no external
calls. The right fit where content or data can't leave your estate.

**Offline audio bundles.** Complete pre-generated audio sets packaged for announcement
hardware. Sync at the depot or site, play offline, no connectivity required.

---

## 9. Compliance

**Welsh Language Standards.** Welsh-first delivery for public bodies in Wales. Diffian
generates Welsh and English from one workflow, with Welsh leading, the way the
Standards expect.

**Accessible information for sensory loss.** Spoken versions of written patient and
service information, in the recipient's language of choice.

**PSV Accessible Information Regulations 2023.** Audible and visible route information
on local bus services, deadlines from October 2026.

**An honest note on compliance.** No supplier can certify you as compliant, and we
won't claim to. What we provide is the generation capability and an audit trail:
deterministic output (the same text always produces identical audio, verifiable by
hash) and inspectable phonetics. Editorial sign-off on your content remains yours —
and our tooling is built to make that sign-off fast rather than to bypass it.

---

## 10. What we'd want to agree with you

Being straight about this shortens procurement rather than lengthening it.

**Editorial review.** Your Welsh language officer should review the pronunciation of
your specific names and terminology before go-live. We'll provide the phonetic output
and apply corrections; the sign-off is yours.

**Clinical and place-name vocabulary.** Health-specific terms, department names and
local place names should be checked by a fluent speaker. This is where the long tail
lives, and it's fixable — but it's work, not magic.

**Hardware verification.** For announcement and queue systems, audio format and
loudness need checking against your specific hardware.

**A first-language listening panel.** We have the framework built for dialect-stratified
review (north, south, west) and would want to run it against your content. It hasn't
been run yet — see the substantiation notes.

---

## 11. Next step

**Send us your hardest sentence.**

Place names, mutations, clinical terms, mixed languages — whatever you think will break
it. We'll send it back spoken, usually the same day. No commitment, no procurement
forms.

**hello@diffian.com**

---

## Claim substantiation

Check this before the brochure goes out. Numbers are measured from our own corpus and
build unless stated.

### Verified

| Claim | Basis |
|---|---|
| 1,391 routes / 52,284 stop entries / 23,928 unique clips | Generated corpus manifest |
| ɬ appears 577 times in the lexicon | Measured across the lexicon's 3,136 entries |
| 24 kHz audio, CPU-only inference | Engine configuration |
| No cloud vendor offers Welsh custom-voice training | Verified against Microsoft's published locale lists, May 2026. Welsh absent from custom-voice training, cross-lingual transfer and personal-voice locale lists. **Re-verify before use — vendor docs change.** |
| Mutation coverage (Caerdydd / Gaerdydd / Nghaerdydd / Chaerdydd) | Pronunciation override table |
| Deterministic output, verifiable by hash | Voice style is seeded from the text and (since 2026-08-18) computed in float64 on one thread, so the style is bit-stable on every host. Waveform bytes are identical per host class; across CPU generations samples can differ at ~-56 dB (inaudible). Say "the same text always produces the same speech"; only promise hash-identical audio within one deployment |
| Welsh number gender and vigesimal ordinals implemented | In the number expansion module |
| PSV Accessible Information Regulations 2023, October 2026 deadlines | UK legislation |

### Needs checking before use

| Claim | Issue |
|---|---|
| **"A warm request generates a clip in well under a second"** (currently on the website) | **Does not match production.** Measured against the live endpoint: a short sentence takes ~2.4s, a 105-character clip ~7s. The sub-second figure is a local development machine, not the deployed service. **Fix the website too** — a customer running the demo will see the real number. Safer wording: *"a sentence in a few seconds, a full announcement set in minutes."* |
| **"All Wales Standards for Accessible Communication and Information for People with Sensory Loss"** | Referenced in §9 by description rather than name because I could not verify the current title and status. Confirm the correct instrument before naming it to NHS Wales. |
| Welsh Language Commissioner findings on telephone services | Resolved 2026-08-19: both site and brochure now use the staffing framing ("few can staff every line"), which needs no citation. Cite a specific published Commissioner report before reintroducing any "weakest compliance area" claim. |
| Cost comparison versus a voice artist | We have credible figures for the cloud-vendor route, not for studio recording. Don't quote a saving until we can source it. |
| Any quality score, MOS or accuracy percentage | **We have none.** An automated speech-recognition sweep over 12,024 clips exists, but it was built to rank clips worst-first for human review, not to measure quality — Welsh speech recognition is itself weak, so the absolute figures mean little. **Never present it as an accuracy metric.** |
| First-language listening panel results | Framework built, dialect-stratified, **not yet run**. §10 says so; keep it that way. |
| **"Fi" name clearance** | UK IPO trademark search (classes 9/42), Companies House, domain, and a fluent-speaker connotation check are all **pending** as of 2026-08-19. Web search found no voice-tech collision, and "Vee" spellings were rejected (crowded voice-AI space, no V in the Welsh alphabet). Confirm before print. |
| Curated route stop lists | Proof-of-concept, curated from public timetables. Must be verified against operator timetables and the national dataset before any operator deployment. Already flagged in the data files. |

### Deliberately not claimed

- **The lexicon size (3,136 words) as a headline number.** Removed from customer-facing
  material 2026-08-19: it invites the wrong comparison, because the authoritative source
  should be the Welsh Language Commissioner's standardised place-name list, which is much
  larger. Adopting that list is an open engine task; quote a lexicon figure again only
  once it's built from the Commissioner's list.

- Compliance certification of any kind
- A male voice — experiments exist, nothing production-ready
- Suitability for open-ended long-form narration. The voice was trained on a focused
  announcement and service-message corpus and is strongest there.
