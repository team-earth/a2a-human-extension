# A2A Human-Aligned Extension



This repository proposes a structured extension to Google's [Agent-to-Agent (A2A) protocol](https://google-a2a.github.io/A2A/specification/) to support real-world, human-led programs and institutions using the G-O-S-R model (Goal ← Obstacles ← Solutions ← Resources).

It defines agent structures like `ProgramCard`, `ParticipationTemplate`, and `operating_character` blocks—enabling civic and institutional actors to participate meaningfully in agent ecosystems alongside AI-based agents.

**📄 Read the full proposal:**  
👉 [doc/Extending-A2A-Human.md](doc/Extending-A2A-Human.md)


> **About Google A2A**  
> The Agent-to-Agent (A2A) protocol is an open, draft specification introduced by Google on April 9, 2025. It enables software agents—including AI models and automated systems—to communicate, share tasks, and coordinate action in a structured, interoperable way across platforms and organizations.

> **Why does A2A matter?**  
> A2A defines a shared language for software agents to collaborate automatically. This extension brings human-led programs—such as nonprofits, civic groups, and public institutions—into that ecosystem, enabling meaningful coordination between AI and real-world initiatives.

---

## 🔍 Purpose

- Extend A2A protocol to represent human-aligned entities  
- Support structured discovery and collaboration via AgentCards  
- Encode motivational, communicative, and governance metadata using recognized frameworks (e.g. Spiral Dynamics, Hofstede)

---

## 📂 Repository Structure

```
a2a-human-extension/
├── doc/                    # Core markdown spec and drafts
│   └── Extending-A2A-Human.md
├── papers/                 # Academic publications and presentations
│   ├── README.md
│   └── HLDM2025-A2A-Human-Extension.pdf
├── schema/                 # JSON Schemas for ProgramCard, metadata, etc.
├── examples/               # Sample AgentCards and use cases
├── diagrams/               # Visuals (optional)
├── CITATION.cff            # Citation metadata for academic use
├── VERSION.md              # Version history and changelog
├── LICENSE                 # MIT License (for schema/code)
├── LICENSE.docs            # CC BY-SA 4.0 License (for documentation)
└── README.md               # You're here
```

---

## 🧪 Status

- Current Version: `v0.1.3` (2025-06-08)  
- Draft status: Open for collaborative review  
- Target audience: Developers, civic technologists, public sector integrators

---

## 📝 Conference Presentation

A paper based on this work was presented at [HLDM'25](https://sml.disi.unitn.it/hldm25.html) on September 15, 2025 (ECML PKDD 2025, Porto, Portugal).

*"Integrating Civic Initiatives into AI Agent Ecosystems: A Human-Aligned Extension of the A2A Protocol"*  
[[PDF](papers/HLDM2025-A2A-Human-Extension.pdf)] · [[Direct download](https://github.com/team-earth/a2a-human-extension/raw/main/papers/HLDM2025-A2A-Human-Extension.pdf)] · [[Papers folder](papers/)]

---

## 📜 Licensing

- **Documentation**: [Creative Commons BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)  
- **Schema and code samples**: [MIT License](LICENSE)

---

## ✍️ Contributing

Contributions, comments, and critiques are welcome. Please:  
- Submit issues or pull requests via GitHub  
- Use the `doc/` folder for edits to the spec  
- Follow semantic versioning in `VERSION.md`

---

## 📬 Contact

Project lead: [Kevin Kells](https://kevinkells.com)  
For inquiries: [team.earth/contact](https://team.earth/contact)

---

## 🔗 Related Work

- [Google A2A Announcement Blog Post](https://developers.googleblog.com/2024/04/announcing-agent2agent-protocol.html) – Google's announcement introducing the A2A protocol

- [Google A2A Protocol Specification](https://google-a2a.github.io/A2A/specification/) – The original agent communication protocol this project extends  
- [G-O-S-R AI Workflow](https://github.com/team-earth/gosr-ai-workflow) – Team Earth's implementation of the G-O-S-R model for structured problem-solving with AI  
- [Team Earth Data](https://github.com/team-earth/data) – Structured datasets for programs, agents, and metadata used in G-O-S-R and A2A-aligned workflows  

---

## 📄 References

- **Voltan, A., & Kells, K. (2025).** *Moving the Needle on Wicked Problems: GenAI for Systems Thinking.*  
  Presented in the plenary session “AI & Collaboration” at the ASAC 2025 Annual Conference  
  (Technology and Innovation Management Division), University of Waterloo, May 19, 2025.

- **Kells, K. (2020).** *A Technology-Assisted Social Computing Framework for Solving Complex Social Problems.*  
  Presented in the Blue Sky Ideas Track at the AAAI Conference on Human Computation and Crowdsourcing (HCOMP 2020).  
  [Conference program](https://www.humancomputation.com/2020/program.html)

- **Kells, K. (2019, November 28).** *A Proposed Practical Problem-Solving Framework for Multi-Stakeholder Initiatives in SocioEcological Systems Based on a Model of the Human Cognitive Problem-Solving Process.*  
  [arXiv:1911.13155](https://arxiv.org/abs/1911.13155)
