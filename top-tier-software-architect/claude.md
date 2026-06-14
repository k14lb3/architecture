# Software Architecture

---

## 1. The Architect's Job Is Not to Be the Smartest Person

The best architects are often invisible. Things just go well and nobody knows exactly why. The bad ones are easy to spot — they gatekeep decisions, drop buzzwords, and position themselves as the person everyone must get approval from.

The mantra Gregor lives by:

> Architects shouldn't try to be the smartest people. They should make everybody else smarter.

The oracle model — where developers line up to receive answers — doesn't scale and doesn't help anyone grow. The amplifier model does.

---

## 2. Risk Is the Real Value Proposition

When pressed on what an architect actually delivers, Gregor's answer is: **risk reduction**.

Not just technical risk either. The trap many architects fall into (especially in banks and large enterprises) is focusing purely on *execution risk* — did we build what we said we'd build? But software has a completely different risk surface:

- Will users actually want this?
- Will it generate revenue?
- Will it move the needle for the business?
- Can it evolve as requirements change?

A perfect plan executed perfectly can still be the wrong thing to build. Good architects hold *both* risk dimensions in their head simultaneously.

---

## 3. Simplicity Is Harder Than Complexity

The engineer from GitHub who said "simple becomes complex at scale" isn't wrong — and Gregor doesn't find it controversial at all. But there's a distinction worth making:

**Inherent complexity** cannot be removed. Distributed systems have physics. Retries, timeouts, idempotency, back pressure — these aren't design choices, they're the laws of the domain. You can't abstract them away entirely.

**Accidental complexity** is what we invite in ourselves — unnecessary abstractions, premature optimization, buzzword-driven design decisions.

The goal is not to make things maximally simple. It's to make inherent complexity *intuitive to deal with* while aggressively eliminating the accidental kind.

> Make it as simple as possible, but no simpler.

When systems get too complex, teams slow down, bugs increase, and eventually nobody wants to touch anything. That's not legacy software by accident — that's the direct result of accumulated complexity nobody addressed.

---

## 4. Shared Framing Before Debate

Most engineering arguments — microservices vs monolith, JSON vs YAML, Kubernetes vs anything else — aren't actually about the technologies. They're about people looking at the same thing from different angles without realizing it.

Gregor uses a cylinder analogy: one person sees a circle, another sees a rectangle. They'll argue forever if nobody steps back to establish what they're even looking at.

The architect's move is to **build the map before debating the route**. Take the microservices debate — instead of picking a side, break it into two independent axes:

- Design-time modularity (how the code is structured)
- Runtime modularity (how it's deployed)

Now you have four quadrants, not two camps. The modular monolith immediately becomes visible as a legitimate option. The debate becomes collaborative instead of tribal.

---

## 5. Draw Things

Gregor is a strong advocate for pen-and-paper visual thinking, and the reasoning is concrete: diagrams are harder to be fuzzy in than words.

In prose you can say "these components have some relationship" and nobody pushes back. In a diagram, either there's a line or there isn't. Either the arrow goes one way or both ways. The precision is forced.

Sketches also have more expressive dimensions than people realize — size, shape, shading, nesting, position, labels, ordering. Two colored pens on paper can carry roughly 20 distinct dimensions of meaning. That's a rich medium for teasing out where misunderstandings are buried.

The skill is learnable through repetition. You don't need artistic talent. What you do need is the ability to flip between left-brain (logical structure) and right-brain (pattern recognition, storytelling) as you work through a problem — using each to check the other.

---

## 6. The Phantom Sketch Artist

One of the sharpest metaphors in the conversation. Before CCTV cameras, police relied on sketch artists to composite images of suspects from witness descriptions. The witness *knows* what the person looks like but can't draw it. The artist *can* draw but has no idea what the person looks like.

The collaboration between them is what produces the useful output.

Architects work the same way. The team knows their system. They know the domain, the edge cases, the historical decisions. But they often can't articulate it clearly or see it from the outside. The architect doesn't know more than them — but can help them express what they already know.

Gregor's favorite signal that this is working: when he draws something wrong on purpose and the team immediately says "no, not like that." That correction *is* the collaboration. They're now in productive dialog.

And like sketch artists, architects need to study the underlying anatomy — not to draw beautiful rectangles, but to understand the structural relationships between components well enough to represent them accurately.

---

## 7. From Cartographer to Scout

The old enterprise architect model — maintaining a giant, comprehensive map of every system and integration — no longer works. By the time the map is finished, it's already wrong.

The better metaphor is the **scout**. A scout doesn't try to map everything. They have a specific objective (cross the river, find the enemy position) and they return with a small, highly relevant, timely map that serves that purpose.

Modern architects need to operate the same way: purpose-driven, situational, focused on the decision at hand rather than comprehensive documentation for its own sake.

> Too many architects try to find answers when they don't have a question.

GenAI is a perfect current example. The useful architect question isn't "where can we use AI?" It's: where are the best first use cases, how do we integrate it without coupling to a rapidly-evolving layer, and what's genuinely novel vs. just another workflow integration?

---

## 8. Your Old Mental Models Are Dangerous

Having strong technical experience from 10 years ago isn't just unhelpful — it's actively risky, because outdated heuristics get applied with full confidence.

Classic example: "everything must scale out." That was reasonable advice in a certain era. Today, Moore's Law means a lot of normal business applications could run on a single server with a few terabytes of RAM. Most companies aren't Netflix. The constraint that drove horizontal scaling as a default has changed.

The solution isn't to try to personally master every new technology — that's impossible. It's to maintain a **trusted network** of people who are actively building things, and to treat conversations with them as high-bandwidth knowledge transfers. Two days with the right person beats months of passive reading.

Social media is a poor substitute. Everyone's selling something.

---

## 9. Political Capital Is Real

Architects rarely have direct authority. No large headcount, no big budget. What they have is influence — and influence works like a currency.

You build it through: keeping promises, being transparent, being fair, actually helping people solve their problems. You spend it when you challenge a decision, call out a risk, or tell someone their project is in trouble.

The mistake is spending before you've earned. Walking into an organization as a new architect and immediately cataloging everything that's wrong is a fast way to become irrelevant. Nobody has an infinite line of credit.

The jester metaphor is useful here. The court jester could say things nobody else could say — not because of power, but because they were trusted to have no hidden agenda. An architect who isn't trying to inflate their own budget or make their resume look better with unnecessary complexity has that same freedom. Use it carefully.

---

## 10. Architecture Is Not Good or Bad — It's Suitable or Not

The "Big Ball of Mud" is often used as a pejorative. Gregor pushes back on this. The pattern's original authors were actually frustrated that it got labeled as obviously bad, because it has genuinely desirable qualities: fast to build, cheap, requires a limited skill set, gets something out the door quickly.

Those aren't small things. If a team has a one-month launch deadline and limited resources, a well-reasoned ball of mud might be exactly the right call. Telling them to build a cloud-native microservices platform instead isn't architecture advice — it's ideology.

When Gregor reviews architecture, he's not asking "is this good?" He's asking:

- Did this team understand their constraints?
- Did they make conscious trade-offs?
- Are those trade-offs aligned with what the business actually needed?

If the answer to all three is yes, the architecture is sound — regardless of what patterns it does or doesn't follow.

---

## 11. Don't Be Replaced by Your Own Tools

LLMs can generate architecture documents that look authoritative. Gregor says he can usually tell within two questions whether someone has actually thought something through or pasted model output and called it done.

The fluffy confidence is the tell. When you probe, it collapses like a house of cards.

The principle he offers is direct: **use the tool as an amplifier of your own thinking, not a substitute for it.** If the tool is doing the thinking, you've made yourself redundant. Either the output is bad and that's a problem, or the output is good and now people wonder why they're paying for you when they could just run the same prompt.

Your starting point can come from a tool. The value you add has to come from you.

---

## 12. Two Traps Worth Naming

**Trap 1 — Stumbling on the finish line.** Sometimes you clarify a problem and suddenly everything seems obvious. The temptation is to wonder if you actually did anything useful. You did. Making something obvious that wasn't is the entire job. Don't let the apparent simplicity of the result make you doubt the work that produced it.

**Trap 2 — "That was obvious."** When you surface a hidden assumption, people often say "well, obviously." But if it was obvious, why wasn't it stated before you showed up? Extracting and naming implicit assumptions is a high-skill activity. The result *feeling* obvious afterward is what good facilitation looks like, not evidence that it was easy.

---

## The Through Line

Every thread in this conversation points to the same thing. The architect's core function isn't technical design — it's **helping people think more clearly about technical decisions**.

The diagrams, the frameworks, the trade-off analysis — these are all in service of that. When that's working, the team makes better decisions, the system is more appropriate for its context, and the architect has done their job even if nobody can quite articulate why things went well.

That's the goal.
