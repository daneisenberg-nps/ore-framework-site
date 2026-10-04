Foundations
===========

Operational Resilience Engineering (ORE) brings together vulnerability
analysis, resilience engineering, operations research, and control theory to
study how engineering systems can be understood and improved under
disturbance, uncertainty, surprise, and changing operational demands.

ORE is organized around three linked but distinct analytical domains:

.. centered:: Vulnerability → Resilience → Control

This sequence is analytical rather than chronological. Vulnerability
characterizes susceptibility to undesirable change and the perspectives used
to evaluate it. Resilience characterizes the capacities, strategies, and
designs through which acceptable performance can be preserved or improved.
Control characterizes the processes through which systems sense, anticipate,
act, and learn as conditions change.

The framework draws from established literature while making its own
definitions, assumptions, and levels of analysis explicit. The goal is not to
impose a single universal vocabulary for resilience research. It is to clarify
which concept, measure, interpretation, and decision problem is being
addressed in a given engineering analysis.

Vulnerability analysis
----------------------

The first foundation of ORE is vulnerability analysis for engineering systems.

A vulnerability analysis begins with the question: under what conditions is a
system susceptible to undesirable change? In engineering contexts, answering
that question typically requires representations of scenarios or states,
likelihood information, consequences, operational limits, feasible designs,
and the relation between a system's present and possible future performance.

Quantitative risk analysis has commonly used a triplet comprising scenarios,
likelihoods, and consequences :cite:p:`kaplanGarrick1981`. ORE builds on this
tradition but distinguishes the underlying vulnerability data from the
particular perspective used to evaluate it.

In the developing ORE formulation, a vulnerability space is represented by:

.. math::

   \mathcal{V} = (S,L,C),

where :math:`S` is a set of scenarios or system states, :math:`L` contains
likelihood information, and :math:`C` contains consequence information.
This space is not itself equivalent to risk. It becomes a quantitative
decision framework only after likelihood and consequence information are
interpreted and evaluated from a particular perspective.

This distinction matters because a system can appear vulnerable in different
ways depending on whether the analysis prioritizes expected consequence,
probability of failure, plausible worst-case disruption, or the possibility of
crossing an unacceptable operational boundary. The current formal treatment
of these perspectives is described on the :doc:`theory` page and in the
developing vulnerability-analysis manuscript.

Risk, reliability, adversary, and safety
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ORE distinguishes risk, reliability, adversary, and safety as related but
non-interchangeable perspectives on engineering-system vulnerability.

Risk analysis commonly evaluates uncertain adverse consequences through a
probabilistic interpretation of likelihood and a scalar interpretation of
consequence. Reliability analysis commonly evaluates the probability that a
system crosses a defined performance or failure boundary. Adversary analysis
commonly emphasizes plausible worst-case consequences, including in
interdiction and failure-budget models. Safety analysis emphasizes avoiding
unsafe or unacceptable states and cannot generally be reduced to reliability
or risk alone.

These distinctions are important because measures that appear numerically
similar can preserve different information, prioritize different scenarios,
and recommend different engineering designs. For example, a risk-oriented
measure may prioritize reduction of rare catastrophic consequences, while a
reliability-oriented measure may prioritize prevention of a more frequent
crossing of an operational threshold.

ORE therefore treats risk as a perspective on vulnerability rather than as the
umbrella concept that subsumes all engineering-system analysis. Reliability,
adversary, and safety analyses are likewise distinct vulnerability
perspectives. The current theoretical framework identifies their formal
differences in likelihood and consequence interpretation.

This position is intended to address four recurring conceptual errors:

* **Conflation:** treating risk, reliability, adversary, or safety as the same
  concept.
* **Subsumption:** treating one perspective as generally a special case of
  another.
* **Substitution:** using a measure from one perspective as though it measured
  another.
* **Reification:** treating perspective-dependent measures as intrinsic
  properties of a system independent of an evaluative framework.

The framework does not imply that one perspective is universally correct.
Instead, it holds that each perspective can reveal relevant vulnerabilities
while also obscuring others. Consequently, a decision justified by one
vulnerability perspective may impose tradeoffs relative to another.

Resilience engineering
----------------------

The second foundation of ORE is resilience engineering: the study of how
systems continue to perform, adapt, and recover under changing conditions,
disturbance, and surprise.

