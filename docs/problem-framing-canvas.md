# Problem Framing Canvas — ChatGPT mobile voice (India)

## User & context

- **Who:** Working professional, 24–35, metro India, ChatGPT mobile 3+ times/week  
- **When:** Commute, short breaks, walking between meetings  
- **Job to be done:** Turn a messy thought into a **correct** prompt for email, summary, analysis, or message draft  

## Current behaviour

- Opens composer, **types** for important tasks  
- Has **seen / used** the mic; does not stick with voice  
- Uses **WhatsApp voice notes** for people; not the same trust for “prompt to AI”  

## Desired behaviour

- Speak a long prompt when hands or eyes are busy  
- **Read and fix** names, numbers, jargon  
- Send only when the text matches intent  

## Barriers

| Type | Detail |
|------|--------|
| Functional | No stable **draft** state; feels like speak → immediate send |
| Emotional | Anxiety about wrong words changing model output |
| Social | Won’t speak sensitive work content in public |
| Habit | Keyboard = control; voice = gamble |

## Insight (one sentence)

**Voice loses to typing because typing lets you edit while you compose; voice on ChatGPT mobile does not offer an equivalent pause.**

## Problem statement

For working professionals on ChatGPT mobile in India, **voice input is avoided for work prompts because they cannot verify and correct the transcript before it becomes the prompt**, even though they already use voice in other apps.

## Solution hypothesis

**Voice Draft Mode:** Mic → live transcript in dashed draft box → tap word to fix → **Send** commits to chat. Optional: mark low-confidence tokens.

## Non-goals (this cycle)

- Re-train recognition for Indian accents / Hindi  
- Auto-structure into STAR/bullets without user action  
- Desktop / web  
- Push campaigns to “try voice” without fixing trust  

## Metrics to validate problem shift

- Voice **draft-to-send rate** (mic tap → Send)  
- **Edit rate** on voice drafts (expect >0; proves review)  
- **7-day repeat** voice use among experiment cohort  
- Guardrail: typing share on long prompts should not rise (no extra friction tax)
