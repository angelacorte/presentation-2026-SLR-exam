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

**Motivating gap:** safety-aware control methods exist, but it is not clear how they are used across swarm and multi-agent coordination tasks, nor how they connect to high-level swarm programming.

---

# Why Control * Functions?

{{% multicol %}}

{{% col %}}

### Control Lyapunov Functions (CLF)

- Encode progress toward a goal;
- Support convergence and stabilization;
- Useful for reaching a target, tracking, and formation objectives.

{{% /col %}}

{{% col %}}

### Control Barrier Functions (CBF)

- Encode safety constraints;
- Keep the system inside a safe set;
- Useful for collision avoidance and obstacle avoidance.

{{% /col %}}

{{% /multicol %}}

**CLF-CBF-QP idea:** follow a nominal objective while minimally modifying the control input to satisfy safety constraints <small>[1]</small>.

<div>
<small style="text-align: left"></br>
[1] A. D. Ames, X. Xu, J. W. Grizzle and P. Tabuada, "Control Barrier Function Based Quadratic Programs for Safety Critical Systems," 2017.</br>
</small>
</div>

---

# Why this is a literature review problem

- The topic is spread across control theory, robotics, swarm intelligence, and distributed systems;
- Different communities use different terminology for similar ideas;
- There is no single obvious search string;
- The boundary between <em>multi-agent systems</em>, <em>multi-robot systems</em>, and <em>swarm robotics</em> is not always explicit.

**Review need:** a transparent protocol to define the scope, identify relevant studies, extract comparable data, and synthesize the evidence <small>[2]</small>.

<div>
<small style="text-align: left"></br>
[2] Kitchenham, Barbara & Charters, Stuart, "Guidelines for performing Systematic Literature Reviews in Software Engineering," 2007.</br>
</small>
</div>

---

# Review objective

The planned review would investigate how **Control Lyapunov Functions** and **Control Barrier Functions** are used to support safe coordination in **swarm** and **multi-agent systems**.

The focus would be on tasks such as:
- Collision avoidance;
- Formation control;
- Coverage and connectivity maintenance.

The planned contribution is a **taxonomy** of existing approaches and a **gap analysis** toward safety-aware aggregate programming.

Here, aggregate programming is not the main review topic, 
but the perspective used to interpret one possible research gap: 
how low-level safety guarantees could be exposed as composable high-level swarm programming abstractions.

---

# Research questions

- **RQ1.** What coordination tasks are addressed by CLF/CBF-based approaches in swarms and multi-agent systems?
- **RQ2.** What safety properties are modeled and enforced?
- **RQ3.** What control and coordination architectures are adopted?
- **RQ4.** How are the proposed approaches evaluated?
- **RQ5.** What evidence exists about scalability and distributed implementation?
- **RQ6.** What gaps emerge with respect to high-level swarm programming and aggregate computing?

---

# Review type and scope

{{% multicol %}}

{{% col %}}

### Review type

- Systematic mapping / SLR-oriented review sketch <small>[3]</small>;
- Content-based classification of primary studies;
- No meta-analysis: expected evidence is heterogeneous.

{{% /col %}}

{{% col %}}

### Scope choices

- White literature as the main source;
- arXiv only as complementary source for emerging works;
- Focus on robotics, control, and multi-agent coordination.

{{% /col %}}

{{% /multicol %}}

<div>
<small style="text-align: left"></br>
[3] Kai Petersen, Sairam Vakkalanka, Ludwik Kuzniarz, "Guidelines for conducting systematic mapping studies in software engineering: An update," 2015.</br>
</small>
</div>

---

# Search strategy sketch

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

**Possible databases:** Scopus, IEEE Xplore, ACM Digital Library, SpringerLink, ScienceDirect.

**Complementary strategy:** backward and forward snowballing from selected seed papers <small>[4]</small>.

<div>
<small style="text-align: left">
[4] Claes Wohlin, "Guidelines for snowballing in systematic literature studies and a replication in software engineering" 2014.
</small>
</div>

---

# Inclusion and exclusion criteria

