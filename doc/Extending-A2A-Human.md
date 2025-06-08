# Executive Summary

This document proposes a practical extension of the Agent-to-Agent (A2A) protocol to better represent **human-led organizations and real-world programs** within decentralized, collaborative ecosystems. It addresses a key gap in current interoperability standards: while A2A excels at describing autonomous software agents, it lacks structures for modeling the nuanced, context-rich work of nonprofits, agencies, and coalitions implementing solutions to complex social challenges.

**Why is this needed?**  
Efforts to solve public problems are often fragmented and opaque. Existing models (like G-O-S-R: Goal, Obstacles, Solutions, Resources) help map the landscape of work, but do not richly describe the actors or the actual programs delivering impact. Meanwhile, A2A’s AgentCard format is powerful for digital agents, but does not natively capture the motivations, operational styles, or concrete deployments of human organizations.

**What will you learn?**

- The limitations of current A2A and G-O-S-R models for representing human actors and their work.  
- The rationale for introducing new metadata structures—**ProgramCard**, **operating\_character**, and **participation\_template**—to bridge this gap.  
- Multiple architectural options for integrating these concepts, and the trade-offs of each.  
- How these extensions can foster alignment, transparency, and voluntary collaboration—without central control or reductionist labeling.

**What next steps are invited?**

- Review and critique the proposed extensions and their schemas.  
- Experiment with implementing ProgramCards and operating\_character blocks in your own organizational metadata.  
- Contribute to the open development and governance of these standards.  
- Explore how these models can support more discoverable, inclusive, and adaptive problem-solving in your ecosystem.

---

## Key Components at a Glance

| Component | Purpose | Role in the Ecosystem |
| :---- | :---- | :---- |
| **AgentCard** | Describes an agent (human or AI), including identity, capabilities, and relationships | Core A2A unit; links actors to their declared abilities and metadata |
| **ProgramCard** | Represents a specific, contextualized program or workstream operated by an agent | Proposed extension; connects real-world implementations to agents; enables granular discovery and alignment |
| **operating\_character** | Encodes self-declared organizational style, motivation, and interaction patterns | Proposed extension; facilitates alignment, transparency, and trust-building between actors |
| **participation\_template** | Provides structured guidance on how to join, replicate, or support a program | Proposed extension; makes participation discoverable and actionable; supports replication and onboarding |
| **Resource** | A program, service, or effort implementing a Solution | G-O-S-R core; the “what is being done”; mapped to Solutions and Obstacles |
| **Actor** | The human-led entity (organization, coalition, etc.) implementing programs | G-O-S-R-A extension; the “who” behind Resources and Programs; aligns intention and action |

---

By extending A2A with these human-aligned structures, we aim to create a **public, interoperable map** of both digital and human efforts—one that supports decentralized alignment, richer discovery, and more effective collaboration across sectors.

*The following pages detail the reasoning, design options, and open questions for this approach. Your feedback and participation are welcome.*

## I.A — What Problem Are We Trying to Solve?

Amid the swirl of crises and initiatives that define our time — food insecurity, loneliness, environmental degradation, civic disengagement — it often feels like everyone is trying to help, and yet no one can quite see the whole. Organizations build programs. Governments fund services. Communities mobilize. But the system as a whole remains opaque, fragmented, and difficult to navigate or learn from.

The problem isn’t a lack of intelligence or goodwill. It’s a **lack of structured visibility**. We don’t have public tools for seeing how the efforts of many map onto what’s needed — or for discovering how we might align disparate, existing efforts towards a common goal .

This is where **G-O-S-R** comes in. It’s a framework for mapping collective efforts toward a shared **Goal** — a focused intention around which problem-solving can be organized. From that anchor point, G-O-S-R helps identify the **Obstacles** that stand in the way, surface actionable **Solutions**, and point to the real-world **Resources** — programs, services, or workstreams — that are already engaged in implementing those solutions.

The problem G-O-S-R aims to solve, then, is not how to coordinate everyone under one system. It’s how to make it possible for many actors to **see the landscape**, locate themselves in it, and act with informed autonomy.

We’re not trying to create control. We’re trying to create clarity.

## I.B — The Limits of Centralized Coordination

Across many fields, there’s a familiar pattern: when challenges become complex or large-scale, efforts often move toward coordination. Central offices are created, shared platforms are proposed, and structures are introduced to help bring alignment. This tendency can make sense — coordination may offer consistency, efficiency, or even safety in uncertainty.

Yet this pattern also raises questions. How well do centralized approaches hold up in contexts where needs and conditions vary widely? What happens when many actors — formal and informal, large and small — are trying to contribute in ways that don’t quite fit the central plan? How are visibility and participation shaped by the assumptions baked into a given structure?

In some settings, coordination might streamline decision-making or reduce redundancy. In others, it may introduce new forms of friction — delays, bottlenecks, or unintentional exclusion. Certain kinds of work may flourish when loosely coupled to a shared framework, while others may lose their relevance or responsiveness when required to conform.

These observations don’t point to a clear right or wrong. They suggest a tension worth examining. In efforts to make sense of complexity, how do different forms of structure — centralized or distributed — shape the way people see their role, or discover how their efforts relate to others?

This inquiry continues throughout the rest of this discussion.

## I.C — A Public Map for Distributed Alignment

If coordination is one response to complexity, another might be visibility. What if, rather than attempting to organize activity from above, the focus shifted toward helping efforts see one another? What forms of alignment might become possible if the landscape of work — goals, obstacles, efforts underway — were more legible to those who wish to engage?

In some fields, tools like public dashboards, open data portals, or community directories have tried to serve this role. They can offer a kind of shared reference point — a way to surface who is doing what, where, and sometimes why. But these tools often remain partial, static, or difficult to adapt across different domains. They may reflect data more than intent, and structure more than purpose.

Still, the idea remains intriguing: Could a more flexible, collectively understandable map help distributed actors orient themselves? Could such a map support reflection — both individual and shared — on how efforts relate, overlap, or leave gaps?

This is not necessarily about comprehensive tracking or evaluation. It may be more about offering structure to help people and organizations find their place in a larger pattern — not through mandates, but through perspective. In this way, alignment doesn’t need to be enforced. It might instead emerge from shared understanding.

## II.A — Overview of the G-O-S-R Structure

Between shared intentions and practical action, there is often a gap — not of will, but of structure. The G-O-S-R model offers one way of navigating that space. It does so not by prescribing solutions, but by helping people and organizations see how their efforts — or their potential contributions — relate to a focused path of change.

The model begins with a **Goal** — a clearly stated and bounded intention. While communities may hold many goals, G-O-S-R is meant to be applied one at a time, so that each instance of its use focuses on a specific future picture.

From that Goal, the process identifies **Obstacles** — the barriers that stand in the way. These might be structural, logistical, cultural, or informational. Critically, obstacles can be **broken down into smaller sub-obstacles**, making them more tractable. What initially seems unsolvable may reveal entry points when its components are made visible.

Next, G-O-S-R introduces **Solutions** — potential responses that could address one or more obstacles. These are not universal answers, nor must they already be in use. What defines a Solution is its relevance to a specific obstacle or sub-obstacle. In keeping the scope narrow, each solution can be clearer and simpler, increasing the likelihood that someone might choose to implement it.

That brings us to **Resources**. In this model, a Resource is a program, service, or effort that implements (or could implement) a given Solution. A Resource does not need to address the whole Goal or even solve a complete problem. Its relevance comes from **carrying out a particular Solution** — whether fully, partially, or experimentally. Importantly, Resources may already exist, or they may be **aspirational**. G-O-S-R creates a space where potential contributors — individuals, organizations, institutions — can find Solutions they might choose to take on.

This structure invites a different kind of engagement. Rather than asking, “Who is solving the big problem?” it asks, “Which part are you working on — or could you work on?”

Step by step, the landscape becomes more visible — and more navigable.

## II.B — How Resources Differ from Implementors

In the G-O-S-R model, a **Resource** is not an organization, a person, or a team — at least not directly. A Resource refers to a **program, initiative, or offering** through which a specific Solution is being (or could be) implemented. The entity responsible for that Resource — the actor that designs, runs, or supports it — is the **Implementor**.

This distinction matters for several reasons.

First, it helps focus the model on relevance. Many institutions run multiple programs, not all of which relate to a given Goal or its associated Solutions. By highlighting only the initiatives that implement relevant Solutions, G-O-S-R avoids overgeneralization and surfaces specific efforts that align with the problem at hand.

