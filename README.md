# A2A Human-Aligned Extension

This repository proposes a structured extension to Google's A2A (Agent-to-Agent) protocol to support real-world, human-led programs and institutions using the G-O-S-R model (Goal → Obstacles → Solutions → Resources).

It defines agent structures such as `ProgramCard` and `operating_character` metadata blocks, allowing civic entities, nonprofits, governments, and grassroots programs to participate in agent ecosystems alongside LLM-based agents.

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
├── schema/                 # JSON Schemas for ProgramCard, metadata, etc.
├── examples/               # Sample AgentCards and use cases
├── diagrams/               # Visuals (optional)
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

- [Google A2A Protocol](https://a2a.dev) – Original agent communication protocol this project extends
- [G-O-S-R AI Workflow](https://github.com/team-earth/gosr-ai-workflow) – Team Earth's implementation of the G-O-S-R model for structured problem-solving with AI
- [Team Earth Data](https://github.com/team-earth/data) – Structured datasets for programs, agents, and metadata used in G-O-S-R and A2A-aligned workflows
- [G-O-S-R Model Overview](https://theunsolvable.org) – Conceptual foundation and use cases for Goal → Obstacles → Solutions → Resources
