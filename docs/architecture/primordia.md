# Primordia Engine Architecture

**Function:** Deterministic Advantage Inference ("Chess Engine for 40k")

## I. The Advantage Meter (20-0 Scale)

Primordia evaluates the board state using the **Dynamic Material Formula (DMF)**:

$$
\text{DMF} = \sum (\text{Material} \times \text{Lethality}) + (\text{Victory Points} \times \text{Momentum})
$$

Advantage is inferred by projecting $\Delta \text{VP}$ delta across Turn 5, mapped to a WTC-style **20-0 point differential**.

## II. Search & Pruning Logic

*   **Alpha-Beta Search:** Prunes branches that don't result in an Objective Flip or High-Efficiency Trade.
*   **Root Parallelization:** Scales search across home server CPU cores, assigning "Luck Profiles" (Optimistic/Pessimistic) to each core to handle dice variance.
*   **Mate in N:** Detection of **Alpha-Lock** (Tabling) or **Delta-Lock** (Points mathematically insurmountable).
