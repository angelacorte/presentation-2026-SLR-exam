+++
title = "Review Protocol Sketch: CLF/CBF for Safe Swarm Coordination"
description = "SLR exam presentation for Literature reviews: methods and tools"
outputs = ["Reveal"]
+++

### Review sketch
# Control Lyapunov and Control Barrier Functions for Safe Coordination in Swarms and Multi-Agent Systems

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

{{% highlight %}}
**Motivating gap.** Safety-aware control methods exist,
but it is not clear how they are used across swarm and multi-agent coordination tasks,
nor how they connect to high-level swarm programming.
{{% /highlight %}}

---

# Review objective, scope rationale, and RQs

The planned review investigates how **Control Lyapunov Functions** and **Control Barrier Functions** are used to support safe coordination in **swarm** and **multi-agent systems**.

{{% multicol %}}

{{% col %}}

### PICOC framing

- **Population:** swarm and multi-agent robotic systems;
- **Intervention:** CLF, CBF, CLF-CBF-QP, barrier certificates;
- **Comparison:** swarm programming languages and macro-programming abstractions;
- **Outcome:** safety, convergence, scalability, and composability;
- **Context:** distributed or locally implementable coordination.

{{% /col %}}

{{% col %}}

### Guiding questions

- Which coordination tasks and safety properties are addressed?
- Which control and coordination architectures are adopted?
- How are approaches evaluated, and at what scale?
- What gaps emerge with respect to swarm programming languages?

{{% /col %}}

{{% /multicol %}}

{{% highlight %}}
**Rationale.** The technical object is CLF/CBF-based safe coordination. Swarm programming is not a competing intervention, but the comparison lens used to ask whether these guarantees can become reusable and composable swarm-level constructs.
{{% /highlight %}}

---

# Background: CLF and CBF

{{< meta-kicker >}}
Two complementary control certificates
{{< /meta-kicker >}}

{{< framework-grid >}}
{{< framework-card title="Control Lyapunov Functions" >}}
- Encode progress toward a goal;
- Support convergence and stabilization;
- Useful for reaching a target, tracking, and formation objectives.
{{< /framework-card >}}

{{< framework-card title="Control Barrier Functions" >}}
- Encode safety constraints;
- Keep the system inside a safe set;
- Useful for collision avoidance and obstacle avoidance.
{{< /framework-card >}}

{{< framework-card title="CLF-CBF-QP" tone="green" >}}
Follow a nominal objective while minimally modifying the control input to satisfy safety constraints <small>[1]</small>.
{{< /framework-card >}}
{{< /framework-grid >}}

{{% footer %}}
[1] A. D. Ames, X. Xu, J. W. Grizzle and P. Tabuada, "Control Barrier Function Based Quadratic Programs for Safety Critical Systems," 2017.
{{% /footer %}}

---

# Review type and tertiary-survey check

{{< meta-kicker >}}
Method choice and positioning check
{{< /meta-kicker >}}

{{< framework-grid columns="2" >}}
{{< framework-card title="Review type" >}}

- Systematic mapping / SLR-oriented review sketch <small>[2]</small>;
- Content-based classification of primary studies;
- No meta-analysis: expected evidence is heterogeneous;
- Structured protocol needed because terminology is fragmented across control, robotics, swarm intelligence, and distributed systems <small>[3]</small>.
{{< /framework-card >}}

{{< framework-card title="Mini tertiary-survey protocol" tone="green" >}}

- **Target:** secondary studies only: surveys, SLRs, and SMSs;
- **Search terms:** CLF/CBF + survey/review/mapping;
- **Adjacent areas checked:** multi-UAV collision avoidance, aerial swarm robotics, swarm programming;
- **Extraction:** coverage, overlap with this review, and remaining gap.
{{< /framework-card >}}
{{< /framework-grid >}}

{{< meta-panel title="Purpose" compact="true" >}}
The tertiary check verifies whether the planned review is already covered and justifies the scope before screening primary studies.
{{< /meta-panel >}}

{{% footer %}}
[2] K. Petersen, S. Vakkalanka and L. Kuzniarz, "Guidelines for conducting systematic mapping studies in software engineering: An update," 2015.<br>
[3] B. Kitchenham and S. Charters, "Guidelines for performing Systematic Literature Reviews in Software Engineering," 2007.
{{% /footer %}}