Resilience is not treated here as a direct synonym for risk, reliability, or
vulnerability. Vulnerability identifies conditions under which undesirable
change can occur and the perspectives through which those conditions are
evaluated. Resilience concerns capacities, strategies, and designs that change
how a system performs in relation to disturbance.

This distinction is particularly important for engineering decision-making.
A vulnerability analysis can identify what conditions or scenarios deserve
attention, but it does not by itself specify what intervention should be
implemented. Resilience analysis evaluates how alternative designs, policies,
configurations, or capabilities preserve, extend, recover, or improve
acceptable performance.

A common engineering representation of resilience is a system-performance
curve showing a selected measure of system function before, during, and after a
disturbance. Such a curve can be useful as a phenomenological description of
observed performance loss and recovery. However, it does not by itself explain
why performance declines or recovers, what interventions were available or
taken, or how alternative decisions could have changed the outcome
:cite:p:`eisenberg2025rebound`.

The limitation is not merely that a rebound curve is incomplete. A curve
typically represents one selected performance measure and an observed
trajectory after a disturbance; it does not necessarily represent system
state, feedback structure, operational constraints, available control actions,
adaptive capacity, or the decision process that produces performance over
time. Consequently, the same observed curve can be consistent with materially
different system dynamics and different opportunities for resilient
intervention.

Recent work using linear time-invariant feedback control further demonstrates
conditions under which a conventional system-performance curve falls short as
a resilience model :cite:p:`demmer2026system`. ORE therefore treats system
performance as an outcome of state stability, operational boundaries, design,
and control processes—not as a curve that can by itself define resilience.

Woods's four concepts
~~~~~~~~~~~~~~~~~~~~~

A central intellectual foundation is David D. Woods's distinction among four
concepts often grouped under the single label *resilience*:

* **Robustness:** continuing to function in the presence of disturbance.
* **Rebound:** recovering or returning toward prior performance after a
  disruption.
* **Graceful extensibility:** extending adaptive capacity when surprise
  challenges the boundaries of ordinary operation.
* **Sustained adaptability:** maintaining the capacity to adapt as demands,
  constraints, and conditions continue to change.

Woods's work cautions against treating robustness and rebound as complete
accounts of resilience, particularly when systems encounter surprise or
exceed the limits of their ordinary adaptive capacity
:cite:p:`woods2015,woods2018`.

ORE agrees that robustness and rebound alone are incomplete. At the same time,
it treats them as worthy engineering design strategies when the objective
concerns system stability. Its developing contribution is to integrate
state-stability strategies with boundary-oriented capabilities informed by
graceful extensibility and sustained adaptability.

The :doc:`theory` page develops this interpretation through a resilience
framework organized by continuity and improvement, and by state stability and
operational boundary.

Surprise and infrastructure resilience
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Critical infrastructure systems must operate amid changing demands,
interdependencies, disturbances, constraints, and incomplete knowledge.
Surprise is therefore not simply a forecasting error to be eliminated; it is
a persistent operational condition for which systems, organizations, and
operators must prepare.

Research on national and critical-infrastructure resilience has emphasized
the integration of human and socio-technical capacities with technical-system
processes :cite:p:`thomas2019resilience`. Later work further argues that
infrastructure resilience must address surprise directly, including the
ability to prepare for, respond to, and learn from conditions that exceed
existing expectations :cite:p:`alderson2022surprise,seager2025infrastructure`.

This literature motivates ORE's emphasis on operational boundaries, adaptive
capacity, feasible interventions, and the processes through which systems
revise their understanding and performance following disruption.

Resilience terminology and scope
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Resilience-related terminology varies substantially across infrastructure
research and across disciplinary contexts. Reviews of critical-infrastructure
literature show that terms such as resilience, robustness, reliability,
vulnerability, adaptation, recovery, and sustainability are often defined
differently or applied at different levels of analysis
:cite:p:`mentges2023resilience`.

ORE responds by defining its concepts in relation to specific analytical
objects:

* **Vulnerability** concerns susceptibility to undesirable change and the
  perspectives used to evaluate it.
* **Resilience** concerns capacities and design strategies that preserve,
  extend, recover, or improve acceptable performance.
* **Control** concerns the processes that connect observation, interpretation,
  decision, action, and learning over time.

These definitions are intended to support comparison and integration where
appropriate without assuming that superficially similar terms are equivalent.

