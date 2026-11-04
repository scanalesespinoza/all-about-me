# All About Me — Sergio Sebastián Canales Espinoza

This repository is the canonical source of truth about **who I am** as a professional, architect, community builder, and human being.
Its purpose is to provide **high-quality context** for:

- Writing talks, articles, and proposals
- Preparing CVs, role descriptions, and applications
- Grounding prompts for LLMs so they can generate work aligned with my experience, values, and style
- Letting an agent predict the decisions I would make, with explicit reasons and confidence
- Documenting my evolution over time as an architect and technology leader, CNCF Ambassador, and Platform Engineering Ambassador

---

## 👤 Who I Am (High-Level)

I am **Sergio Sebastián Canales Espinoza**, a **Senior Architect – Global Services at Red Hat** and technology leader with more than 12 years at **Red Hat** across two stages. I align architecture, delivery, and technology decisions with organizational priorities. My first lens is **architecture and continuous improvement**—turning constant technological change into strategic advantage, keeping technical debt deliberate, and guiding organizations toward long-term evolution.

scanales.com is my public home for this work, where I share ideas and stories with technology enthusiasts through talks, blog posts, and community events, extending the same mindset I apply to architecture and leadership.

Community comes next: I rely on developers, mentoring, and open source networks as the core fabric that sustains progress. As a **CNCF Ambassador** and **Platform Engineering Ambassador** since **2024**, I help communities grow across Latin America and beyond through organizing, speaking, and hands-on support.

AI-augmented development and **Cloud Native / Platform Engineering** are the toolkits I use to realize these goals: early, sustainable technology adoption, production-ready delivery, and dependable developer experience.

I focus on turning change into strategic advantage through:

- **Architecture & continuous improvement**
- **Community & people growth**
- **AI-augmented development & early tech adoption**
- **Cloud Native & Platform Engineering**

My core belief:
> Technology must empower people, improve their capabilities, and deliver real value to the organizations and communities they serve.

---

## 🎯 Repository Goals

This repository is designed to be:

1. **A living knowledge base about me**
   - Biography and professional journey
   - Core skills and domains of expertise
   - Projects, talks, and contributions

2. **A stable context layer for AI systems**
   - So LLMs can generate content that sounds like me
   - So prompts for coding, architecture, and writing can use a consistent, rich representation of my profile

3. **A foundation for future work**
   - Personal branding
   - Speaker submissions and CFPs
   - Career transitions and strategic opportunities

---

## 📂 Directory Structure

```text
biography/      # Narratives about my life, identity and professional evolution
career/         # Roles, responsibilities, milestones, career timeline
projects/       # Deep dives on key projects (EventFlow, arkit8s, PulseState, Wise Tech)
skills/         # Technical and non-technical skills, matrices, and domains
context/        # JSON / structured context for LLM grounding
community/      # Planned: open source, meetups, conferences, initiatives
philosophy/     # Personality, decision criteria, principles, way of working and thinking
decisions/      # Real past decisions with my reasons, and the evaluation protocol
interests/      # Planned: broader interests such as AI, fitness, storytelling, communities
speaking/       # Planned: talks, topics, conferences, abstracts
```

---

## 🧠 Current Status

Available today:

- Biography and identity: `biography/`
- Career timeline, Red Hat roles, and community leadership: `career/`
- Project deep dives: `projects/`
- Technical and leadership skills plus a machine-readable matrix: `skills/`
- Personality, decision criteria, priority ranking, and red lines: `philosophy/`
- Decision log and evaluation protocol: `decisions/`
- Agent entry point: `AGENTS.md`
- Structured LLM context: `context/context-base.json`

Planned next:

- More real decision cases.
- Community, interests, and speaking sections.

---

## 🤖 Using This Repo as LLM Context

Agents should start with [`AGENTS.md`](AGENTS.md), which defines the read order and the procedure for predicting a decision I would make.

Tools, prompts, and assistants can:

- Load `context/context-base.json` as a starting profile for "Sergio-aligned" tasks.
- Use `biography/`, `career/`, and `projects/` to enrich responses.
- Treat `career/timeline.md` as the canonical source for roles, titles, and dates.
- Use `philosophy/personality-and-decision-criteria.md` to anticipate the decisions and criteria I would apply.
- Respect my values, tone, and priorities when generating content.

This repo is, in short, "all about me": a stable and evolving foundation for everything I build, share, and lead.