---

# Tertiary survey: coverage and gap

{{% multicol %}}

{{% col %}}

### What existing surveys cover

- **CLF/CBF theory:** nonlinear-affine systems, QP formulations, applications <small>[4]</small>;
- **Safe learning:** learned or uncertain dynamics with CLF/CBF guarantees <small>[5]</small>;
- **Collision avoidance:** multi-UAV planning, conflict resolution, guidance <small>[6]</small>;
- **Aerial swarms:** trajectory generation, task allocation, sensing, mapping <small>[7]</small>.

{{% /col %}}

{{% col %}}

### Remaining gap

- **Coverage gap:** no retained secondary study maps CLF/CBF methods specifically in swarm/MAS coordination;
- **Evidence gap:** limited synthesis of task type, architecture, validation scale, and scalability;
- **Abstraction gap:** little attention to the distance between control-level guarantees and swarm-programming abstractions.

{{% /col %}}

{{% /multicol %}}

{{% highlight %}}
**Differentiation.** The planned review targets the intersection: CLF/CBF-based safe coordination in swarm/MAS, with explicit attention to scalability and swarm-programming abstractions.
{{% /highlight %}}

{{% footer %}}
[4] B. Li, S. Wen, Z. Yan, G. Wen and T. Huang, "A Survey on the Control Lyapunov Function and Control Barrier Function for Nonlinear-Affine Control Systems," 2023.<br>
[5] A. Anand, K. Seel, V. Gjærum, A. Håkansson, H. Robinson and A. Saad, "Safe Learning for Control using Control Lyapunov Functions and Control Barrier Functions: A Review," 2021.<br>
[6] S. Huang, R. S. H. Teo and K. K. Tan, "Collision avoidance of multi unmanned aerial vehicles: A review," 2019.<br>
[7] S. J. Chung, A. A. Paranjape, P. Dames, S. Shen and V. Kumar, "A Survey on Aerial Swarm Robotics," 2018.
{{% /footer %}}

---

# Methodological anchors
## SLR/SMS basis + tertiary survey

{{< meta-panel title="Methodological stance" >}}
SLR/SMS guidelines provide the methodological basis for reproducible search, selection, extraction, and synthesis <small>[2,3]</small>. Related secondary studies are used only to position the topic scope, identify overlap, and motivate the gap before screening primary studies <small>[4-7]</small>.
{{< /meta-panel >}}

{{% multicol %}}

{{% col %}}

### Protocol-level choices

- Use SLR/SMS guidelines as the methodological reference;
- Use the tertiary survey to position related secondary studies before screening primary studies;
- Use the aerial-swarm survey to refine task and architecture terminology;
- Treat the review protocol as the main exam artefact.

{{% /col %}}

{{% col %}}

### Protocol-design rationale

- Fragmentation is part of the research problem;
- Control-side dimensions capture what CLF/CBF papers actually prove;
- Swarm-side dimensions capture task, scale, and distribution assumptions;
- Programming-side dimensions are used only to expose the abstraction gap.

{{% /col %}}

{{% /multicol %}}

---

# Search and selection protocol

### Query blocks

```text
("control barrier function" OR "control Lyapunov function" OR "CLF-CBF" OR "barrier certificate")
AND
("multi-agent" OR "multi-robot" OR swarm OR "robot swarm")
AND
("collision avoidance" OR "formation control" OR coverage OR flocking OR coordination)
```

{{< framework-grid >}}
{{< framework-card title="Sources" compact="true" >}}

- Scopus;
- IEEE Xplore.
{{< /framework-card >}}

{{< framework-card title="Pilot volume" compact="true" >}}

- Scopus: 230 raw hits;
- IEEE Xplore: 149 raw hits;
- before screening and deduplication.
{{< /framework-card >}}

{{< framework-card title="Selection" tone="green" compact="true" >}}

- Deduplicate;
- Screen title/abstract;
- Full-text check for borderline studies;
- Snowball from seed papers <small>[8]</small>.
{{< /framework-card >}}
{{< /framework-grid >}}

{{< meta-panel title="Search-design note" >}}
Architecture is not used as a hard filter: centralized, decentralized, distributed, and local implementations are compared during extraction.
{{< /meta-panel >}}