Control and resilient performance
---------------------------------

The third foundation of ORE is control: the continuing process through which
a system observes conditions, interprets their significance, selects feasible
actions, implements interventions, and updates its future behavior.

Control provides a formal language for distinguishing observed system
performance from the mechanisms that generate it. The rebound curve is
frequently used to summarize a system's functional decline and recovery, but
it is descriptive rather than explanatory: it does not identify why a system
declined, why it recovered, what actions were taken, or what alternatives
could have improved its performance :cite:p:`eisenberg2025rebound`.

A performance trajectory may instead reflect the interaction of system state,
disturbances, feedback, controller structure, operational constraints,
resource availability, and intervention choices. Without representing these
relationships, the same observed curve can be consistent with materially
different system dynamics and different opportunities for resilient
intervention. Feedback-control analysis demonstrates why a system-performance
curve can omit the dynamics and control structure needed to explain, evaluate,
or improve resilient performance :cite:p:`demmer2026system`.

Within ORE, control is not limited to automatic feedback regulation. It also
includes human, organizational, technical, and socio-technical processes that
shape how an engineering system detects change, evaluates alternatives, acts
under constraints, and learns from the resulting performance.


SAAL: sensing, anticipating, acting, and learning
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

ORE's developing control formulation uses four connected processes:

* **Sensing:** observing system performance, disturbances, resource
  conditions, constraints, and proximity to operational boundaries.
* **Anticipating:** identifying possible future states, demands, threats,
  opportunities, and emerging boundary challenges.
* **Acting:** selecting and implementing feasible interventions, operational
  strategies, policies, or designs.
* **Learning:** revising models, interpretations, strategies, constraints, and
  future intervention choices in light of both successful and unsuccessful
  performance.


The SAAL processes provide an operational language for resilient control. They
identify how information about system state and changing operational boundaries
can enter a feedback process: sensing supplies observations; anticipating
relates observations to possible future conditions; acting implements feasible
control or design interventions; and learning revises the model, strategy
space, and boundary assumptions used in future cycles.

The SAAL formulation is consistent with resilience-engineering accounts that
connect resilient performance to the capacities to monitor, anticipate,
respond, and learn. It also emphasizes the integration of human and
socio-technical capacities with infrastructure-system processes
:cite:p:`thomas2019resilience`.

SAAL does not presume that surprise can be fully predicted, prevented, or
eliminated. Instead, it organizes how systems and their operators can detect
changing conditions, develop and revise expectations, implement feasible
actions, and learn from the limits of prior models
:cite:p:`alderson2022surprise,seager2025infrastructure`.

Operations research and decision support
-----------------------------------------

ORE uses operations research to formalize the decision structures that connect
vulnerability, resilience, and control. These include:

* Scenario and state spaces.
* Likelihood and consequence information.
* Performance measures and operational boundaries.
* Constraints, resources, and feasible strategy spaces.
* Engineering designs, policies, and interventions.
* Tradeoffs among multiple vulnerability and resilience perspectives.

The purpose of formalization is not to suggest that all relevant system
knowledge is fully observable, measurable, or reducible to a single metric.
Rather, it makes assumptions and decision consequences explicit.

A central ORE proposition is that system data do not directly determine a
decision. They must first be interpreted through one or more perspectives:

.. centered:: Data → Perspective → Decisions

This principle applies to vulnerability analysis, resilience evaluation, and
control design. It also makes visible the potential for blind spots: a model
can support effective action within its perspective while omitting
vulnerabilities, capabilities, or consequences that would be salient under
another perspective.

Relationship among the foundations
----------------------------------

The three domains are mutually connected:

* Vulnerability analysis identifies how unacceptable performance can arise and
  which aspects of system behavior are visible under particular analytical
  perspectives.
* Resilience analysis evaluates the capacities and design strategies that can
  preserve, extend, recover, or improve acceptable performance in relation to
  those vulnerabilities.
* Control specifies the continuing sensing, anticipation, action, and learning
  processes through which vulnerabilities are recognized, resilience
  capacities are invoked, and models are revised over time.

ORE is under active development. The :doc:`theory` page contains the current
conceptual and formal architecture, while :doc:`research-path` identifies
planned technical notes, formal results, engineering examples, and research
artifacts.

References
----------

.. bibliography::