Second, it keeps the unit of analysis grounded in **work, not identity**. This framing allows for more modular thinking: different actors may implement similar programs; one actor may offer multiple distinct resources. It also opens space for **aspirational contributions** — work that could exist, even if no implementor has yet stepped forward.

There is also a subtler effect. When coordination systems are built around organizations or identities, they can unintentionally reinforce dynamics of visibility, competition, or control. Efforts may begin to orbit questions of who “owns” an area of work, who gets credit, or who deserves funding — even when the underlying goal is shared. By shifting the focus to Resources — defined by what they do, not who they belong to — G-O-S-R invites a softer form of alignment. One that emphasizes contribution, not position.

This does not remove the need for clear actors or accountability. It simply reframes how shared work can be seen — not as a map of organizational turf, but as a collection of ongoing, interconnected efforts that others might learn from, adapt, or join.

## II.C – Why Alignment Matters More Than Orchestration

Orchestration implies central control: a conductor assigning parts, a planner issuing directives. But the scale and diversity of real-world actors — nonprofits, community groups, agencies, volunteers — defy that model.

Alignment, by contrast, is lightweight. It does not require shared leadership, only shared understanding. When actors see how their efforts fit into a broader picture — even one they didn’t draw — they can voluntarily align.

This is the promise of the G-O-S-R model: by clearly naming the **Goal**, breaking down the **Obstacles**, proposing **Solutions**, and surfacing relevant **Resources**, it provides just enough structure to make alignment possible — without imposing control.

Rather than directing behavior, it invites contribution. Rather than consolidating power, it distributes opportunity. And by decoupling participation from permission, it supports action at the edges — where innovation often begins, and where often the largest portion of the community find a match of what needs to be done with what they are able to do

## III.A — The Limits of G-O-S-R in Representing Actors

The G-O-S-R model is designed to clarify work. It helps surface what a focused effort is trying to achieve, what’s getting in the way, what might be done about it, and what efforts are already doing part of that work. This has proven useful for mapping local initiatives, identifying gaps, and discovering overlooked programs.

But G-O-S-R, by design, **does not attempt to fully represent the actors themselves** — the individuals, organizations, or coalitions implementing the work. It describes Resources in relation to Solutions, but does not provide a rich vocabulary for the nature, structure, values, or capacities of those who bring those Resources into being.

This limitation can be constructive. By focusing on actions rather than actors, G-O-S-R avoids reinforcing institutional hierarchies or visibility biases. It keeps the emphasis on contribution rather than identity.

Still, there are moments when this actor-level context becomes important. For example:

* A funder may want to know not just *what* is being done, but *who* is doing it and whether they are capable of sustaining it.  
    
* A potential collaborator might seek alignment not only in goals but in values, governance, or communication style.  
    
* A program that appears promising may hinge on the credibility, legitimacy, or lived experience of the implementor.

Without a shared way to represent these aspects of human and institutional actors, the model can miss important dimensions of interoperability and trust.

G-O-S-R gives us a map of work. But to navigate that map in real-world settings — especially when forming new partnerships or evaluating readiness — we also need a structured way to describe the **actors behind the efforts**. This is where the Agent-to-Agent (A2A) protocol begins to offer new possibilities.

## III.B – What G-O-S-R Already Captures About Actors

Even though the G-O-S-R framework was designed to highlight the work rather than the worker, it does include some information about who is doing that work. The Resource entries in G-O-S-R datasets typically name the organization running the program, sometimes along with a contact person, service area, or eligibility criteria. These fields offer a thin layer of actor metadata — enough to point toward an implementor, but not enough to understand or know how best to interact with them.

This lightweight metadata reflects the G-O-S-R principle of **focusing on solutions, not identities**. It avoids the trap of reinforcing brand-centric or institution-centric thinking and instead surfaces programs based on what they are doing, not who they are. In doing so, it creates room for new actors to step into existing solution spaces and invites alignment without demanding affiliation.

However, there are real limits to how far we can get with this minimal approach. When multiple resources appear to offer similar services, users often want to know more: Who runs this? What’s their philosophy? Are they credible, inclusive, stable, well-resourced? Are they locally embedded or nationally scaled? In the absence of structured ways to answer these questions, judgments default to familiarity or branding — which risks reinforcing inequalities in visibility and trust.

In short, G-O-S-R already points toward actors, but it doesn’t yet describe them. To move from mapping the work to understanding the working landscape, we need a new representational layer. Fortunately, one may already exist.

## III.C – What Is A2A and What Does It Offer?

On April 9, 2025, Google introduced the **Agent-to-Agent (A2A)** protocol to enable communication between AI agents in a decentralized ecosystem. At its core, A2A provides a structured, lightweight format for representing agents — including their identity, capabilities, preferences, and relationships — in a way that can be read and understood by other agents (and by humans).

The central unit of representation in A2A is the **AgentCard**, a JSON-based profile that describes what an agent is and what it offers. AgentCards are designed to be:

* **Self-declarative** — Agents describe themselves rather than relying on external registries.  
    
* **Modular** — Capabilities, skills, and relationships are described in extensible blocks.  
    
* **Interoperable** — Designed to be understood across systems, agents, and use cases.

AgentCards typically include fields such as:

* name, description, and contact info  
    
* capabilities\[\]: high-level actions or services the agent can perform  
    
* skills\[\]: more detailed technical or procedural competencies  
    
* relationships\[\]: optional links to other agents for collaboration, hierarchy, trust, etc.

Though originally intended for computational agents (e.g. AI bots, LLM-based tools, and serviceful automations), the A2A format quickly revealed itself to be more broadly useful. Its simplicity, openness, and low barrier to entry make it appealing as a **general-purpose metadata layer** — not just for bots, but potentially for any entity that wants to declare “Here’s who I am, here’s what I can do, and here’s how to engage with me.”

This possibility opens a door: could human-based organizations — such as nonprofits, government agencies, or local collectives — also be described using AgentCards? If so, the A2A format might offer a ready-made foundation for expanding G-O-S-R’s representational limits, without reinventing the wheel.

But there are caveats. As we’ll see next, the A2A protocol was built with a specific type of agent in mind — and it makes certain assumptions about intent, autonomy, and service delivery that don’t always translate cleanly to human-led programs or institutions.

## III.D – Why Non-Computational Actors Might Fit the A2A Frame

Despite being originally designed for autonomous AI agents, the A2A format is surprisingly well-suited to describing human-led organizations — including nonprofits, local agencies, cooperatives, and other collective actors. Why? Because many of the same questions we ask about bots are the ones we also ask about human entities:

* What do you do?  
    
* How do you do it?  
    
* What are you good at?  
    
* Who else do you work with?  
    
* How can others discover and align with you?

These questions map cleanly to A2A’s AgentCard schema. A nonprofit running a food distribution program, for example, might describe its capabilities in terms of logistics, outreach, and eligibility screening. A city agency might list skills related to case management or legal documentation. A grassroots coalition might use the relationships block to point to trusted partners or shared protocols.

In this sense, the AgentCard becomes a **portable, machine-readable persona** for human institutions — one that supports discovery, matching, and coordination without requiring centralization or gatekeeping.

There are deeper reasons this fit works:

* **Declarative self-description** respects organizational autonomy and avoids reductive categorization.  
    
* **Capability-based modeling** emphasizes what the entity can offer, not just what sector it belongs to.  
    
* **Extensibility** allows for custom fields that capture domain-specific or cultural nuance.  
    
* **Interoperability** makes it easier for humans and machines alike to navigate a diverse ecosystem of actors.

That said, there are limitations. The A2A protocol doesn’t natively include concepts like **programs**, **implementations**, or **context-specific deployments** — all of which are central to G-O-S-R’s model of real-world work. Nor does it yet provide mechanisms for describing **organizational motivations**, **governance structures**, or **epistemic orientation** — elements that may be crucial for meaningful alignment between human actors.

Still, the overlap is substantial. With modest extensions, the A2A format can be adapted to accommodate human-led agents in a respectful, structured, and interoperable way. Rather than starting from scratch, we can build on what exists — and enrich it to represent the complexity and intentionality of human-centered work.

# IV. Modeling Human Agents: Beyond Individuals

## IV.A – Why Individuals Are Not Our Modeling Target

