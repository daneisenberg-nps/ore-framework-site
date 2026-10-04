Theory
======

Operational Resilience Engineering is organized around three linked but
distinct analytical domains:

.. centered:: Vulnerability → Resilience → Control

The sequence is analytical, not chronological. Vulnerability characterizes
susceptibility to undesirable change and the perspectives used to evaluate it.
Resilience characterizes capacities and design choices that preserve, extend,
recover, or improve acceptable performance under disturbance. Control
characterizes the processes through which a system senses, anticipates, acts,
and learns as conditions change.

The present vulnerability formulation is developed in
*Towards a Theory of Quantitative Vulnerability Analysis for Engineering
Systems*, a manuscript submitted to arXiv and intended for subsequent
peer-review submission :cite:p:`eisenbergAlderson2026vulnerability`. The resilience and control formulations presented
below are developing research directions.

Vulnerability
-------------

ORE defines the vulnerability of an engineering system in terms of its
susceptibility to undesirable change. A quantitative vulnerability analysis
begins with a vulnerability space:

.. math::

   \mathcal{V} = (S, L, C),

where:

* :math:`S` is a set of scenarios or system states describing what can go
  wrong;
* :math:`L : S \rightarrow [0,1]` represents information about the
  likelihood of each scenario; and
* :math:`C : S \rightarrow \mathbb{R}_{\geq 0}` represents information about
  the adverse consequence associated with each scenario.

The tuple :math:`\mathcal{V} = (S,L,C)` is not itself a risk measure.
It contains vulnerability data that must be interpreted before it can support
a quantitative evaluation or an engineering decision.

Data, perspectives, and decisions
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The central claim of the framework is:

.. centered:: Data → Perspective → Decisions

An interpretation maps likelihood and consequence data into a mathematical
form that supports a particular class of vulnerability measures. A
vulnerability perspective is a specific combination of likelihood and
consequence interpretations. Perspective is therefore not merely a verbal
description of an analyst's viewpoint; it has formal mathematical content.

Taking a perspective is necessary for quantitative decision-making, but it
also narrows the information brought forward for evaluation. No single
perspective is expected to reveal every relevant vulnerability of a complex
engineering system.

Four vulnerability perspectives
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The current theory identifies four foundational perspectives on a vulnerability
space. They differ according to whether likelihood is interpreted as
probability or possibility, and whether consequence is interpreted as a
numeric value or as membership in a category or performance set.

.. list-table:: Vulnerability perspectives for engineering systems
   :header-rows: 1
   :widths: 19 27 27 27

   * - Likelihood interpretation
     - Consequence interpretation
     - Perspective
     - Representative measures
   * - Probability

       :math:`P(S)`
     - Numeric or scaled value

       :math:`G(S)`
     - **Risk**

       :math:`\mathrm{Risk} = (P,G)`
     - Expected loss; expected consequence; value-at-risk; conditional
       value-at-risk; expected unserved energy
   * - Probability

       :math:`P(S)`
     - Set-value or category

       :math:`\Gamma(S)`
     - **Reliability**

       :math:`\mathrm{Reliability} = (P,\Gamma)`
     - Probability of failure; availability; mean time to failure; loss-of-load
       probability; interruption indices
   * - Possibility

       :math:`\Pi(S)`
     - Numeric or scaled value

       :math:`G(S)`
     - **Adversary**

       :math:`\mathrm{Adversary} = (\Pi,G)`
     - Network interdiction; maximum load shed; worst-case contingency
       performance; failure-budget analysis
   * - Possibility

       :math:`\Pi(S)`
     - Set-value or category

       :math:`\Gamma(S)`
     - **Safety**

       :math:`\mathrm{Safety} = (\Pi,\Gamma)`
     - Security criteria; reachability analysis; reserve margins; minimum
       contingency budget to violation

Here, :math:`P` maps likelihood information to a probability distribution and
:math:`\Pi` maps it to a possibility distribution. :math:`G` maps
consequence information to a scalar value, whereas :math:`\Gamma` maps it to
a category, group, or performance classification.

For a binary operational boundary :math:`\tau`, a consequence interpretation
can be written:

.. math::

   \Gamma_{\tau}(s) =
   \begin{cases}
   \text{operational}, & C(s) < \tau, \\
   \text{non-operational}, & C(s) \geq \tau.
   \end{cases}

