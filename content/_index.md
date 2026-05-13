+++
title = "Review Protocol Sketch: CLF/CBF for Safe Swarm Coordination"
description = "SLR exam presentation for Literature reviews: methods and tools"
outputs = ["Reveal"]
+++

### Review sketch
# *Control Lyapunov* and *Control Barrier Functions* for Safe Coordination in Swarms and *Multi-Agent Systems*

[**Angela Cortecchia**](mailto:angela.cortecchia@unibo.it)

<div style="text-align: center; width: 100%; margin-top: 5rem;">
<img src="example-background.svg" style="width: 30%" />
</div>

---

# Motivation

{{% multicol %}}

{{% col %}}

### Research context

- Swarm and multi-agent systems coordinate through local interactions;
- Typical tasks include movement, formation, coverage, and flocking;
- In safety-critical settings, coordination alone is not enough.

{{% /col %}}

{{% col %}}

### Safety concerns

- Avoid inter-agent collisions;
- Avoid obstacles and unsafe regions;
- Preserve constraints such as connectivity or formation structure.

{{% /col %}}

{{% /multicol %}}

**Motivating gap:** safety-aware control methods exist, \
but it is not clear how they are used across swarm and multi-agent coordination tasks, \
nor how they connect to high-level swarm programming.

---

# Review objective and research questions

The planned review investigates how **Control Lyapunov Functions** and **Control Barrier Functions** are used to support safe coordination in **swarm** and **multi-agent systems**.

{{% multicol %}}

{{% col %}}

### Focus

- Collision avoidance;
- Formation control;
- Coverage and connectivity maintenance;
- Distributed or locally implementable coordination.

{{% /col %}}

{{% col %}}

### Guiding questions

- Which coordination tasks and safety properties are addressed?
- Which control and coordination architectures are adopted?
- How are approaches evaluated, and at what scale?
- What gaps emerge toward high-level swarm programming?

{{% /col %}}

{{% /multicol %}}

**Planned contribution:** a taxonomy of existing approaches and a gap analysis toward safety-aware aggregate programming.

---

# Background: CLF and CBF

{{% multicol %}}

{{% col %}}

#### Control Lyapunov Functions (CLF)

- Encode progress toward a goal;
- Support convergence and stabilization;
- Useful for reaching a target, tracking, and formation objectives.

{{% /col %}}

{{% col %}}

#### Control Barrier Functions (CBF)

- Encode safety constraints;
- Keep the system inside a safe set;
- Useful for collision avoidance and obstacle avoidance.

{{% /col %}}

{{% /multicol %}}

**CLF-CBF-QP idea:** follow a nominal objective while minimally modifying the control input to satisfy safety constraints <small>[1]</small>.

<div>
<small style="text-align: left">
[1] A. D. Ames, X. Xu, J. W. Grizzle and P. Tabuada, "Control Barrier Function Based Quadratic Programs for Safety Critical Systems," 2017.
</small>
</div>

---

# Review type and scope

{{% multicol %}}

{{% col %}}

### Review type

- Systematic mapping / SLR-oriented review sketch <small>[2]</small>;
- Content-based classification of primary studies;
- No meta-analysis: expected evidence is heterogeneous;
- Structured protocol needed because terminology is fragmented across control, robotics, swarm intelligence, and distributed systems <small>[3]</small>.

{{% /col %}}

{{% col %}}

### Scope choices

- White literature as the main source;
- arXiv only as complementary source for emerging works;
- Focus on robotics, control, and multi-agent coordination.

{{% /col %}}

{{% /multicol %}}

<div>
<small style="text-align: left">
[2] Kai Petersen, Sairam Vakkalanka, Ludwik Kuzniarz, "Guidelines for conducting systematic mapping studies in software engineering: An update," 2015.<br>
[3] Kitchenham, Barbara & Charters, Stuart, "Guidelines for performing Systematic Literature Reviews in Software Engineering," 2007.
</small>
</div>

---

# Methodological exemplar:
## macroprogramming survey

An in-topic survey on macroprogramming is used here as a methodological reference point: \
it shows how a broad and fragmented research area can be organized through a review-style structure <small>[4]</small>.

{{% multicol %}}

{{% col %}}

### Structure highlighted

- Motivation: the field is fragmented across domains;
- Research questions: used to organise the investigation;
- Search and selection: based on databases, keywords, and manual inspection;
- Extraction: notes on self-positioning, programming model, implementation, and examples.

{{% /col %}}

{{% col %}}

### Methodological takeaways

- Terminology is treated as part of the review scope;
- Classification dimensions are made explicit;
- Synthesis is organised around concepts and themes;
- The review ends by identifying opportunities and challenges.

{{% /col %}}

{{% /multicol %}}

<div>
<small style="text-align: left">
[4] R. Casadei, "Macroprogramming: Concepts, State of the Art, and Opportunities of Macroscopic Behaviour Modelling," 2023.
</small>
</div>

---

# Search and selection protocol

### Candidate query string

```text
("control barrier function" OR "control Lyapunov function" OR "CLF-CBF")
AND
("multi-agent" OR "multi-robot" OR swarm OR "robot swarm")
AND
("collision avoidance" OR "formation control" OR coverage OR coordination)
AND
(distributed OR decentralized OR local)
```

**Sources:** Scopus, IEEE Xplore, ACM Digital Library, SpringerLink, ScienceDirect; arXiv only as complementary source.