As we begin to extend A2A to support human actors, a critical design choice comes into focus: **we are not aiming to model individual people**. This is a principled decision, rooted in both ethical caution and functional clarity. While A2A technically allows any autonomous agent to generate an AgentCard — and that could include an individual human — we consciously choose to prioritize **entities** made up of humans rather than individuals themselves. These include nonprofit organizations, public agencies, for-profit enterprises, educational bodies, civic and neighborhood coalitions, informal collectives, hybrid structures like cooperatives and public-private partnerships, labor and professional associations, charitable groups, and faith-based institutions—groupings that, despite their varied forms, operate as relatively durable, semi-public actors in the social landscape.

There are several reasons for this design boundary:

1. **Privacy and Risk:** Modeling individuals risks revealing sensitive personal information or enabling unwanted profiling. This concern grows sharper when metadata includes values, motivations, and capabilities — dimensions that, for humans, are often private or fluid.  
     
2. **Labeling and Identity Politics:** Assigning behavioral or motivational tags to individuals can easily slip into stereotyping or overgeneralization. Group-level modeling provides a safer and more respectful abstraction.  
     
3. **Stability and Alignment:** Organizations, even informal ones, tend to have more consistent offerings, missions, and decision-making structures. That makes them easier to describe usefully — and easier for others to align with.  
     
4. **Avoiding Competition Framing:** Modeling individuals directly can unintentionally reinforce zero-sum thinking — who gets the grant, who gets the praise, who counts. Modeling group-level actors shifts attention toward the work itself.  
     
5. **Interoperability with G-O-S-R:** In our model, the point of describing actors is to connect them to the **work they implement**. Programs and services typically emerge from collaborative, institutional, or civic efforts, rather than remaining the domain of isolated individuals. Modeling the entity behind the program keeps the link to the Resource meaningful and actionable.

This doesn’t mean individuals are excluded from participation. They lead, contribute to, and initiate entities. But the unit of representation — the "Agent" in A2A — should reflect **the structure that holds the work**, not merely the person who touches it.

## IV.B – Who We Do Include: Nonprofits, Government Agencies, Collaboratives, etc.

While we intentionally avoid modeling individual humans, we cast a broad and inclusive net when it comes to modeling human-based groupings. Our working definition of a “human agent” includes any semi-stable, identity-bearing entity composed of people who can initiate, maintain, or participate in a programmatic effort aligned with a Solution in the G-O-S-R model.

This includes, but is not limited to:

* **Nonprofit organizations** — from large, mission-driven institutions to smaller service providers.  
    
* **Government agencies** — at city, county, state, or federal levels, as long as they manage or co-manage Resources.  
    
* **For-profit enterprises** — when offering products or services relevant to public-facing Solutions.  
    
* **Educational institutions** — such as universities, schools, or research centers, particularly when they operate public programs or service partnerships.  
    
* **Civic and neighborhood coalitions** — community-level efforts organized around place-based issues or public engagement.  
    
* **Informal collectives** — unincorporated groups that act together to implement a Solution or support a shared initiative.  
    
* **Hybrid structures** — such as cooperatives, public-private partnerships, or mission-driven businesses with blended governance.  
    
* **Labor and professional associations** — including unions and credentialing bodies working to advance shared economic or professional interests.  
    
* **Charitable groups** — including foundations, aid organizations, and direct-relief providers.  
    
* **Faith-based organizations** — when they engage in public service, education, or advocacy in alignment with a Solution.  
    
* **Cross-sector collaborations** — multi-entity teams formed around shared goals or coordinated program delivery, often combining nonprofit, governmental, and private actors.

What these entities have in common is not their legal status or sector, but their role as **initiators and stewards of work**. In G-O-S-R terms, they are not Resources themselves — but they implement them. They are the actors behind the action.

We do not require formal incorporation, nonprofit status, or official recognition to qualify as a human agent. What matters is coherence: a name, a purpose, and a group of people acting together over time with the ability to take action and declare intent.

This approach lowers the barrier to participation while anchoring our metadata in entities that are meaningful to align with — whether large and institutional or small and emergent.

Next, we’ll look at how we might describe these human agents using structured frameworks that capture their distinctive qualities.

## IV.C – Frameworks for Describing Human-Based Entities

Once we open the door to representing human-led entities in structured ways, we encounter a powerful question:  
**How can we meaningfully describe these entities — not just what they do, but how they operate, think, and relate to others?**

To answer this, we turn to established frameworks from psychology, organizational behavior, and intercultural studies — systems already in use to support leadership, teaming, and collaboration. These frameworks offer structured vocabularies for describing communication styles, motivations, decision-making approaches, and cultural assumptions — all of which can influence how a human-based agent functions and interacts.

Some of the most relevant include:

* **Spiral Dynamics** – A framework for understanding motivational systems based on values and worldview. It categorizes entities (or cultures) using “vMemes” like Blue (order-driven), Orange (achievement-driven), Green (community-driven), and so on. Useful for surfacing **core motivations** and social assumptions.  
    
* **Insights Discovery** – A color-based system (Red, Blue, Yellow, Green) reflecting communication and interaction styles, derived from Jungian typology. Helpful for expressing **interface style** — how an entity may communicate or engage with others.  
    
* **MBTI / 16 Types / Big Five** – Personality-based systems that may be abstracted to organizational tendencies (e.g., are decisions more data-driven or intuition-based?). These are controversial at the individual level but can surface shared **cognitive or strategic preferences** when applied carefully to teams.  
    
* **Hofstede’s Cultural Dimensions** – Used internationally to describe cultural orientation along axes like individualism vs. collectivism, power distance, and uncertainty avoidance. Useful for understanding **cultural context and governance patterns**.  
    
* **The Enneagram (organizationally applied)** – Offers nine motivational archetypes that some organizations use to reflect on core drives and behaviors.

Each of these systems brings strengths and risks. Used transparently and voluntarily, they can help surface differences in **approach, tone, decision-making, and collaboration readiness** — especially in cross-sector or multicultural contexts. They also provide **interoperability scaffolding** — enabling machine-readable expressions of "fit" or compatibility, without forcing convergence or sameness.

For example, a grassroots collective with a strong Green-Blue Spiral Dynamics profile might state a preference for relational and consensus-based collaborations. A high-Red Insights-style agency may favor clear directives and tight timelines. Neither is better — but knowing this upfront helps reduce friction and increase trust.

These frameworks can also signal **intentional self-awareness**: when a group describes its motivational or communication style, it invites others to engage more respectfully and productively.

Still, we must tread carefully. Overuse of typology can lead to stereotyping or shallow sorting. In the next section, we’ll propose a flexible, opt-in metadata block — called operating\_character — to encode these frameworks while guarding against misuse.

## IV.D – The operating\_character Block

To encode the structured yet respectful representation of human-based entities, we propose a new optional metadata section within the AgentCard: the operating\_character block.

This block is designed to hold **declared self-descriptions** about how a human entity operates — not in terms of tasks or services (that’s handled in capabilities and skills), but in terms of **motivational orientation, communication style, governance tendencies, and epistemic stance**. In other words: *how this actor thinks, relates, and decides*.

**Key properties of operating\_character:**

* **Framework-Based**: The block is composed of one or more entries that each use a recognized system (like Spiral Dynamics or Insights Discovery) to describe the entity’s internal style.  
    
* **Self-Declared**: Only the agent (or its authorized stewards) can declare or modify its own operating\_character.  
    
* **Optional and Extensible**: The entire block is optional, and frameworks can be added over time. There is no mandated list.  
    
* **Multi-framework Support**: Entities can include multiple framework entries if they feel that more than one system contributes to a well-rounded profile.

**Example (illustrative only):**
```
"operating_character": {
  "version": "2024.1",
  "effective_date": "2024-05-01",
  "expires": "2025-05-01",
  "declared_by": "operations_team",
  "spiral_dynamics": {
    "blue": 0.3,
    "green": 0.6,
    "yellow": 0.1
  },
  "insights": {
    "profile": {
      "yellow": 0.5,
      "green": 0.3,
      "red": 0.15,
      "blue": 0.05
    },
    "notes": "Primarily ideation- and people-oriented, with some assertive and compliance-driven traits."
  },
  "governance_style": "distributed_consensus",
  "epistemic_orientation": {
    "primary": "community-grounded",
    "secondary": "practice-informed"
  }
}
```

In this example:

* The entity presents a **Green-leaning Spiral Dynamics profile**, with additional influence from Blue (structure and duty) and Yellow (adaptability and systems thinking).  
    
* Its **Insights temperament** is a **blended profile**, primarily Yellow (idea-driven and relational), with Green (empathetic), Red (assertive), and minor Blue (compliant) traits — indicating a flexible but action-capable team dynamic.  
    