{{% multicol %}}

{{% col %}}

### Include

- Multi-agent, multi-robot, or swarm systems;
- Explicit use of CLF, CBF, or related barrier certificates;
- Safety or convergence guarantees;
- Distributed, decentralized, or locally implementable methods.

{{% /col %}}

{{% col %}}

### Exclude

- Single-agent only studies;
- Pure path planning without safety certificates;
- No explicit coordination or safety task;
- Non-English papers.

{{% /col %}}

{{% /multicol %}}

---

# Study selection and quality assessment

{{% multicol %}}

{{% col %}}

### Selection process

- Remove duplicates across databases;
- Screen title and abstract using inclusion/exclusion criteria;
- Read full text for borderline or relevant studies.

{{% /col %}}

{{% col %}}

### Lightweight quality checks

- Is the safety property explicitly defined?
- Are assumptions and system model clear?
- Is the evaluation scenario described?
- Is the level of distribution/decentralization explicit?

{{% /col %}}

{{% /multicol %}}

The aim is not to discard many papers, but to make the strength and limitations of the evidence explicit.

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

These are not final categories: they would be refined during data extraction and adjusted if the selected studies reveal additional recurring dimensions.

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

- A macro-programming paradigm for distributed collective systems <small>[5]</small>;
- Devices compute local values and exchange them with neighbors;
- Global behavior emerges as a computational field over the network.

{{% /col %}}

{{% /multicol %}}

**Question:** can CLF/CBF-style safety guarantees be lifted from local controllers to aggregate-level programming abstractions?

<div>
<small style="text-align: left">
[5] J. Beal, D. Pianini and M. Viroli, "Aggregate Programming for the Internet of Things," 2015.
</small>
</div>

---

# MacroSwarm as a possible bridge

MacroSwarm is useful here because it instantiates aggregate computing in the swarm robotics setting <small>[6]</small>:
collective behaviors are expressed as composable high-level blocks, rather than only as low-level controllers.

- Collective movement;
- Flocking and leader-follower behavior;
- Shape formation and morphogenesis;
- Team formation and collective planning.

**Opportunity:** use CBF-style safety filters to make such blocks safety-aware.

<div>
<small style="text-align: left">
[6] Gianluca Aguzzi, Roberto Casadei, Mirko Viroli: "MacroSwarm: A Field-based Compositional Framework for Swarm Programming," 2025.
</small>
</div>

---

# Identified research gap

**Gap:** CLF/CBF methods provide formal safety and convergence guarantees, but they are rarely integrated as reusable and composable abstractions in macro-programming frameworks for swarms.

Conversely, aggregate programming provides compositional high-level coordination, but safety certificates are not usually exposed as central programming constructs.

**Potential paper idea:** safety-aware aggregate programming for swarm robotics.

---

# Proposed direction

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

- A reproducible protocol: RQs, search strings, databases, selection criteria;
- A dataset of selected primary studies and extraction fields;
- A taxonomy of CLF/CBF-based safe coordination approaches;
- A synthesis structured around tasks, architectures, safety properties, and validation;
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
- [2] Kitchenham, Barbara & Charters, Stuart, "Guidelines for performing Systematic Literature Reviews in Software Engineering," 2007.
- [3] Kai Petersen, Sairam Vakkalanka, Ludwik Kuzniarz, "Guidelines for conducting systematic mapping studies in software engineering: An update," 2015.
- [4] Claes Wohlin, "Guidelines for snowballing in systematic literature studies and a replication in software engineering" 2014.
- [5] J. Beal, D. Pianini and M. Viroli, "Aggregate Programming for the Internet of Things," 2015.
- [6] Gianluca Aguzzi, Roberto Casadei, Mirko Viroli: "MacroSwarm: A Field-based Compositional Framework for Swarm Programming," 2025.
  
- 
- 
- Roberto Casadei: Macroprogramming: Concepts, State of the Art, and Opportunities of Macroscopic Behaviour Modelling. ACM Comput. Surv. 55(13s): 275:1-275:37 (2023)