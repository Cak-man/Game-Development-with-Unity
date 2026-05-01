# 🔦 Modular Horror Game Systems for Unity

This repository contains a collection of essential, modular C# scripts designed for 3D first-person horror games in Unity[cite: 1]. It covers core gameplay mechanics including inventory management, smart AI, hiding systems, and environmental interactions[cite: 1].

## 🛠 Features

### 1. Interaction & Inventory Logic
*   **Raycast Interaction:** Handles world interactions (doors, items, switches) via a central raycasting system from the player's camera[cite: 1].
*   **Name-Based Key System:** Uses a global `ItemData` class to track the last collected item, allowing doors to be unlocked if their name matches the held item[cite: 1].
*   **Physics-Based Pickups:** Collectible items can be parented to the player's hand or inventory transform upon interaction[cite: 1].

### 2. Advanced Enemy AI (Monster)
*   **Patrol & Destination System:** The AI moves between a series of predefined waypoints using Unity's `NavMeshAgent`[cite: 1].
*   **Detection & Chase:** Implements a Line-of-Sight check; if the player is within `sightDistance` and not behind cover, the AI initiates a chase[cite: 1].
*   **Jumpscare Mechanism:** Automatically triggers a jumpscare UI and camera sequence when the distance to the player is less than the `catchDistance`[cite: 1].

### 3. Hiding & Stealth
*   **Safe Zones:** Players can interact with objects like wardrobes to hide, which disables the player controller and switches to a "hiding camera"[cite: 1].
*   **Dynamic Aggro:** Enemies will stop chasing and return to patrol if the player hides and stays beyond a certain `loseDistance`[cite: 1].

### 4. Flashlight & Lighting
*   **Auto-Flashlight:** A specialized script that activates the flashlight automatically when it is picked up by the player[cite: 1].
*   **Light Switch System:** Allows players to toggle scene lights (Spotlights/Point Lights) using the interaction system[cite: 1].

---

## 🚀 Setup Instructions

1.  **NavMesh Setup:**
    *   Ensure your environment is marked as **Static**[cite: 1].
    *   Go to `Window > AI > Navigation` and click **Bake** so the AI can move[cite: 1].

2.  **Tagging:**
    *   Assign the following Tags in your Unity project: `Player`, `Collectible`, `Door`, `LockedDoor`, and `Light`[cite: 1].

3.  **Hierarchy Configuration:**
    *   Assign your UI elements (Jumpscare Image, Interaction Text) to the corresponding slots in the `FirstPersonController` and `EnemyAI` inspectors[cite: 1].

---

## 📂 Script Directory

| Script | Function |
| :--- | :--- |
| **FirstPersonController.cs** | Core movement, interaction raycasting, and UI management[cite: 1]. |
| **EnemyAI.cs** | Manages NavMesh movement, player detection, and the jumpscare trigger[cite: 1]. |
| **HidingPlace.cs** | Switches player states and cameras for stealth gameplay[cite: 1]. |
| **ItemData.cs** | A static helper class for cross-script item data storage[cite: 1]. |
| **LightButtonController.cs** | Simple toggle logic for environmental lighting[cite: 1]. |

---

## 📝 Usage Example: Key & Door
To create a locked door:
1.  Place a key object and name it `LaboratoryKey`[cite: 1].
2.  Set its Tag to `Collectible`[cite: 1].
3.  Place a door object, set its Tag to `LockedDoor`, and name it exactly `LaboratoryKey`[cite: 1].
4.  The system will automatically match the names to unlock the door when interacted with[cite: 1].

---
*Developed for Unity developers looking for a quick-start foundation in the horror genre.*
