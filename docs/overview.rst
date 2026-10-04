Overview
========

Operational Resilience Engineering
----------------------------------

Operational Resilience Engineering (ORE) is a developing research framework
for understanding and improving engineering systems under disturbance,
uncertainty, surprise, and changing operational demands.

.. centered:: Operations Research + Resilience Engineering = Operational Resilience Engineering

ORE connects vulnerability analysis, resilience engineering, operations
research, and control theory. It is intended for critical infrastructure and
other complex engineering systems in which performance depends on technical,
human, organizational, and socio-technical processes.

The framework
-------------

ORE is organized around three linked but distinct analytical domains:

.. centered:: Vulnerability → Resilience → Control

**Vulnerability** concerns a system's susceptibility to undesirable change.
It identifies relevant scenarios, system states, likelihood information,
consequences, operational boundaries, and the analytical perspectives used to
evaluate them.

**Resilience** concerns the capacities, strategies, and engineering designs
through which a system can preserve, extend, recover, or improve acceptable
performance under disturbance.

**Control** concerns the continuing processes through which systems sense
conditions, anticipate future challenges, act through feasible interventions,
and learn from resulting performance.

This sequence is analytical rather than chronological. Vulnerability does not
occur only before a disruption, resilience does not occur only during or after
a disruption, and control is not merely a final implementation step. Together,
they describe how a system can be evaluated, improved, and managed over time.

From data to decisions
----------------------

A central ORE principle is:

.. centered:: Data → Perspective → Decisions

Engineering-system data do not independently determine a decision. Analysts
must first interpret information about system states, likelihoods,
consequences, performance, constraints, and feasible actions. That
interpretation establishes a perspective through which vulnerabilities,
resilience strategies, and control actions can be evaluated.

For example, the same vulnerability data can support distinct perspectives on
risk, reliability, adversary, and safety. Those perspectives can preserve
different information, prioritize different system conditions, and recommend
different engineering designs. ORE therefore treats perspective as an explicit
part of quantitative analysis rather than an implicit assumption.

Current focus
-------------

The present formal foundation of ORE is quantitative vulnerability analysis.
The developing theory defines a vulnerability space composed of scenarios,
likelihood information, and consequence information:

.. math::

   \mathcal{V} = (S,L,C).

Within this framework, risk is one perspective on vulnerability rather than
the general category for all vulnerability analysis. Reliability, adversary,
and safety are likewise treated as distinct perspectives that can reveal
different engineering-system concerns and decision tradeoffs.

Future ORE work will connect these vulnerability perspectives to a formal
resilience framework organized around robustness, rebound, extensibility, and
evolvability, and to a control framework organized around sensing,
anticipating, acting, and learning.

Navigating ORE
--------------

* :doc:`foundations` describes the research traditions and conceptual
  distinctions informing ORE.

* :doc:`theory` presents the developing vulnerability, resilience, and control
  architecture.

* :doc:`research-path` lists anticipated research outputs.

* :doc:`artifacts` will provide citable papers, technical notes, code, and
  other released research materials.