# Protocolo de Mudanças Materiais entre Business/Operations e Application Engineering

## Principle

The two tracks operate independently. Cross-boundary communication exists only when a change materially affects the other track.

`PARALLEL OWNERSHIP + MATERIAL BOUNDARY COMMUNICATION`

Administrative status messages are not part of the operating model.

## Business-to-technical change object

When an approved business change requires application change, the change object should contain:

- `CHANGE_ID`
- date/version
- affected business object/control
- reason
- previous approved behavior
- new approved behavior
- data impact
- UX impact, when known
- migration/compatibility considerations
- acceptance criteria
- priority
- approval/provenance

Cowork implements the change under its technical authority. No routine acknowledgement is required.

## Technical-to-business exception

Cowork should escalate only when a technical fact materially requires a business decision, for example:

- a platform limitation makes an approved rule impossible or materially different;
- a security constraint changes the user flow or responsibilities;
- a data-model restriction would alter meaning or auditability;
- a deployment/access restriction changes who can use the system;
- a proposed simplification would remove a material control.

The escalation must isolate the decision required and avoid administrative narrative.

## No-status-traffic rule

Do not generate cross-platform messages whose only purpose is:
- “what did you do?”;
- “confirm receipt”;
- “we are still working”;
- “send status”;
- “wait for the other AI”;
- “tell the other AI that this phase ended.”

A message must materially change an object, requirement, risk, decision, infrastructure condition or acceptance state.

