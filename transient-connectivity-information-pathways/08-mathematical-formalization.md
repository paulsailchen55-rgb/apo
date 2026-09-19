# 08 — Mathematical Formalization: First Working Vocabulary

This is a starting vocabulary, not a finished theory.

Let A and B be two regions or systems.

S_A(t), S_B(t) = their states.

C(t) = coupling between them.

P(t) = pathway availability.

I(A→B | t) = information about A recoverable at B.

T = duration of usable connectivity.

A transient pathway can be represented schematically by P(t) > 0 only during a finite interval.

## Information measures

The project should first examine established quantities rather than inventing new ones unnecessarily:

- mutual information;
- conditional mutual information;
- channel capacity;
- transfer entropy;
- causal intervention;
- network information flow.

## Representation

Let R0 be an originating representation and Rn a representation after n transformations.

A future fidelity measure may be:

F(R0,Rn)

and distortion:

D(R0,Rn) = 1 - F(R0,Rn)

The central unresolved problem is how to define fidelity across representations with different forms.

## Observation

A generic measurement interaction can be represented as:

(X,O) → (X',O')

where X is a system and O an observer/measurement apparatus.

## Restoration

Let M be a mediation or transformation operation:

M(X) = X'

A restoration criterion must be independently defined; the model should not assume that "better" has a universal numerical meaning.

## Graph model

The framework may eventually become a directed graph:

SOURCE → REPRESENTATION → CHANNEL → RECEIVER → TRANSFORMATION → NEW STATE

with optional feedback:

NEW STATE → FEEDBACK CHANNEL → SOURCE

The sink experiment can supply a physical example of coupled dynamics while information theory supplies the formal language for transmission.