* It operates with a **distributed consensus governance model**, favoring shared authority and participatory decision-making.  
    
* Its **epistemic orientation** is **community-grounded** and **practice-informed**, prioritizing lived experience and iterative learning over abstraction.  
    
* The operating character is **versioned** and **temporally bounded**, providing a snapshot of the organization’s internal posture and interaction style for a specific time window.

Together, this tells a nuanced story: not just what the organization does, but how it moves through the world.

This block is not meant to be exhaustive, prescriptive, or permanent. Rather, it serves as an **interoperability aid**: a way for agents (human or AI) to better understand what working with this entity might feel like — and how best to align or engage.

In the next section, we’ll examine how to keep such profiling from becoming reductive or exclusionary — and how to incorporate reflexivity and caution into the design.

## IV.E – Guardrails Against Reductionism and Misuse

As promising as the operating\_character block may be for increasing alignment, it also invites a serious ethical responsibility: **preventing reductive use, stereotyping, or exclusionary dynamics**.

Any attempt to categorize human organizations — especially using frameworks drawn from psychology or culture — carries the risk of misapplication. Without care, what begins as a declaration of intent can morph into a filter for legitimacy, an excuse for exclusion, or a tool for bias reinforcement.

To counter these risks, we propose several key **design guardrails**:

**1\. Reflexivity Is Encouraged**

Each framework-supported description should be treated as **situated and interpretive**, not static or "true." Wherever possible, entities should accompany framework entries with short human-readable notes (e.g., "interpretation\_note": "We use Spiral Dynamics as a reflection tool, not a label.").

This invites others to read the metadata with humility — and to remember that human systems evolve.

**2\. No Required Framework**

Participation in operating\_character is completely optional. There are no required systems, no minimum number of entries, and no "default" values. This protects entities that may be culturally averse to typology, prefer informal representation, or lack the time or confidence to self-describe in these terms.

**3\. Interpretation-Free Matching**

The operating\_character block is not a ranking mechanism. It is not intended to be used by search engines or discovery algorithms as a compatibility filter without explicit, opt-in logic. Human actors should remain discoverable by what they offer (Resources, Capabilities) — not how they score on motivational profiles.

**4\. Extensibility with Accountability**

The list of acceptable frameworks should grow via transparent versioning and open-source contribution, not closed standardization. For each added framework, documentation should include:

* Who created it and why?  
    
* How is it interpreted in different cultures?  
    
* Known risks of misuse or misrepresentation.

**5\. Support for Reinterpretation and Evolution**

Organizations change. New leadership, shifting missions, or emerging contexts may alter an entity’s style or stance. To reflect that, AgentCards can version their operating\_character block and retain change history if desired — signaling that identity is not frozen.

**6\. Encouraging Non-Formal Voice**

The system should explicitly welcome **soft narrative self-descriptions**, not just structured tags. A plain-language "about\_how\_we\_work" field can be offered alongside operating\_character to provide context, story, and tone in human terms.

---

Ultimately, our goal is **not** to predict or classify behavior, but to support understanding — especially in contexts of partnership, trust-building, and shared problem-solving. Just as open data invites accountability, open character invites **self-aware alignment**.

Next, we turn from the actors themselves to the **work they implement** — and a gap in the A2A model that G-O-S-R is positioned to help fill.

# V. The Missing Link: Programs as Real-World Implementations

## V.A – Capabilities vs. Deployed Workstreams

A2A’s capabilities and skills blocks allow agents to declare what they can do — and in many AI and service-automation contexts, that’s enough. Capabilities serve as a menu of potential behaviors. Skills specify technical affordances. Together, they describe **what an agent is able to do** under the right conditions.

But for human-based agents — particularly those participating in the G-O-S-R model — this isn’t sufficient.

What we care about most is **what is actually being done**, here and now, in the real world. We need to describe not just capacity, but **implementation** — the active, concrete programs that are delivering value, responding to needs, or addressing recognized Obstacles.

We might say it this way:

A capability describes a potential.  
A program describes a commitment.

Where G-O-S-R centers its resource mapping on programs-as-implemented-solutions, A2A lacks a native structure for **representing workstreams in context**. This makes it difficult to connect:

* An implementor (the actor),  
    
* With a Solution (as defined by an upstream problem structure),  
    
* Via a program (the real-world expression of that implementation).

In our existing G-O-S-R data model, Resources are not just records of organizations — they’re entries for **specific programs**. Often, the same organization appears more than once because it operates multiple programs, each aligning with different Solutions.

To carry this forward into A2A, we need a way to **declare not just what an agent can do, but what it is doing** — ideally with enough detail to allow matching, evaluation, and distributed coordination.

In the next section, we’ll explore why this concept is missing from A2A — and why it may have been omitted by design.

## V.B – Why A2A Doesn’t Model Implementation

The absence of a built-in concept of *programs* in A2A appears to be a **deliberate design choice**, not an oversight. The protocol was created to enable decentralized discovery and communication among autonomous agents — especially software-based agents — whose capabilities are often invoked on demand and dynamically composed.

In that world, the focus is on **what an agent can do** — its declared capabilities and skills — rather than on **what it is currently doing**. The assumption is that deployments are ephemeral or outside the protocol’s scope: an agent declares what it offers; what happens next is negotiated at runtime.

For many computational agents, this is appropriate. A large language model might advertise summarization and translation skills, but it doesn’t need to describe each ongoing job. Its metadata is stable and general-purpose.

However, for **human-based agents** — particularly those embedded in public services, civic initiatives, or nonprofit delivery systems — this assumption breaks down. What matters most is not just what an organization *can* do in principle, but **what it is actively implementing** in the world.

G-O-S-R is built around this idea. Its Resources are not abstract representations of capacity; they are **real-world programs**, situated in context:

* Time-bound (e.g. open weekdays 10–4),  
    
* Place-bound (e.g. serving a specific neighborhood),  
    
* Criteria-bound (e.g. income-eligible households only),  
    
* and often attached to collaborative, cultural, or value-based constraints.

This specificity is essential for:

* Matching available services to real-world needs,  
    
* Highlighting implementation gaps in a distributed problem map,  
    
* Empowering new actors to align with existing work — or to fill voids.

Because A2A does not natively model implementation, it leaves a gap between **agent metadata** and **on-the-ground activity**. Whether by design or by deferral, this gap matters — particularly for frameworks like G-O-S-R that prioritize understanding and aligning with deployed workstreams.

This doesn’t necessarily mean A2A must change. It may mean we need to **layer additional concepts onto it**, or create lightweight extensions that preserve interoperability while introducing real-world grounding.

In the next section, we explore why that additional layer — a way to name and describe active programs — is vital to G-O-S-R’s theory of alignment.

## V.C – G-O-S-R Needs Named, Contextualized Programs

At the heart of the G-O-S-R model is a simple, powerful shift:  
**We don’t just map who exists — we map what is being done.**

In this model, the fundamental unit of relevance is not the agent, the organization, or the individual. It’s the **program**: a specific implementation of a potential Solution that addresses a defined Obstacle on the path to a shared Goal.

This shift carries several implications:

**1\. Programs Are the Actual Interface with the World**

Programs are where theory meets practice. They reflect decisions about design, delivery, target populations, resource constraints, and operational values. By describing these with precision — including hours, eligibility, geography, modality, and stage of development — we enable a deeper form of alignment than abstract capability matching.

**2\. Programs Create a Many-to-Many Relationship Between Entities and Solutions**

The same entity may run multiple programs, each aligned with different Solutions. Likewise, a single Solution may be implemented by many programs run by different actors. Without named, contextualized programs, this richness is lost — or flattened into a single, hard-to-interpret profile.

**3\. Programs Can Invite Participation**

Because G-O-S-R maps Resources that implement Solutions derived from Obstacles, it allows *gaps* to be visible. When a Solution is named but has no implementing program, the map acts as an invitation: "This work is needed. Who can step in?" In that sense, programs are not only descriptive — they are **generative**.

**4\. Programs Decouple Recognition from Formal Identity**

By centering the program, G-O-S-R allows informal collaborations, cross-agency efforts, or even family- or community-led initiatives to be listed — even if their parent entity lacks incorporation or infrastructure. This decentralizes visibility while preserving accountability through contextual metadata.

**5\. Programs Enable Realistic Aggregation**