This distinction matters because each perspective retains, aggregates, and
orders vulnerability data differently. Therefore, different perspectives can
favor different engineering designs even when they are evaluated using the
same scenarios and the same underlying system data.

Risk is not reliability
~~~~~~~~~~~~~~~~~~~~~~~

Risk and reliability are not interchangeable measures of the same system
property. In the current formulation, risk applies probability to a
scalar-valued consequence interpretation:

.. math::

   \mathrm{Risk} = (P,G).

Reliability applies probability to a categorical or thresholded consequence
interpretation:

.. math::

   \mathrm{Reliability} = (P,\Gamma).

For example, a common expected-consequence risk measure is:

.. math::

   V^{\mathrm{risk}} =
   \sum_{s \in S} p(s) C(s),

while a threshold-based unreliability measure is:

.. math::

   V^{\mathrm{unreliable}} =
   \sum_{s \in F(\tau)} p(s),

where :math:`F(\tau) = \{s \in S : C(s) \geq \tau\}` is the set of
non-operational states.

The first measure preserves relative consequence magnitudes. The second
groups all states beyond an operational boundary into a common category.
Consequently, risk and reliability can rank vulnerabilities differently and
can recommend different designs. Neither should generally be assumed to be a
special case, substitute, or synonym for the other.

Adversary and safety perspectives
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Probability is not the only coherent interpretation of likelihood information.
A possibility interpretation changes how likelihoods are normalized,
combined, and compared. Possibility-based perspectives are especially relevant
when the task concerns plausible worst cases, adversarial action, security
criteria, or reachability of unacceptable states.

The adversary perspective is:

.. math::

   \mathrm{Adversary} = (\Pi,G),

and emphasizes a scalar-valued consequence among plausible scenarios. A simple
worst-case measure is:

.. math::

   V^{\mathrm{adversary}} =
   \max_{s \in S} C(s).

The safety perspective is:

.. math::

   \mathrm{Safety} = (\Pi,\Gamma),

and combines possibility-based likelihood with a categorical interpretation of
whether system performance remains within an acceptable boundary. A
representative safety measure is:

.. math::

   V^{\mathrm{unsafe}} =
   \max_{s \in F(\tau)} \pi(s).

The theory therefore distinguishes risk, reliability, adversary, and safety as
co-constituted perspectives on a common vulnerability space. It does not treat
one as the parent category of the others.

Implications for decisions
~~~~~~~~~~~~~~~~~~~~~~~~~~

A vulnerability measure does more than assign a numerical score. It determines
which features of system behavior are prioritized in a design decision.

For example, a risk perspective may favor an intervention that reduces a rare
but catastrophic consequence. A reliability perspective may instead favor an
intervention that reduces the more frequent crossing of an operational
threshold. An adversary perspective can prioritize the most consequential
plausible attack or disruption, while a safety perspective can prioritize the
possibility of reaching an unacceptable state.

A design that improves one perspective need not improve another. When this
occurs, the problem is not resolved simply by treating all measures as
synonyms, nor necessarily by combining them into a single aggregate score.
Rather, the decision-maker must identify and justify the tradeoffs among
distinct vulnerability perspectives.

Resilience
----------

Vulnerability and resilience are distinct, interacting, and mutually
constitutive concepts. Vulnerability analysis can characterize the states,
boundaries, likelihoods, consequences, and perspectives through which a system
is susceptible to undesirable change. It does not by itself identify what
capabilities, strategies, designs, or interventions should be created to
maintain or improve system performance.

Resilience addresses that complementary question: how can an engineering
system preserve, extend, recover, or improve acceptable performance under
disturbance and changing conditions?

ORE does not treat resilience as inverse of vulnerability, but instead it focuses on evaluating alternative designs, policies, configurations, and
capabilities intended to change system performance in relation to disturbance Specifically, ORE organizes resilience into four perspectives on how new design can change system vulnerability along two dimensions:

* **Direction of change:** continuity or improvement.
* **Analytical object:** state stability or the operational boundary.

State stability concerns whether current performance should be maintained or
improved. Operational boundary concerns the feasible range of states, conditions, resources, and constraints within which acceptable operation can be sustained.

The developing ORE resilience framework is as follows:

.. list-table:: Developing resilience framework
   :header-rows: 1
   :widths: 28 36 36

   * -
     - State Stability
     - Operational Boundary
   * - Continuity
     - **Robustness**

       Maintaining acceptable performance in the current state despite
       disturbance.
     - **Extensibility**

       Extending the feasible operational boundary or available adaptive
       capacity beyond the current state.
   * - Improvement
     - **Rebound**

       Improving performance in the current or recovered state following
       disturbance.
     - **Evolvability**

       Changing the operator model, strategy space, constraints, or feasible
       possibilities to improve future performance.

This formulation is informed by Woods's four concepts of resilience:
robustness, rebound, graceful extensibility, and sustained adaptability
:cite:p:`woods2015,woods2018`. The ORE framework is a developing formal
interpretation; it does not claim to reproduce Woods's theory or terminology
exactly.

Woods cautions against treating rebound and robustness as complete accounts of
resilience, particularly when a system encounters surprise, approaches the
limits of its ordinary adaptive capacity, or must remain capable of adapting
through continuing change. ORE agrees that robustness and rebound alone are
incomplete. However, it treats both as worthy engineering design strategies
when the analytical objective concerns system stability. The intended
contribution is to integrate these commonly applied state-stability strategies
with boundary-oriented capabilities informed by Woods's treatment of graceful
extensibility and sustained adaptability in the Theory of Graceful
Extensibility (TGE) :cite:p:`woods2018`.

**Extensibility** concerns the ability to preserve acceptable operation by
stretching or extending available adaptive capacity when a system approaches
or exceeds its established operational boundary. In the present ORE
formulation, extensibility can make disruption or failure-mode operation less
harmful without necessarily improving normal-operation performance.

**Evolvability** concerns improvement in system function through changes to the
operator model, strategy space, constraints, resources, or other conditions
that expand or improve the system's future feasible possibilities. In the
present formulation, evolvability differs from extensibility: rather than
primarily reducing the consequences of a disrupted state, it uses information,
experience, or capabilities generated through disruption to improve benefits
during future normal operation.


Control
-------

Control concerns the continuing processes that relate observed conditions and
vulnerability information to resilient action. In ORE, control follows the
identification of relevant vulnerabilities and the specification of resilience
capacities.

The developing control framework will connect vulnerability and resilience to four resilience-engineering processes:

* **Sensing:** detecting system performance, disturbances, constraints, and
  conditions near operational boundaries.
* **Anticipating:** identifying possible future states, demands, threats,
  opportunities, and boundary challenges.
* **Acting:** selecting and implementing feasible interventions, designs, or
  operational strategies.
* **Learning:** revising models, operational boundaries, strategies, and
  intervention choices from both successful and unsuccessful performance.

The control formulation will ultimately specify how sensing and interpretation
identify vulnerability; how anticipation and action invoke resilience
capacities; and how learning changes the future decision model.

Sensing, anticipating, acting, and learning
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The developing ORE control formulation treats resilient performance as a
continuing process of sensing conditions, anticipating future challenges,
acting through feasible interventions, and learning from the consequences of
action.

This process-oriented account builds on resilience engineering work that links
human, organizational, and technical capacities in national infrastructure
resilience :cite:p:`thomas2019resilience`. It also responds to the central
challenge of surprise in critical infrastructure: the objective is not to
assume that all disruptive conditions can be predicted or eliminated, but to
prepare systems and their operators to recognize, respond to, and learn from
conditions that exceed existing expectations
:cite:p:`alderson2022surprise,seager2025infrastructure`.

The vocabulary of resilience remains highly context-dependent across critical
infrastructure research. ORE therefore makes its use of vulnerability,
resilience, state stability, operational boundary, and control processes
explicit rather than assuming that these terms are interchangeable
:cite:p:`mentges2023resilience`.

The SAAL processes do not presume that surprise can be eliminated. Instead,
they organize how an engineering system and its operators can detect changing
conditions, anticipate plausible futures, select and implement feasible
actions, and revise the system's future decision model through learning
:cite:p:`alderson2022surprise,seager2025infrastructure`.


Research status
---------------

The vulnerability-space theory and its four perspectives are described in the
current manuscript, *Towards a Theory of Quantitative Vulnerability Analysis
for Engineering Systems*. The manuscript is being prepared for public hosting
and subsequent peer review.

The resilience and control sections state the intended architecture of
Operational Resilience Engineering. Their formal notation, propositions,
decision models, and engineering examples remain under active development and
will be released as versioned technical notes, preprints, and publications.