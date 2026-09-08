# Project Proposal: Shōtei Sushi-ya

## 1. Introduction & Core Concept
**Shōtei Sushi-ya** is a 2D interactive digital dining experience developed using the Python Arcade library. Designed for the CT029-3-2 Imaging and Special Effects module, the game reimagines the traditional restaurant visit as a premium, island-hopping adventure. 

Instead of playing as a chef in a static kitchen, the player acts as a **Customer** who embarks on a "Relaxing & Zen" journey to source, prepare, and enjoy their own meal. The experience is accompanied by lo-fi traditional music, smooth scene transitions, and satisfying visual effects. The overarching objective is to provide a seamless, event-driven journey that naturally integrates complex special effects (such as particle generation and fluid dynamics) into a calm gameplay loop.

## 2. Narrative & Storyboard
The narrative unfolds over a single day, taking the customer across an archipelago dedicated to the ultimate sushi experience.

*   **Scene 1: The Arrival & Menu Selection**
    *   **Setting:** A serene main island dock and the reception of Shōtei Sushi-ya.
    *   **Plot:** The customer arrives by boat. They interact with the Host to select their desired omakase menu, establishing the goals for the day.
    *   **Mechanics:** UI interactions for menu selection, ambient environment effects (water ripples, gentle breeze).

*   **Scene 2: The Catch**
    *   **Setting:** A secluded neighboring island known for legendary marine life.
    *   **Plot:** The customer sails to the fishing spot. They must catch the specific ingredients required for their chosen menu, including a rare, supernatural glowing fish.
    *   **Mechanics:** Timing-based fishing mini-game with water splash particles and glowing sprite auras.

*   **Scene 3: The Preparation**
    *   **Setting:** An open-air preparation station overlooking the ocean.
    *   **Plot:** Guided by a Zen Master, the customer prepares their catch. They slice the fish and roll the sushi themselves.
    *   **Mechanics:** Precision clicking or rhythm mechanics for chopping, featuring fluid splatter effects and motion-tracked knife movements.

*   **Scene 4: The Feast & Departure**
    *   **Setting:** A beautiful, lantern-lit dining area at dusk.
    *   **Plot:** The customer finally eats their creation. After the meal, they settle their bill and sail away as night falls.
    *   **Mechanics:** Exaggerated, satisfying food transformation effects (from raw to plated to eaten), coin particle explosions during payment, and ambient steam/glow effects.

## 3. Game Mechanics & Scenes
The gameplay loop prioritizes event-driven interactions and a relaxing atmosphere over frantic time limits. 

*   **Controls:** The game utilizes a hybrid control scheme. Players use the keyboard (WASD/Arrows) to navigate their character around the islands, while the mouse is used for specific interactions (e.g., clicking to cast a fishing line, dragging the knife to slice fish).
*   **Progression & The "Zen Meter":** There are no strict timers, allowing players to enjoy the scenery. Instead, progression is tied to completing event-driven tasks. A unique "Zen Meter" tracks the player's precision and calmness (e.g., perfect knife cuts). Maxing out the Zen Meter unlocks special events, such as the appearance of the legendary glowing fish in Scene 2.
*   **State Management (Pydantic & Python Arcade):** To ensure seamless transitions between the four scenes, the game architecture uses **Pydantic** for rigorous state management. A central `GameState` model validates and safely passes critical variables—such as `chosen_menu`, `caught_fish_inventory`, and `zen_score`—between the independent Arcade `View` classes that make up each scene.

## 4. Special Effects Integration
To meet the core coursework objectives, *Shōtei Sushi-ya* heavily integrates both visual and audio special effects, distributed evenly across the four scenes so each team member can demonstrate technical proficiency:

*   **Scene 1 (The Arrival):** 
    *   *Visual:* Ambient water ripples using animated textures, smooth boat rocking animations, and dynamic UI hover effects for the menu.
    *   *Audio:* Gentle wave ambience and seagull sound effects triggered upon entering the scene.
*   **Scene 2 (The Catch):** 
    *   *Visual:* Dynamic water splash particle emitters when the bobber hits the water, and a pulsating glowing aura effect applied to the legendary fish sprite.
    *   *Audio:* Reel-in tension sounds and satisfying water splash sound effects synced to the particle generation.
*   **Scene 3 (The Preparation):** 
    *   *Visual:* Fluid splatter particle effects generated at the precise location of the knife cut, and motion-tracked swoosh trails following the player's mouse cursor.
    *   *Audio:* Rhythmic chopping and slicing sound clips that trigger strictly on event-driven knife interactions.
*   **Scene 4 (The Feast & Departure):** 
    *   *Visual:* Object transformation animations (morphing raw ingredients into beautifully plated sushi), ambient steam rising from hot tea (particle effects), warm lantern glow overlays, and UI coin bursts during payment.
    *   *Audio:* Satisfying eating sound effects and cash-register/coin clinking audio cues.