If we want to assess what’s being done on the ground — not just who exists — we need program-level data. This enables localized analysis, equitable funding models, targeted partnership-building, and better system-level feedback.

In short, programs are not an afterthought. They are the **active threads of implementation** in the G-O-S-R map. To make this model actionable — and interoperable with systems like A2A — we need a place for these threads to be named, structured, and discoverable.

In the next section, we’ll explore multiple architectural options for how this could be accomplished — including both **extensions to A2A** and **layered approaches** that keep protocols separate but connected.

# VI. Competing Proposals: Where Do Programs Live?

The need to represent real-world programs within an A2A-compatible ecosystem is clear. But **how** we do that is an open design question — and the answer depends on how much we want to **extend**, **adapt**, or **layer** on top of the existing A2A protocol.

In this section, we examine several structural options, beginning with the most conservative.

## VI.A – Option 1: Programs Embedded in AgentCard (programs\[ \])

One option is to treat *programs* as a **property of the agent**, encoded directly within the existing AgentCard structure as an optional array. Each entry would represent a named, contextualized implementation the agent is currently offering.

This could look something like:

```
"programs": [
  {
    "name": "Fresh Start Housing Navigator",
    "description": "Provides support for housing-insecure families in Wards 7 and 8.",
    "aligned_solution": "affordable_housing_access",
    "status": "active",
    "geography": ["DC_Ward_7", "DC_Ward_8"],
    "modality": "in_person",
    "eligibility": "families_with_children",
    "delivery_partners": ["FaithCo Housing Fund", "Urban Roots Collective"]
  }
]
```

This model keeps everything under a single agent identity. The programs are **subcomponents** of the agent — tightly coupled to its card and governance. This mirrors how many real-world orgs operate: they maintain a central identity and portfolio of offerings.

**Advantages:**

* **Simple and familiar** — follows the structure of existing A2A fields like capabilities.  
    
* **No new object type needed** — programs are treated as metadata.  
    
* Keeps the agent-card-first philosophy intact.

**Limitations:**

* Difficult to share or reference programs independently.  
    
* Programs cannot easily be **co-owned** or federated across multiple agents.  
    
* Doesn’t support program-level versioning, status tracking, or discovery independent of the agent.

This model may work well for small orgs with a single service line — but becomes brittle when programs are collaborative, complex, or dynamic. For that reason, it may not be sufficient for the kinds of distributed solution ecosystems G-O-S-R aims to support.

In the next subsection, we’ll consider the opposite approach: treating each program as an agent in its own right.

## VI.B – Option 2: Programs as Standalone Agents

Another approach is to treat each **program as its own agent** — effectively giving it a distinct AgentCard with a unique identifier, independent metadata, and its own lifecycle.

Under this model, the program *is* the agent. It can declare capabilities, express operating characteristics, describe alignment with a Solution, and participate in discovery directly.

For example:
```
{
  "@type": "AgentCard",
  "id": "program:dc-fresh-start-housing",
  "name": "Fresh Start Housing Navigator",
  "description": "Provides support for housing-insecure families in Wards 7 and 8.",
  "operating_character": { "spiral_dynamics": { "green": 0.7 } },
  "capabilities": ["housing-navigation", "referrals", "case-management"],
  "aligned_solution": "affordable_housing_access",
  "parent_agent": "agent:urban-roots-collective"
}
```

This structure allows the program to be addressed, referenced, versioned, and understood **independently** of the entity running it. In effect, each program becomes a **first-class participant** in the A2A ecosystem.

**Advantages:**

* Fully expressive: each program can carry its own metadata, skills, and operating context.  
    
* Supports collaborative or multi-stakeholder programs — ownership can be abstracted or co-declared.  
    
* Enables direct alignment to a Solution and Obstacle within G-O-S-R.

**Limitations:**

* Breaks the conceptual model of agents as **intentional, autonomous actors**. Programs are typically *expressions* of an agent’s will — not agents with independent agency.  
    
* Can clutter the ecosystem: if every program is an agent, the agent-space may become crowded and hard to reason about.  
    
* May require additional logic to trace relationships between parent orgs, funders, or stewards.

This model maximizes **addressability** and **granular discovery**, but it also risks collapsing the distinction between **actor** and **activity**. That blurring may confuse or even conflict with the original intent of A2A’s agent structure.

In the next section, we explore a possible middle path — one that introduces a new object type to preserve the distinction between programs and agents while still enabling integration.

## VI.C – Option 3: New ProgramCard Object

Rather than forcing programs into the AgentCard structure or promoting them to agent status themselves, a third option introduces a new type: the **ProgramCard**.

This object would represent a program or workstream as a **distinct but non-autonomous entity**. It is not an agent in the A2A sense, but a **declarative artifact** associated with one or more agents. It exists to describe *what is being done* — in enough detail to enable discovery, analysis, and alignment — without implying that the program is independently capable of action or communication.

Here’s a simplified example:
```
{
  "@type": "ProgramCard",
  "id": "program:dc-fresh-start-housing",
  "name": "Fresh Start Housing Navigator",
  "description": "Housing support for families in DC Wards 7 and 8.",
  "aligned_solution": "affordable_housing_access",
  "operated_by": ["agent:urban-roots-collective"],
  "status": "active",
  "delivery_modality": "in_person",
  "eligibility_criteria": ["income_below_AMI", "must_have_children"],
  "geography": ["DC_Ward_7", "DC_Ward_8"],
  "tags": ["housing", "navigation", "community-based"]
}
```

This approach offers a **layered architecture**:

* The **AgentCard** retains its clean design, focused on who the actor is and what it can do.  
    
* The **ProgramCard** captures how the agent expresses that potential in the real world.  
    
* The relationship is clearly defined via links such as operated\_by or affiliated\_with.

**Advantages:**

* Preserves conceptual clarity: agents act, programs are expressions of action.  
    
* Enables granular discovery of programs without bloating the agent registry.  
    
* Allows programs to be co-owned, federated, versioned, or referenced independently.  
    
* Integrates naturally with G-O-S-R’s model of Resource listings as contextualized implementations of Solutions.

**Limitations:**

* Requires a modest extension to the A2A ecosystem (a new object type).  
    
* Not usable by default in existing tooling unless extensions are supported.  
    
* May introduce complexity if not carefully governed or documented.

This model may offer the **best of both worlds**: fidelity to real-world structure and alignment with A2A’s agent-centric architecture. It also opens the door to richer metadata standards, allowing programs to evolve, declare impact, or connect to obstacles and solutions in a public map.

In the next subsection, we’ll explore one final approach: **not extending A2A directly at all**, but instead layering G-O-S-R’s program logic alongside A2A through a lightly-coupled bridge.

## VI.D – Option 4: Overlay G-O-S-R on Top of A2A

Instead of modifying or extending the A2A protocol directly, a final option is to **build an overlay**: maintain G-O-S-R’s existing data structures — including programs, solutions, and obstacles — and link to A2A’s AgentCards through simple references or bridges.

In this model, the G-O-S-R ecosystem acts as a **complementary layer**:

* It preserves its own JSON structures, focused on programs and their alignment with specific problems.  
    
* Where relevant, it links programs to implementors described in A2A AgentCards via agent\_ref or agent\_id fields.  
    
* It respects the boundaries of A2A as a protocol for agents — while layering in contextual grounding through G-O-S-R’s lens.

An example G-O-S-R Resource entry might include:
```
{
  "program_name": "Fresh Start Housing Navigator",
  "solution_id": "affordable_housing_access",
  "description": "In-person support for families seeking housing in Wards 7 and 8.",
  "agent_ref": "a2a://agent/urban-roots-collective",
  "eligibility": "families with children under 18",
  "geography": ["DC_Ward_7", "DC_Ward_8"],
  "status": "active"
}
```

Here, G-O-S-R defines the **program**, while A2A defines the **actor**. The two systems remain decoupled — but interoperable.

**Advantages:**

* **Maximally respectful** of A2A’s original boundaries and purpose.  
    
* Allows G-O-S-R to evolve its own richer program ontology without friction.  
    
* Keeps systems modular — useful for evolving ecosystems with different update cycles or design authorities.  
    
* Enables experimental metadata to flourish without requiring protocol-level standardization.

**Limitations:**

* Discoverability and indexing become more complex unless bridges are well-maintained.  
    
* Some duplication may occur, particularly around eligibility, geography, or intent.  
    
* Tooling must be built to interpret the overlay, reducing plug-and-play reuse of existing A2A libraries.