**Complementary strategy:** backward and forward snowballing from selected seed papers <small>[5]</small>.

**Selection:** remove duplicates, screen title/abstract, then read full text for relevant or borderline studies.

<div>
<small style="text-align: left">
[5] Claes Wohlin, "Guidelines for snowballing in systematic literature studies and a replication in software engineering" 2014.
</small>
</div>

---

# Inclusion, exclusion, and quality checks

{{% multicol %}}

{{% col %}}

**Include:** multi-agent, multi-robot, or swarm systems with explicit CLF, CBF, or barrier certificates for safety or convergence guarantees.

**Exclude:** single-agent studies, pure path planning without safety certificates, no explicit coordination or safety task, non-English papers.

{{% /col %}}

{{% col %}}

### Lightweight quality checks

- Is the safety property explicitly defined?
- Are assumptions and system model clear?
- Is the evaluation scenario described?
- Is the level of distribution/decentralization explicit?

{{% /col %}}

{{% /multicol %}}

---

# Preliminary extraction and classification framework

| Dimension | Possible values |
|---|---|
| Coordination task | collision avoidance, formation, coverage, flocking |
| Control architecture | centralized, decentralized, distributed |
| Safety mechanism | CBF, CLF-CBF-QP, barrier certificates, hybrid methods |
| System type | ground robots, UAVs, generic nonlinear MAS, simulated swarm |
| Validation | theory only, simulation, hardware experiments |
| Scalability evidence | number of agents, simulation scale, hardware scale, computational burden |

The same extraction sheet also supports lightweight quality assessment: safety definition, clarity of assumptions, evaluation setting, and distribution level.

---

# From safe control to swarm programming

{{% multicol %}}

{{% col %}}

### CLF/CBF literature

- Strong formal guarantees;
- Precise control-level formulations;
- Often expressed as optimization problems.

{{% /col %}}

{{% col %}}

### Aggregate computing

- Macro-programming for distributed collective systems <small>[6]</small>;
- Devices compute local values and exchange them with neighbors;
- Global behavior emerges as a computational field over the network.

{{% /col %}}

{{% /multicol %}}

**Interpretive gap:** CLF/CBF methods provide safety at control level, while aggregate programming provides compositional high-level coordination. The review asks whether these two levels have been connected.

<div>
<small style="text-align: left">
[6] J. Beal, D. Pianini and M. Viroli, "Aggregate Programming for the Internet of Things," 2015.
</small>
</div>

---

# MacroSwarm as a possible bridge

MacroSwarm is useful here because it instantiates aggregate computing in the swarm robotics setting <small>[7]</small>:
collective behaviors are expressed as composable high-level blocks, rather than only as low-level controllers.

- Collective movement;
- Flocking and leader-follower behavior;
- Shape formation and morphogenesis;
- Team formation and collective planning.

**Opportunity:** use CBF-style safety filters to make such blocks safety-aware.

<div>
<small style="text-align: left">
[7] Gianluca Aguzzi, Roberto Casadei, Mirko Viroli: "MacroSwarm: A Field-based Compositional Framework for Swarm Programming," 2025.
</small>
</div>

---

# Research gap and proposed direction

**Gap:** CLF/CBF methods provide formal safety and convergence guarantees, but they are rarely integrated as reusable and composable abstractions in macro-programming frameworks for swarms.

**Possible direction:** safety-aware aggregate programming for swarm robotics.

Aggregate / MacroSwarm behavior block</br>
↓</br>
Nominal desired movement field</br>
↓</br>
CBF safety filter or QP projection</br>
↓</br>
Safe distributed actuation

The nominal collective behavior is preserved whenever possible, while unsafe actions are locally corrected.

---

# Expected outputs

- A reproducible protocol: RQs, search strings, databases, and selection criteria;
- A taxonomy of CLF/CBF-based safe coordination approaches;
- A synthesis structured around tasks, architectures, safety properties, validation, and scalability;
- A gap analysis toward safety-aware aggregate and macro-programming abstractions.

---

# Takeaways

1. CLF and CBF provide a promising lens for safety-critical swarm coordination;
2. A review protocol can make the scope, search, selection, extraction, and synthesis reproducible;
3. The aggregate computing perspective reveals an original gap: compositional programming of formally safe swarm behaviors.

**Final idea:** from safe controllers to safety-aware aggregate blocks.

---

# References

- [1] A. D. Ames, X. Xu, J. W. Grizzle and P. Tabuada, "Control Barrier Function Based Quadratic Programs for Safety Critical Systems," 2017.
- [2] Kai Petersen, Sairam Vakkalanka, Ludwik Kuzniarz, "Guidelines for conducting systematic mapping studies in software engineering: An update," 2015.
- [3] Kitchenham, Barbara & Charters, Stuart, "Guidelines for performing Systematic Literature Reviews in Software Engineering," 2007.
- [4] Roberto Casadei: "Macroprogramming: Concepts, State of the Art, and Opportunities of Macroscopic Behaviour Modelling," 2023.
- [5] Claes Wohlin, "Guidelines for snowballing in systematic literature studies and a replication in software engineering" 2014.
- [6] J. Beal, D. Pianini and M. Viroli, "Aggregate Programming for the Internet of Things," 2015.
- [7] Gianluca Aguzzi, Roberto Casadei, Mirko Viroli: "MacroSwarm: A Field-based Compositional Framework for Swarm Programming," 2025.