{{% footer %}}
[8] C. Wohlin, "Guidelines for snowballing in systematic literature studies and a replication in software engineering," 2014.
{{% /footer %}}

---

# Inclusion, exclusion, and quality checks

{{< meta-kicker >}}
Screening rules and evidence sanity checks
{{< /meta-kicker >}}

{{< framework-grid >}}
{{< framework-card title="Include" >}}
Multi-agent, multi-robot, or swarm systems with explicit CLF, CBF, or barrier certificates for safety or convergence guarantees.
{{< /framework-card >}}

{{< framework-card title="Exclude" >}}
Single-agent studies, pure path planning without safety certificates, no explicit coordination or safety task, non-English papers.
{{< /framework-card >}}

{{< framework-card title="Quality checks" tone="green" >}}

- Is the safety property explicitly defined?
- Are assumptions and system model clear?
- Is the evaluation scenario described?
- Is the level of distribution/decentralization explicit?
{{< /framework-card >}}
{{< /framework-grid >}}

---

# Extraction and classification framework

{{< meta-kicker >}}
Coding scheme for extraction and synthesis
{{< /meta-kicker >}}

{{< framework-grid >}}
{{< framework-card title="Coordination scope" >}}
- **Task:** collision avoidance, formation, coverage, flocking;
- **System:** ground robots, UAVs, generic nonlinear MAS, simulated swarm.
{{< /framework-card >}}

{{< framework-card title="Control structure" >}}
- **Architecture:** centralized, decentralized, distributed;
- **Mechanism:** CBF, CLF-CBF-QP, barrier certificates, hybrid methods.
{{< /framework-card >}}

{{< framework-card title="Evidence and abstraction" tone="green" >}}
- **Validation:** theory only, simulation, hardware experiments;
- **Scalability:** number of agents, simulation scale, hardware scale, computational burden;
- **Programming abstraction:** none, controller-level API, behavior block, macro-programming language.
{{< /framework-card >}}
{{< /framework-grid >}}

{{% highlight %}}
**Framework derivation.** The dimensions map each RQ to extraction needs:
tasks and safety mechanisms come from the CLF/CBF seed papers; architecture, validation, and scalability come from the swarm/MAS scope; programming abstraction comes from the PICOC comparison lens.
{{% /highlight %}}

---

# From safe control to swarm programming

{{% multicol %}}

{{% col %}}

### Intervention: CLF/CBF literature

- Strong formal guarantees;
- Precise control-level formulations;
- Often expressed as optimization problems;
- Usually close to the controller or dynamics model.

{{% /col %}}

{{% col %}}

### Comparison: swarm programming

- Macro-programming for distributed collective systems <small>[9]</small>;
- Devices compute local values and exchange them with neighbors;
- Global behavior emerges as a computational field over the network;
- Emphasis on reusable, composable behavior abstractions.

{{% /col %}}

{{% /multicol %}}

{{% highlight %}}
**Comparison rationale.** In PICOC, comparison means “abstraction lens”: CLF/CBF papers are checked against what swarm programming languages normally provide, namely composability, reuse, and expression of collective behavior above controller level.
{{% /highlight %}}

{{% footer %}}
[9] J. Beal, D. Pianini and M. Viroli, "Aggregate Programming for the Internet of Things," 2015.
{{% /footer %}}

---

# MacroSwarm as a possible bridge

MacroSwarm instantiates aggregate computing in the swarm robotics setting <small>[10]</small>: \
collective behaviors are expressed as composable high-level blocks, rather than only as low-level controllers.

- Collective movement;
- Flocking and leader-follower behavior;
- Shape formation and morphogenesis;
- Team formation and collective planning.

{{< meta-panel title="Opportunity" tone="green" >}}
Use CBF-style safety filters to make aggregate-programming behavior blocks safety-aware.
{{< /meta-panel >}}

{{% footer %}}
[10] G. Aguzzi, R. Casadei and M. Viroli, "MacroSwarm: A Field-based Compositional Framework for Swarm Programming," 2025.
{{% /footer %}}

---

# Gap to be assessed

{{< meta-kicker >}}
From safe controllers to safe swarm abstractions
{{< /meta-kicker >}}

{{< meta-panels >}}
{{< meta-panel title="Review gap" >}}
CLF/CBF methods provide formal safety and convergence guarantees, but the review will assess whether these guarantees become reusable, composable abstractions in swarm-programming frameworks.
{{< /meta-panel >}}