This option may be best suited for early experimentation or environments where **protocol purity matters**, but it also introduces more friction for developers seeking a unified system.

Still, it reinforces a key value behind both A2A and G-O-S-R: **interoperability without overreach**. Systems can work together without becoming each other.

With these options on the table, we can now reflect on what kind of coordination philosophy we actually want — and why G-O-S-R was never meant to be a coordination protocol in the traditional sense.

# VII. Philosophical Alignment: Decentralized Discovery, Not Coordination

## VII.A – Why G-O-S-R Is Not a Coordination Protocol

At a glance, G-O-S-R’s structured representation of Goal, Obstacles, Solutions, and Resources may resemble a planning or coordination framework — a kind of blueprint for organizing action across a system. But this would be a misunderstanding.

G-O-S-R is not designed to **coordinate**. It is designed to **illuminate**.

Traditional coordination frameworks often involve:

* Assigned roles  
    
* Shared timelines  
    
* Central authorities or coalition conveners  
    
* Performance metrics tied to orchestrated outcomes

By contrast, G-O-S-R deliberately avoids centralization. It does not assign tasks. It does not adjudicate legitimacy. It does not require consensus. Instead, it creates a **shared public map** — one that makes the structure of a complex challenge legible and explorable, without prescribing how it must be tackled.

This distinction is subtle but critical.

G-O-S-R helps actors discover alignment — not through instructions, but through **insight**.

The goal is to create conditions where distributed actors — from nonprofits to city agencies to local organizers — can **see** what’s happening, identify where they fit, and take action **independently but coherently**.

In this way, G-O-S-R is not a coordination protocol but an **alignment surface**: a reflective structure that supports collaboration without requiring permission, direction, or orchestration.

In the next section, we’ll examine the mechanics of how that alignment happens — and how transparency and agency take the place of command and control.

## VII.B – The Role of Transparency and Agency

If G-O-S-R isn’t a coordination protocol, how does it help anything happen?  
The answer lies in two principles: **transparency** and **agency**.

Transparency refers to the clarity with which **work** — not just actors — is represented. In G-O-S-R, this means making the structure of complex challenges visible:

* What Goal is being pursued?  
    
* What Obstacles have been named?  
    
* What Solutions are believed to address them?  
    
* What Resources (programs) are implementing those Solutions?

Each layer of this structure exposes **intentions, efforts, and gaps**. It reveals the reasoning behind actions and the relationships between them. And because this is shared in a public map — not buried in institutional silos — it allows others to **orient** themselves more easily.

Agency, meanwhile, is about preserving the freedom and power of actors to choose their own path. G-O-S-R does not prescribe who should do what. Instead, it assumes:

* Actors are autonomous.  
    
* Motivations vary.  
    
* Participation is voluntary and self-directed.

By making the landscape transparent, G-O-S-R invites **self-alignment**. An organization may see that its new initiative already matches a named Solution. A funder may notice that a critical Obstacle has few Solutions being implemented and decide to invest there. A community member may recognize a missing piece and step into the gap.

This model avoids coercion and coordination fatigue. It also reflects how real-world ecosystems often operate: not through rigid plans, but through **adaptive responsiveness** to shared understanding.

G-O-S-R’s role is not to plan for others, but to help them **plan with awareness** — and to discover others who are doing the same.

In the next section, we explore how this capacity for self-alignment — enabled by transparency and protected by agency — can lead to **emergent collaboration**, without ever needing central control.

## VII.C – How Self-Alignment Leads to Emergent Collaboration

In traditional models of collaboration, partnerships are often brokered through direct outreach, formal agreements, or participation in a centralized coalition. These mechanisms work — but they are slow, selective, and often shaped by existing power dynamics.

G-O-S-R imagines something different:  
a system where **collaboration emerges** not from direction, but from **visibility and intent**.

Here’s how:

1. **A Shared Map Becomes a Discovery Surface**  
   When multiple actors view the same structure of Obstacles and Solutions, they begin to see not just their own role, but how others are showing up.  
     
   * Who is implementing a similar Solution in a different place?  
       
   * Who is addressing a shared Obstacle from a different angle?  
       
   * Who has a program that could complement — or duplicate — my own?

These insights don’t require a meeting. They’re byproducts of public structure.

2. **Gaps Become Invitations**  
   A Solution listed in G-O-S-R but lacking Resources becomes a visible opportunity — a "pull request" to the world. It invites implementation without assigning responsibility. And it does so in a way that aligns with each actor’s own mission and capacity.  
     
3. **Redundancy Becomes Visible — and Fixable**  
   If three actors in the same region are unknowingly tackling the same Obstacle with nearly identical Solutions, the G-O-S-R map may be the first place this becomes clear.  
   This doesn’t require top-down consolidation. It simply makes **coordination an option**, not an obligation.  
     
4. **Cross-Pollination Becomes Easier**  
   A community group working on food security might discover that another actor’s transportation program solves part of their delivery challenge. Neither knew of the other. But through alignment to shared Obstacles, unexpected synergies can emerge.  
     
5. **Distributed Action Gains Coherence**  
   Over time, self-aligned actors — each making decisions independently but guided by the same structured map — begin to behave like a coordinated system.  
   But the coherence is **emergent**, not engineered. It arises from shared framing, not shared governance.

In this way, G-O-S-R models a different kind of collaboration:  
one where transparency replaces permission, and alignment replaces orchestration.

This is especially powerful in ecosystems where:

* Trust is uneven  
    
* Capacity is distributed  
    
* Coalitions are hard to maintain  
    
* Needs evolve faster than structures

With these philosophical commitments in place, we can now turn to a practical question:  
**How do we extend A2A to support this kind of grounded, decentralized participation — without breaking its elegant simplicity?**

# VIII. Extending A2A Without Breaking It

## VIII.A – Using Extensions to Encode Real-World Meaning

The Agent-to-Agent (A2A) protocol is intentionally minimal. It offers a compact schema to describe autonomous agents, their capabilities, and how they can interact — whether those agents are APIs, services, models, or (with appropriate extension) human-based entities such as nonprofits, public institutions, or coalitions. That elegant simplicity is one of its greatest strengths.

But when real-world problem-solving takes center stage — as it does in the G-O-S-R approach — complexity can’t be fully avoided. Actors often operate through multiple programs. Programs implement distinct solutions. And solutions may be motivated by goals and constrained by real-world eligibility, geography, or history.

These layers of context matter.  
They shape how work is done — and how others might find it, support it, or replicate it.

This is where a **tension emerges**:

How can we structurally represent programs in or around A2A without bloating the protocol or fragmenting the ecosystem?

Earlier, we outlined **four competing options** — from embedding programs directly in AgentCards to modeling them as standalone objects or overlaying them externally. But before resolving that structural question, we need to understand a deeper challenge:  
**What kinds of information must programs carry to support alignment, discovery, and replication?**

That’s where **extensions** come in. The A2A protocol allows optional fields or linked schemas to enrich AgentCards — without altering the core format. This gives us room to explore expressive layers that can work across all four structural models.

And that brings us to one of the most important expressive needs in decentralized ecosystems:  
the ability for agents to invite **participation** — not just describe what they do.

---

## VIII.B – Reframing “Tools” as Participation Templates

In its current design, the A2A protocol allows agents to list **tools** — links to APIs, endpoints, or digital services that other agents can invoke. This mechanism works well in software ecosystems: one agent offers a function, another calls it. The interaction is tightly scoped and clearly defined.

But when the agents are human entities — nonprofits, mutual aid groups, public agencies — this pattern feels insufficient. What does a “tool” mean when the service is a food pantry, a housing navigation team, or a grief support circle? A website link might convey *where* the work is happening, but not *how* to engage with it — or what it would take to replicate or support it.

What these actors often need isn’t just a tool, but a **template for participation**.

**A Template for Action**

A participation template is a structured invitation. It helps others understand:

* What kind of work is being done  
    
* What values, rhythms, or commitments define it  
    
* How others can join, replicate, or support it — and in what roles

Unlike a tool, which is often transactional (“call this API”), a participation template is **relational** and **adaptive**. It frames the *style* of participation, not just the task.

This structure helps in several directions:

* **For implementors**, it’s a recipe:  
  “Here’s how we do this, what it takes, what’s flexible, and what’s core.”  
    
* **For volunteers**, it sets expectations:  
  “Here’s what we need from you, how we show up for each other, and what it feels like to be part of this.”  
    
