# /consult — The Boardroom

> Step into an immersive advisory boardroom. You're the President. 2-4 world-class advisors debate your strategic decisions in real-time.

22 deep-research personas across Business, Engineering, Design, Finance, and Thai Business — each with authentic voice, real frameworks, signature quotes, and known blind spots. They speak directly to you, react to each other, interrupt, challenge, and deliver a clear recommendation.

**Bilingual: English + Thai (ภาษาไทย)** — Ask in Thai, get Thai responses. Signature quotes stay in original English.

## Install

```bash
# Clone into your Claude Code skills directory
git clone https://github.com/Moysed/claud-consultants-skill.git ~/.claude/skills/consult
```

Or manually copy the entire `consult/` folder into `~/.claude/skills/`.

That's it. No dependencies. No config. Just `/consult`.

## Usage

### English
```
/consult Should I rewrite my auth system from scratch?
/consult What's the best pricing strategy for my SaaS?
/consult Should I raise VC or bootstrap?
```

### ภาษาไทย
```
/consult ควรเขียน auth ใหม่ทั้งหมดไหม?
/consult ตั้งราคา SaaS ยังไงดี?
/consult ควรระดมทุน VC หรือ bootstrap ดี?
```

### Auto-trigger
The skill auto-detects strategic questions about architecture, design, investing, pricing, rewrites, scaling, and product direction — in both English and Thai. Just ask naturally.

### The Meeting

When you invoke `/consult`, the environment transforms into a boardroom:

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
  BOARDROOM SESSION
  Advisors: Torvalds, Hotz, Carmack
  Agenda: Should we rewrite the auth system?
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

Advisors speak directly to you as "President", react to each other by name, interrupt, and challenge. Stage directions (*leans forward*, *shakes head*, *taps the table*) make it feel alive.

The session closes with an **Executive Summary** — consensus, tensions, recommended action, and risk of inaction.

### Directing the Room

After a session, you can:
- **"Call on Taleb"** / **"เรียก Taleb มาพูด"** — single-advisor deep dive
- **"Bring Bezos into the room"** / **"เพิ่ม Bezos เข้ามา"** — new voice enters and reacts
- **"Munger, elaborate"** / **"ขยายประเด็นของ Munger"** — expand one advisor's argument
- **"Who disagrees?"** / **"ใครไม่เห็นด้วย?"** — strongest contrarian enters the room
- **"Adjourn"** / **"ปิดประชุม"** — end with final summary

## The 22 Advisors

### Business & Leadership
| Name | Lens | Signature |
|------|------|-----------|
| Elon Musk | First principles | "Who made this requirement?" |
| Steve Jobs | Taste / design | "Tell me what's not working." |
| Jeff Bezos | Customer / ops | "Who is the customer?" |
| Charlie Munger | Mental models | "Invert, always invert." |

### Tech & Engineering
| Name | Lens | Signature |
|------|------|-----------|
| Linus Torvalds | Data structures / taste | "Talk is cheap. Show me the code." |
| John Carmack | Performance / focus | "Sometimes, the elegant implementation is just a function." |
| Andrej Karpathy | Pedagogy / first-principles | "What I cannot create, I do not understand." |
| George Hotz | Radical simplification | "You have never refactored enough." |

### Design & Creative
| Name | Lens | Signature |
|------|------|-----------|
| Dieter Rams | Reduction / honesty | "Less, but better." |
| Massimo Vignelli | Structure / systems | "If you can design one thing, you can design everything." |
| Hayao Miyazaki | Soul / emotion | "Does this feel alive?" |

### Finance & Investing
| Name | Lens | Signature |
|------|------|-----------|
| Warren Buffett | Patient value | "Price is what you pay. Value is what you get." |
| Ray Dalio | Systematic macro | "Pain + Reflection = Progress" |
| Nassim Taleb | Antifragility | "Wind extinguishes a candle and energizes fire." |
| Howard Marks | Second-level thinking | "The riskiest thing is the belief that there's no risk." |
| Morgan Housel | Behavioral wisdom | "Doing well with money has little to do with how smart you are." |

### Thai Business & Startup
| Name | Lens | Signature |
|------|------|-----------|
| Tan Passakornnatee (ตัน) | Guerrilla marketing / self-made | "ล้มเหลวได้ แต่อย่าล้มเลิก" |
| 9arm (นายอาร์ม) | Tech democratization | "ไม่มีใครเอาอะไรไปจากเราได้" |
| Top Jirayut (ท็อป) | Crypto nation-building | "กัดไม่ปล่อย" |
| Krating Poonpol (กระทิง) | Ecosystem building | "ไม่กล้าเปลี่ยน ก็ไม่มีวันโต" |
| Dhanin Chearavanont (ธนินท์) | Vertical integration / long-game | "ความสำเร็จ ดีใจได้วันเดียว" |
| Srettha Thavisin (เศรษฐา) | Brand building / lifestyle | "I'm not a PM, but Thailand's top salesman." |

## Key Tensions (Built-in Debate Fuel)

The skill automatically pairs advisors who disagree on the topic:

- **Rewrites**: Torvalds (never) vs Hotz (always) vs Carmack (profile first)
- **Concentration vs Diversification**: Buffett vs Dalio vs Taleb
- **Speed vs Patience**: Musk vs Munger vs Marks
- **Intuition vs Data**: Jobs vs Bezos vs Musk
- **Simplicity vs Systems**: Hotz vs Dalio vs Housel
- **Design Philosophy**: Rams (reduce) vs Vignelli (systematize) vs Miyazaki (feel it)
- **Thai: Build vs Sell**: Dhanin (vertical empire) vs Srettha (brand) vs Tan (guerrilla)
- **Thai: Ecosystem vs Solo**: Krating (build everything) vs Top Jirayut (own platform) vs 9arm (educate)
- **Thai: Patience vs Speed**: Dhanin (decades) vs Top Jirayut (bite and hold) vs Krating (Godzilla)

## How It Works

1. **Selection index** (~800 bytes) is always in context — zero tool calls to pick advisors
2. **Domain + keyword matching** narrows to 2-3 relevant advisors
3. **Tension injection** ensures opposing viewpoints when a known debate applies
4. **On-demand profile loading** — only selected advisors' full profiles are read (~3-5K each)
5. **Immersive boardroom output** with cross-talk, stage directions, and executive summary

Token budget per invocation: ~9K-23K (vs ~80K+ if all profiles were loaded).

## Customization

### Add your own advisor
1. Create a new `.md` file in `consultants/` following the existing format (frontmatter with title, domain, lens, signature + sections for Philosophy, Frameworks, Communication DNA, Advice Style, Best For)
2. Add a row to the Selection Index table in `SKILL.md`
3. Add relevant tensions to the Tension Injection table

### Modify an advisor
Edit their `.md` profile directly. The skill reads profiles at invocation time — changes take effect immediately.

## Structure

```
consult/
  SKILL.md              # Skill definition + selection logic
  SOUL.md               # Boardroom host personality
  README.md             # This file
  consultants/          # 22 deep-research profiles
    Elon Musk.md        # + Steve Jobs, Jeff Bezos, Charlie Munger
    Linus Torvalds.md   # + John Carmack, Andrej Karpathy, George Hotz
    Dieter Rams.md      # + Massimo Vignelli, Hayao Miyazaki
    Warren Buffett.md   # + Ray Dalio, Nassim Taleb, Howard Marks, Morgan Housel
    Tan Passakornnatee.md  # Thai: + 9arm, Top Jirayut, Krating Poonpol,
    Dhanin Chearavanont.md #        Srettha Thavisin
```

## License

MIT