{{< meta-panel title="Question to assess" tone="green" >}}
Are safety filters already supported, only partially explored, or still missing as aggregate-programming behavior blocks?
{{< /meta-panel >}}
{{< /meta-panels >}}

{{< bridge-flow title="Conceptual bridge to assess" >}}
{{< bridge-step title="Aggregate behavior block" note="collective intent" >}}
{{< bridge-arrow >}}
{{< bridge-step title="Nominal movement field" note="desired dynamics" >}}
{{< bridge-arrow >}}
{{< bridge-step title="CBF/QP safety filter" note="constraint enforcement" >}}
{{< bridge-arrow >}}
{{< bridge-step title="Safe distributed actuation" note="local correction" >}}
{{< /bridge-flow >}}

{{< meta-note >}}
The mapping checks whether this bridge is supported, partially explored, or still missing in the literature.
{{< /meta-note >}}

---

# Expected outputs

{{< meta-kicker >}}
From protocol design to review contribution
{{< /meta-kicker >}}

{{< bridge-flow title="Deliverable chain" >}}
{{< bridge-step title="Reproducible protocol" note="RQs, query, sources, criteria" >}}
{{< bridge-arrow >}}
{{< bridge-step title="Tertiary positioning" note="related surveys and differentiation" >}}
{{< bridge-arrow >}}
{{< bridge-step title="Classification taxonomy" note="tasks, architectures, safety mechanisms" >}}
{{< bridge-arrow >}}
{{< bridge-step title="Gap analysis" note="scalability and abstraction" >}}
{{< /bridge-flow >}}

{{< meta-panel title="Synthesis focus" tone="green" >}}
The final synthesis will compare evidence across coordination tasks, safety properties, validation type, scale, and the distance from controller-level guarantees to swarm-programming abstractions.
{{< /meta-panel >}}

---

# Takeaways

{{< meta-kicker >}}
What should remain clear
{{< /meta-kicker >}}

{{< takeaway-grid >}}
{{< takeaway-card number="01" title="A focused technical lens" >}}
CLF and CBF provide a concrete way to review formal safety and convergence guarantees in swarm/MAS coordination.
{{< /takeaway-card >}}

{{< takeaway-card number="02" title="A reproducible review protocol" >}}
The protocol makes scope, search, selection, extraction, and synthesis explicit before the full screening phase.
{{< /takeaway-card >}}

{{< takeaway-card number="03" title="From control guarantees to swarm abstractions" tone="green" >}}
The review maps how far the literature moves from controller-level safety filters toward reusable, composable swarm-programming constructs.
{{< /takeaway-card >}}
{{< /takeaway-grid >}}

---

# References

- [1] A. D. Ames, X. Xu, J. W. Grizzle and P. Tabuada, "Control Barrier Function Based Quadratic Programs for Safety Critical Systems," 2017.
- [2] K. Petersen, S. Vakkalanka and L. Kuzniarz, "Guidelines for conducting systematic mapping studies in software engineering: An update," 2015.
- [3] B. Kitchenham and S. Charters, "Guidelines for performing Systematic Literature Reviews in Software Engineering," 2007.
- [4] B. Li, S. Wen, Z. Yan, G. Wen and T. Huang, "A Survey on the Control Lyapunov Function and Control Barrier Function for Nonlinear-Affine Control Systems," 2023.
- [5] A. Anand, K. Seel, V. Gjærum, A. Håkansson, H. Robinson and A. Saad, "Safe Learning for Control using Control Lyapunov Functions and Control Barrier Functions: A Review," 2021.
- [6] S. Huang, R. S. H. Teo and K. K. Tan, "Collision avoidance of multi unmanned aerial vehicles: A review," 2019.
- [7] S. J. Chung, A. A. Paranjape, P. Dames, S. Shen and V. Kumar, "A Survey on Aerial Swarm Robotics," 2018.
- [8] C. Wohlin, "Guidelines for snowballing in systematic literature studies and a replication in software engineering," 2014.
- [9] J. Beal, D. Pianini and M. Viroli, "Aggregate Programming for the Internet of Things," 2015.
- [10] G. Aguzzi, R. Casadei and M. Viroli, "MacroSwarm: A Field-based Compositional Framework for Swarm Programming," 2025.