* **For funders**, it’s a transparency layer:  
  “Here’s how this program actually works, how it addresses a defined Solution, and what would be required to grow or replicate it.”

Participation templates serve as **multi-sided artifacts** — carrying the DNA of a working program and making it legible to others across the ecosystem.

**Why This Fits Into the Larger Question**

You might wonder: *Where does this leave the four options we introduced earlier?*  
We’re not walking away from them. Instead, we’re **building the criteria** by which they can be judged.

Templates work whether programs are:

* Embedded in agents  
    
* Modeled as standalone objects  
    
* Linked from G-O-S-R  
    
* Or treated as agents themselves

Rather than resolving the architecture now, we’re expanding the vision of what a meaningful representation should offer — to implementors, volunteers, and funders alike.

And soon, we’ll return to the structural question better equipped to answer it.

## VIII.C – Balancing Protocol Compatibility with Expressiveness

One of A2A’s most elegant design choices is its simplicity. Its AgentCard format is deliberately minimal: a clear, JSON-based description of what an agent does, what it can respond to, and how it can be contacted or invoked. This leanness ensures that agents — whether AI models or API wrappers — can interoperate quickly and reliably, with minimal overhead.

But this strength creates a natural tension. As we’ve seen in the G-O-S-R context, human-based agents and real-world programs often need to express far more:

* Motivations, histories, and community roots  
    
* Operational rhythms and participation norms  
    
* Eligibility criteria, geographic scope, or language fluency  
    
* Non-standard communication styles or decision-making models

All of these are important for discoverability, alignment, and implementation. But encoding them risks bloating the AgentCard — making it harder to parse, harder to interoperate, and harder to standardize across domains.

So how can we introduce meaningful structure **without breaking the core protocol**?

**The Role of Extensions**

A2A’s design wisely includes a solution: extensions. Agents can define custom fields or link to external schema definitions via the "extensions" block in their AgentCard. This creates a safe boundary between the **interoperable core** and the **context-specific layer**.

In our case, this opens the door to:

* Including "operating\_character" to describe human agents’ motivational or communicative styles  
    
* Linking to "participation\_templates" that show others how to engage, replicate, or support a program  
    
* Declaring "programs" as a list of implemented solutions, each with its own metadata

This modularity allows human-facing complexity to **sit beside** the core protocol — not inside it.

**Designing for Compatibility**

To ensure compatibility, every extension we propose:

1. **Uses clearly namespaced fields**, avoiding collisions with future core fields  
     
2. **Links to stable external schema definitions**, so others can validate or adopt them  
     
3. **Keeps the base AgentCard intact**, so it remains functional even if extensions are ignored

This gives us a graceful fallback: agents that don’t understand the extensions still know how to talk to each other — while those that do can unlock deeper forms of alignment.

**Why This Matters**

In a decentralized system, adoption isn’t mandated — it’s earned. Protocols survive when they’re useful, not just when they’re elegant. By treating expressiveness as an additive layer — something agents can opt into when needed — we preserve the interoperability of A2A while expanding its utility for real-world work.

And with that foundation, we’re now ready to revisit the question we’ve been circling:  
How should programs — the concrete, replicable implementations of solutions — actually be represented in the system?

In the next section, we explore the introduction of a new class of participants: **Actors**. And with them, a new proposal for closing the loop between Goals, Solutions, Resources, and real-world agency.

# IX – The “A” in G-O-S-R-A: Actors as Self-Aligned Agents

## IX.A – Introducing “Actors” as Independent Participants

Throughout this discussion, we've introduced several terms to describe participation in decentralized problem-solving systems:

* In **G-O-S-R**, we focus on **Resources** — concrete programs or entities implementing specific Solutions.  
    
* In **A2A**, we describe **Agents** — typically software-based participants that expose clear interfaces and capabilities.  
    
* In our proposed extensions, we’ve added metadata like operating\_character and participation\_template to reflect the more human and situational nature of real-world entities.

But as our modeling deepens, another term must be brought forward: the **Actor**.

It’s easy to confuse “Actor” with “Agent,” but the distinction is intentional.  
Where an Agent in A2A is a well-defined interface endpoint, an **Actor** in G-O-S-R-A is a **real-world participant** — usually a human-led organization or institution — that chooses to align itself with a particular Solution.

The Actor is not the program or the service.  
The Actor is the *chooser*, the *implementor*, the *declaring force* behind the work.

This includes:

* Nonprofits  
    
* Government departments  
    
* Mutual aid networks  
    
* University labs  
    
* Civic groups  
    
* And emerging collectives not yet formalized

What binds them is not formality or scale, but **intention**.  
They act — and in doing so, they align themselves with a Solution already mapped in the G-O-S-R landscape.

Yet while A2A's AgentCard is not well-suited to representing **individuals** directly (due to concerns about privacy, stability, and reductionism), G-O-S-R understands the **individual as central**:

* It is **individuals** who experience the unmet need.  
    
* It is **individuals** who surface Obstacles and imagine new paths.  
    
* It is **individuals** who build, join, or spin up the very organizations we now model as Actors.  
    
* And it is **individuals** who, even outside formal structures, contribute through insight, effort, and alignment.

In this light, the Actor is best understood not as a faceless entity, but as a **vessel of individual intention**, magnified and made sustainable through structure.

**Clarifying Roles**

This framing also brings precision to G-O-S-R:

* **Actors** run one or more **Programs**  
    
* Each **Program** implements one or more **Solutions**  
    
* Each **Solution** addresses one or more **Obstacles**  
    
* All which are in service of a singular, shared **Goal**

Actors become the linchpin in this map. They connect the abstract Solution to the real-world Resource. They are how the system moves from potential to kinetic — from idea to action.

And by modeling them explicitly — including their motivations, values, and operating norms — we enable **decentralized discovery**: a way for others to find alignment and collaboration without a central authority.

This is the final transformation G-O-S-R undergoes in adopting A2A’s grammar:  
It acknowledges the human — not just as subject, but as **agentive force**.

## IX.B – Actor Motivations, Declarations, and Biases

Once we recognize Actors as intentional participants in a decentralized solution landscape, we must ask:  
**How can others understand what motivates them? What they care about? What conditions shape their behavior?**

In traditional interoperability models, agents are expected to list interfaces and capabilities. But with human-based Actors — from nonprofits to municipal teams — we need **a more grounded vocabulary**. Not just what they can do, but *why* they do it. And *how* they tend to show up.

This is where **declarations** become essential.

These declarations aren’t claims of objectivity. They’re more like **reflexive metadata** — public reflections of perspective, operating assumptions, and values. They might include:

* **Motivational frameworks** (e.g., Spiral Dynamics vMemes)  
    
* **Communication or decision-making styles** (e.g., Insights Discovery colors)  
    
* **Organizational biases** (e.g., preference for consensus vs. efficiency, hierarchy vs. network)  
    
* **Stated goals and intended outcomes**  
    
* **Declared openness to collaboration, funding, or replication**

These declarations serve multiple purposes:

1. **Transparency** – They help others understand how and why an Actor engages.  
     
2. **Alignment** – They make it easier to find kindred efforts — or respectful differences.  
     
3. **Trust-building** – They acknowledge subjectivity up front, rather than pretending to be “neutral.”

Importantly, this approach **avoids labeling individuals**. Instead, it allows **entities** to choose to describe themselves using recognized, non-sensitive frameworks. These may evolve over time. They may even contradict each other, revealing internal tensions. That’s okay.

What matters is that Actors **choose to be legible** — not for the sake of control, but to make alignment discoverable.

In a world without central orchestration, these kinds of declarations are the connective tissue.  
They help turn a loose network of efforts into a living ecology of responses — more adaptive, more participatory, and more reflective of the human entities doing the work.

## IX.C – How Actors Discover and Connect to Resources

Once an Actor declares its motivations, values, and readiness to engage, a natural question arises:  
**How does it find the right work to align with?**

In traditional top-down systems, opportunities flow through gatekeepers — funders, directories, or personal networks. But the G-O-S-R-A approach envisions something different:  
A **public map** of actionable work — described not in terms of ownership, but in terms of alignment.

In this map, **Resources** are not just passive listings of services. They are **implemented Solutions** — partial or complete — that map directly to real-world Obstacles. Each Resource offers a context-rich story of what is being done, why, and how.

Actors can discover Resources through several alignment pathways:

1. **Goal-based discovery** – Actors search for initiatives aligned with the Goal they also serve.  
     
2. **Obstacle-driven discovery** – Actors filter based on the barriers they feel uniquely prepared to address.  
     
