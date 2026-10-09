# Voice Draft Mode — Milestone 3 (3-pager source)

**Team:** ChatGPT mobile composer · **Contributor:** Arushi Srivastava · **Status:** Proposal + prototype  
**Prototype:** [https://steel-main-21529943.figma.site](https://steel-main-21529943.figma.site)

---

## 1. Problem definition

**What is the problem?**  
Working professionals on ChatGPT mobile in India rarely use voice for work prompts. They know the mic exists and many have tried it once. They go back to typing because **voice feels less safe**: the words can become the prompt before they have read and fixed them.

**Who experiences it?**  
Employed ChatGPT mobile users in India, 3+ sessions/week, prompts for email, summaries, analysis, drafting.

**Business value**  
Higher **voice completion** on mobile → longer sessions, stronger habit, better Plus retention in a high-LTV cohort.

**User benefit**  
Speak when hands or eyes are busy; **same control as typing** before the model runs.

**Why now?**  
Competitors expose **review or interrupt** patterns (WhatsApp listen-before-send, Gemini Live). ChatGPT mobile composer still feels **one-shot**. Milestone 2 showed **control**, not discoverability, is the gap.

---

## 2. Goals

**North star (primary)**  
**Voice prompt completion rate** — share of voice sessions that end in **Send** (not abandoned, not fully retyped on keyboard).

**Supporting metrics**

| Metric | Why |
|--------|-----|
| Draft-to-send rate | Mic stop → user taps Send |
| Edit rate on voice drafts | Proves review step is used |
| 7-day repeat voice use | Habit, not one-off trial |
| Flagged-word tap rate | Low-confidence UX working |
| Typing share on 50+ char prompts | Guardrail: no net friction vs control |

**Non-functional**  
Draft appears in **&lt;200ms** after stop; no auto-send; accessible tap targets on mobile.

---

## 3. Non-goals

- Advanced Voice Mode (spoken conversation)  
- New ASR / Indian accent programme  
- Auto-organize into bullets or STAR (phase 2 in prototype, labeled)  
- Desktop / web composer  
- Push / email campaigns to “try voice” without draft UX  

---

## 4. Validation of the problem (Milestone 2 recap)

| Signal | Result (focus segment) |
|--------|-------------------------|
| Typing feels safer | **70%** |
| Check-and-fix before send would help | **50%** |
| Voice on WhatsApp; ChatGPT not rated above Google/Gemini | **80%** / **0% better** |

Qual: three calls + survey open-text → **pre-send control** theme dominates. Details: [survey-and-interviews.md](./survey-and-interviews.md).

---

## 5. Target audience

**Segment:** Working professionals, India, ChatGPT mobile, English-first work prompts.  
**Persona:** “Priya, 28, consultant—ChatGPT on commute, types client emails, tried voice once, got a wrong term, stopped.”  
**Journey today:** Open chat → type long prompt → send → read answer.  
**Unmet need:** Speak the prompt **without losing the edit pass**.

---

## 6. Solution — three directions & trade-offs

| Direction | Impact on control barrier | Effort (2 wk) | Confidence | Decision |
|-----------|---------------------------|---------------|------------|----------|
| **A. Voice Draft Mode** | High — directly adds review | Medium (composer UX) | Medium (n≈16 survey + 6 interviews) | **Build** |
| B. Auto-organize / STAR coach | Medium — helps after text exists | Medium–high | Low without more research | **Later** |
| C. Recognition / Hinglish | High long-term | Very high (model) | Low in 2 weeks | **Out** |

**Chosen: A — Voice Draft Mode**

---

## 7. User flow

1. User in chat; **mic always visible** in composer (no buried menu).  
2. Tap mic → speak → stop.  
3. Transcript appears in **dashed draft box** (not sent).  
4. Uncertain tokens optionally underlined; **tap word** to edit inline.  
5. User taps **Send** → text enters thread as user message → model responds.  
6. Optional: **Discard** returns to keyboard without sending.

**Discovery:** One first-run line: “Voice stays as a draft until you send.” No modal takeover.

---

## 8. Wireframes (annotated)

See prototype: [steel-main-21529943.figma.site](https://steel-main-21529943.figma.site)

| Screen | Annotation |
|--------|------------|
| Default composer | Mic in bar; parity with text field |
| Recording | Obvious stop; no fake “live send” |
| Draft state | Dashed border, “Draft — not sent yet” |
| Edit word | Inline fix; keyboard for one token |
| After Send | User bubble shows final text; assistant runs |

Local HTML demo: [Voice_Draft_Mode_Prototype.html](../Voice_Draft_Mode_Prototype.html) (if added to repo).

---

## 9. Key logic

- **Never auto-send** speech to the thread.  
- Draft cleared on Send or Discard.  
- If recognition empty → stay in draft with error hint, do not send.  
- Phase 2 button “Structure this” visible but **disabled / labeled later** in prototype.  

---

## 10. Launch readiness (experiment)

| Milestone | Owner |
|-----------|--------|
| PRD + flag spec | PM |
| Composer draft UI | Mobile eng |
| QA: edit, send, discard, rotation | QA |
| Support macro: “voice draft” | Support |

**Experiment:** 50/50 on mobile, India + English locale, 2 weeks.  
**Kill rule:** If draft-to-send &lt; control voice completion **and** edit rate &lt; 15%, stop—review step may be too heavy.

---

## 11. Growth (light touch)

- Mic persistent in composer (no seasonal campaign).  
- At most **one** in-product tip first week; no badge spam.  
- Measure repeat, not mic taps alone.

---

## 12. Open questions

- Exact underline threshold for low-confidence tokens?  
- Should Send require explicit tap or allow “Send on stop” power user setting? (Default: require tap.)  
- Expand segment to students after professional cohort validates?

**Decisions taken:** Build draft mode; defer recognition and auto-structure; mobile-only V1.
