# Analysis & Breakdown: Shōtei Sushi-ya

## 1. Workload Matrix (Scene Allocation)
As per the assignment requirements, the group consists of four students, with each member taking full ownership of one scene's logic, assets, and special effects.

| Team Member | Scene Allocation | Primary Responsibilities | Key Special Effects |
| :--- | :--- | :--- | :--- |
| **Member 1** | **Scene 1: The Arrival** | Implement main menu, character movement (WASD) on the main island, and scene transition to Scene 2. | Ambient water ripples, boat rocking animation, wave/seagull audio. |
| **Member 2** | **Scene 2: The Catch** | Implement the fishing mini-game mechanics, collision detection for the bobber, and random fish generation. | Dynamic water splash particles, glowing aura (legendary fish), splash/reel audio. |
| **Member 3** | **Scene 3: The Preparation** | Implement the preparation mini-game (mouse drag for knife cuts), and logic for evaluating cut precision (Zen Meter). | Fluid splatter particles, motion-tracked knife swooshes, chopping audio. |
| **Member 4** | **Scene 4: The Feast** | Implement the final dining logic, calculate the final score/bill, and handle the game-over/restart loop. | Object transformation (raw to plated), steam particles, coin bursts, UI glows. |

## 2. Asset Plan
The project requires a cohesive set of visual and audio assets to maintain the "Relaxing & Zen" aesthetic.

### Visual Assets (Sprites & Environments)
*   **Characters:** Player Character (Customer), Zen Master (NPC), Host (NPC).
*   **Environments:** 
    *   Scene 1: Main island dock, sushi house exterior, reception desk.
    *   Scene 2: Ocean view, small boat, fishing rod.
    *   Scene 3: Cutting board, ocean backdrop, knife.
    *   Scene 4: Wooden dining table, glowing lanterns, dusk sky.
*   **Food/Items:** Assorted fish (normal and glowing legendary variants), seaweed, rice, plated sushi (various types), coins.

### Audio Assets
*   **Background Music (BGM):** Lo-fi traditional Japanese instrumentals (Shamisen/Koto) that loop seamlessly across all scenes.
*   **Sound Effects (SFX):**
    *   *Nature:* Waves crashing, seagulls, wind.
    *   *Action:* Fishing reel click, heavy splash, rhythmic knife chop, fluid squelch.
    *   *UI/Feedback:* Menu click, coin clink, success chime (Zen Meter level up).

### Technical Assets (Pydantic / Logic)
*   `GameState` JSON schema (for saving/loading states during debugging).
