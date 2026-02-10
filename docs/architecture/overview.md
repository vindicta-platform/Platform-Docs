# Platform Overview

Vindicta's modular architecture explained.

---

## Design Philosophy

Vindicta follows a **modular monolith** approach:

- Each component is a standalone, independently deployable module
- Components communicate through well-defined interfaces
- The platform-core integrates all modules for unified deployment

```
┌─────────────────────────────────────────────────────────────┐
│                     Vindicta Platform                       │
├─────────────────────────────────────────────────────────────┤
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐    │
│  │ Logi-    │  │ Vindicta │  │ Vindicta │  │ Vindicta │    │
│  │ Slate UI │  │ CLI      │  │ API      │  │ Core     │    │
│  └────┬─────┘  └────┬─────┘  └────┬─────┘  └────┬─────┘    │
│       │             │             │             │          │
│  ─────┴─────────────┴─────────────┴─────────────┴──────    │
│                                                             │
│  ┌──────────┐  ┌──────────┐  ┌──────────┐  ┌──────────┐    │
│  │ Dice     │  │ Economy  │  │ Meta-    │  │ WARScribe│    │
│  │ Engine   │  │ Engine   │  │ Oracle   │  │ Core     │    │
│  └──────────┘  └──────────┘  └──────────┘  └──────────┘    │
└─────────────────────────────────────────────────────────────┘
```

## Core Modules

| Module                  | Purpose                                     |
| ----------------------- | ------------------------------------------- |
| **Vindicta Foundation** | Base models, Architecture, Constitution     |
| **Vindicta Engine**     | Physics, Dice, Entropy, Evaluation, AI Core |
| **Warscribe System**    | Notation, Parsing, Transcripts              |
| **Vindicta Economy**    | Ledger, GasTank, Transactions, Achievements |
| **Vindicta Oracle**     | Debate Council, Prediction, Agent Protocol  |
| **Vindicta Platform**   | API, Portal, UI Lib                         |
| **Vindicta Agents**     | SDKs, Workflows, Swarm                      |

## Data Flow

```
User → UI/CLI → API → [ Service Modules ] → Database
                           │
                    ┌──────┴──────┐
                    ↓             ↓
              Dice Engine   Meta-Oracle
```

---

## Deployment Options

1. **Full Platform** — All modules integrated
2. **Individual Modules** — Use specific components
3. **Self-Hosted** — Run on your infrastructure