3. **Solution-matching** – Actors look for Solutions they already implement (or aspire to).  
     
4. **Style or bias affinity** – Using declared traits, Actors can seek collaborators whose values and operational styles mesh with their own.

This creates a **many-to-many discovery surface**:

* One Resource may appeal to multiple Actors.  
    
* One Actor may connect with several Resources (as implementor, supporter, or replicator).  
    
* And new Solutions, once imagined, may attract new Actors who didn’t exist when the model was first built.

In this sense, the G-O-S-R-A map functions like **civic infrastructure** — not coordinating behavior, but making voluntary alignment easier, richer, and more legible.

Over time, as more Actors declare their intentions and as more Resources are described, this infrastructure gains power:

* Power to reduce duplication of effort  
    
* Power to reveal gaps and overlaps  
    
* Power to show where collaboration wants to happen

And because no central authority dictates who participates, this becomes a **commons for decentralized problem-solving** — one where discovery, not direction, is the primary mode of movement.

# X – Toward a Coherent Ecosystem of Agents and Programs

As we’ve seen, the G-O-S-R-A model, extended with A2A’s Agent grammar and enriched with human-aware metadata, provides a promising foundation. But clarity of structure is essential if this model is to scale across real-world applications, tools, and collaborations.

What emerges now is a layered ecosystem — one where Actors, Agents, Resources, and Programs coexist within a public problem-solving map that remains comprehensible and extensible.

## X.A – A Layered Structure: Goal ← Obstacles ← Solutions ← Resources ← Actors

At its core, the G-O-S-R-A model reveals a simple logic:

* A shared **Goal** anchors collective attention — not by forcing consensus, but by inviting alignment.  
    
* **Obstacles** name the friction — the why-not-yet — breaking down the problem into solvable parts.  
    
* **Solutions** respond directly to these Obstacles — potential interventions that could unlock progress.  
    
* **Resources** are the concrete implementations of these Solutions — described in real-world terms, such as services, programs, or prototypes.  
    
* **Actors** are the agents (human-led or otherwise) who run, support, or align themselves with Resources.

This hierarchy does more than organize ideas — it **models action**. It lets any participant — individual or institutional — locate themselves in the problem-solving space without needing permission or central approval.

It also allows people to work at different layers:

* Some may clarify Goals.  
    
* Others may specialize in obstacle-mapping.  
    
* Others still may prototype new Solutions or implement them through local Resources.

And because the model is public and portable, the same shared map can support many kinds of agents — AI, civic, organizational, or grassroots — each with different roles and affordances.

## X.B – Diagrams or Tables to Illustrate Relationships

To make this structure widely usable, we envision visual models and simple schemas that clarify:

* How a single Resource relates to one or more Solutions  
    
* How a single Actor may operate multiple Resources  
    
* How shared Obstacles can cluster around key bottlenecks  
    
* How disparate efforts might align when viewed through the Goal lens

Such models are not just explanatory tools — they are **coordination scaffolds** without central control. They help people “see the system,” so they can **self-align** more effectively.

(We will include sample tables, cards, and relationship maps in a future appendix.)

## X.C – Supporting Dynamic Alignment Without Central Control

The ultimate goal of this layered model is not documentation — it’s **movement**.

By exposing the logic of how work fits together — and how intentions map to implementations — the G-O-S-R-A ecosystem supports:

* Faster collaboration  
    
* Lower onboarding costs  
    
* Easier replication  
    
* Better collective sensemaking

And it does this without dictating strategy or imposing authority.  
Instead, it relies on **structured transparency**: clear enough to invite alignment, open enough to remain plural.

This ecosystem is not fixed. It is **intended to evolve**:

* New frameworks for describing Actors may emerge.  
    
* Program types may diversify.  
    
* A2A protocol extensions may deepen.

But the core idea will remain:

That a public, interoperable structure can empower decentralized actors to find each other, align their work, and move forward — not through control, but through shared context.

# XI. Next Steps and Open Questions

The G-O-S-R-A model, enriched by A2A and extended with human-aware fields like operating\_character and participation\_template, offers a promising direction. But as with any evolving infrastructure, **clarity, caution, and community input** are essential. This section outlines next steps and unresolved challenges that future collaborators must help shape.

## XI.A – Do We Need a ProgramCard Standard?

One lingering structural question is whether **Programs** — the real-world implementations of Solutions — deserve their own formal representation within the protocol. So far, we’ve modeled them either:

* As fields within AgentCards (Option 1\)  
    
* As standalone agents (Option 2\)  
    
* As a new ProgramCard object (Option 3\)  
    
* Or as externally described overlays linked to the G-O-S-R model (Option 4\)

Each of these has trade-offs:

* **Option 1** keeps the schema simple but may limit discoverability.  
    
* **Option 2** forces Programs to behave like agents, which they may not be.  
    
* **Option 3** offers clarity but introduces a new class of object into the protocol.  
    
* **Option 4** maintains separation of concerns but could dilute integration.

We believe **practical experimentation** will reveal which approach best supports the actual needs of collaboration, discoverability, and interoperability. Until then, our schema must remain flexible — but well-documented enough to be used and critiqued.

## XI.B – Governance, Validation, and Versioning of Extensions

Any ecosystem meant to outlive its first draft must face this:  
**Who decides which extensions are legitimate?**

We’ve added structures that may not be part of core A2A — including operating\_character, participation\_template, and our interpretation of “program.” These must:

* Be clearly versioned and namespaced  
    
* Be available in public repositories (e.g. GitHub, JSON schema registries)  
    
* Include reference documentation and example use cases

Crucially, we believe **legitimacy comes not from gatekeeping, but from transparency and usefulness**. A well-documented extension, widely used, becomes part of the de facto standard — not because it was authorized, but because it solves a real need.

That said, we also recognize the need for **coordinated validation efforts**, especially when integrations cross into high-stakes systems like funding, accreditation, or service delivery.

The challenge will be finding lightweight, community-trustable mechanisms to review and evolve extensions without imposing centralized control.

## XI.C – How Does This Connect to Model Context Protocol (MCP)?

Finally, we must acknowledge the link between this modeling work and **Model Context Protocol (MCP)** — a framework for structuring AI prompts, context, and cognitive scope.

MCP is often seen as an input-side problem: how to feed LLMs structured goals, values, and knowledge.  
But G-O-S-R-A is also relevant here — because it structures **the outputs and actors** participating in long-term, multi-agent problem-solving.

This raises several questions:

* Can AgentCards, ProgramCards, and operating\_character blocks be treated as part of model context?  
    
* Can LLMs use the G-O-S-R-A map to better reason about real-world consequences?  
    
* Could structured declarations (like values or motivations) help LLMs simulate or critique proposed collaborations?

We don’t yet know — but the overlap is fertile ground. As AI and human systems increasingly entangle, protocols like A2A, G-O-S-R-A, and MCP may need to **converge — or at least interoperate.**

# XII – Conclusion: Building Shared Infrastructure Without Central Control

In an age of proliferating problems and fragmented responses, the question is no longer *can we act* — it is *how do we align*?

The G-O-S-R-A model offers one answer. It does not prescribe a single path. It does not demand a singular identity. It does not create new hierarchies.  
Instead, it invites transparency, alignment, and **participation without permission**.

By integrating:

* the **structural clarity** of the G-O-S-R method,  
    
* the **descriptive power** of A2A AgentCards and capability declarations,  
    
* and the **human nuance** of new fields like operating\_character and participation\_template,

we’ve created a bridge between formal interoperability and informal collaboration — between machine-readable structure and human-driven work.

This new model acknowledges:

* That **Goals** must be shared, even when contested.  
    
* That **Obstacles** must be made visible, not hidden behind institutional blind spots.  
    
* That **Solutions** can and should be imagined by anyone.  
    
* That **Resources** can be discovered, adapted, and extended without central coordination.  
    
* And that **Actors**, whether individuals or institutions, can declare themselves — not to claim ownership, but to offer alignment.

Crucially, this is not a design for a system of control.  
It is a **map for voluntary discovery**, where self-aligning agents — human or AI — can find one another and decide what to do next.

Just as open protocols made the internet possible, G-O-S-R aims to make **collective problem-solving legible** — across silos, systems, and sectors.

This is our vision:

A public infrastructure for decentralized alignment.  
A commons of purpose.  
A grammar of participation — that scales.

The work is unfinished. That’s the point.  
We now invite others to take part.
