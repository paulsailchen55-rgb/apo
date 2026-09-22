# Workflow Archive — 2026-09-22

## Topic
Stage 1: Initial five-choice menu and open-source prototype principle

## Status
PROPOSED / AGREED AS A STARTING DESIGN, NOT YET TESTED

## Decision Summary
The initial interaction may begin with five menu choices. Five is a practical starting point, not a permanent requirement or universal standard. The open-source project should publish a functional prototype that people can try, evaluate, adapt, and replace with their own variations.

The five-choice structure also has a human-interface association with the five fingers of a hand. This is an illustrative design reference, not a technical limitation, accessibility claim, or requirement that every future interface use five choices.

## Initial Menu Concept

1. **Choose the closest location**
   - Begin with the nearest authorized food-access location or nearby directional options.
   - The person may then enter further information, directions, and access decisions.

2. **Compare nearby locations**
   - Compare nearby authorized locations and what each one provides.
   - The system should avoid forcing a food-preference questionnaire before showing local options.

3. **Check whether I can get there**
   - Consider route feasibility, return feasibility, and access feasibility.
   - Relevant factors may include distance, terrain, entrances, stairs, mobility constraints, and the ability to carry food back.

4. **Get more information**
   - This is a cross-cutting function that may also be available within other branches, including the closest-location and comparison branches.
   - Information should be provided in small, decision-relevant portions, with optional expansion.

5. **Something else**
   - Provide pathways such as changing location, asking for help, returning to the main menu, pausing, cancelling, or changing the current goal.

## Interaction Principle
The menu is not a set of isolated destinations. Branches can lead into one another. For example, selecting the closest location may lead to more information, travel-capability checks, directions, correction, or a return to another choice.

The interaction should support reversible movement through the decision path. Backtracking, changing a choice, detouring, pausing, or cancelling should be treated as continued progress toward the current or next journey rather than as failure.

## Keypad and Voice Relationship
The initial menu is intended to be compatible with a standard phone keypad and text-first or voice-supported interaction. A user may select a numbered option by pressing a number or speaking the number in a supported language. Exact assignments for `*`, `#`, and `0` remain PROPOSED and require testing.

## Open-Source Principle
The repository should provide a working baseline rather than claim to provide the final or only correct design. Contributors and communities may:

- Change the number of choices.
- Rename or reorganize menu items.
- Add language and cultural interpretation layers.
- Adapt the interface for different devices or access needs.
- Test alternative navigation models.
- Document their changes and results.

The baseline must clearly distinguish established requirements from proposed choices and experimental alternatives.

## Evidence Classification

- **KNOWN:** The user approved the five-choice menu as a useful starting point and agreed that menu functions may overlap across branches.
- **PROPOSED:** The specific wording and ordering of the five menu choices.
- **PROPOSED:** The relationship between the menu and keypad/voice navigation.
- **NOT TESTED:** Whether five choices are optimal for different users, devices, languages, literacy levels, or situations.
- **UNKNOWN:** Whether a different number of choices produces better completion, comprehension, correction, or accessibility outcomes.

## Next Workflow Step
Proceed from the Stage 1 menu decision toward Stage 2: design the AI workflow. The next stage should specify how the system interprets a request, resolves location uncertainty, discovers nearby authorized resources, presents choices, handles corrections, and preserves user control without requiring a large initial questionnaire.
