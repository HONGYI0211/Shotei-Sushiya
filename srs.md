# Software Requirements Specification (SRS): Shōtei Sushi-ya

## 1. System Architecture & Frameworks
The interactive digital experience will be built strictly using Python, relying on two primary libraries to handle rendering and logic.

*   **Python Arcade (`arcade`):** The core engine used for 2D rendering, window management, sprite handling, particle emission, and capturing event-driven user inputs (keyboard/mouse).
*   **Pydantic (`pydantic`):** Used for strict data validation and state management across the game's scenes, ensuring that inventory and scores are correctly typed and safely passed between Arcade Views.

## 2. State Management Design
To facilitate collaboration among the four team members, the game will use a centralized state manager rather than global variables. 

```python
from pydantic import BaseModel
from typing import List

class GameState(BaseModel):
    chosen_menu: str = "omakase"
    caught_fish: List[str] = []
    zen_score: int = 0
    legendary_fish_unlocked: bool = False
```
*Implementation:* Each scene (e.g., `Scene1_Arrival(arcade.View)`) will accept a `GameState` instance upon initialization. When a scene ends, it updates the `GameState` and passes it to the next scene's View, ensuring seamless data flow.

## 3. Event-Driven Interaction Model
Unlike traditional procedural loops, the game relies on Arcade's built-in event handlers:
*   `on_mouse_press()` / `on_mouse_drag()`: Used in Scene 2 (casting the line) and Scene 3 (dragging the knife to slice fish).
*   `on_key_press()`: Used primarily in Scene 1 and Scene 2 for WASD character movement around the islands.
*   `on_update(delta_time)`: Used exclusively for updating special effects (e.g., updating particle lifespans, moving animated sprites, and glowing aura interpolation).

## 4. Special Effects Implementation Strategy
To ensure high marks for the CT029-3-2 module, the team will utilize specific Arcade features:
*   **Particle Systems:** Using `arcade.Emitter` and `arcade.FadeParticle` for water splashes, fluid splatter, steam, and coin bursts.
*   **Lighting/Glows:** Utilizing alpha blending and `arcade.Sprite` color tinting to create the glowing effect for the legendary fish and the lanterns in Scene 4.
*   **Animation:** Using `arcade.AnimatedTimeBasedSprite` for the boat rocking and environmental animations to ensure they remain smooth regardless of frame rate.
