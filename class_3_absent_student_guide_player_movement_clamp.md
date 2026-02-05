# MIDNIGHT LARK: Unity Game Development Foundations
## Class 3 — Player Movement (4-Direction) + Screen Clamp

### Purpose of This Guide (Read First)
This guide is written **specifically for students who were absent in Class 3**.

If you follow this document step by step **without skipping anything**, you will be able to:
- Understand **what was taught in Class 3**
- **Implement exactly the same result** as done in the live class
- End with a **working Player movement system** with proper screen boundaries

This guide is **self-sufficient**. No prior explanation from the class is required.

---

### If You Get Stuck
If at any point you face a problem:
1. First, **contact classmates who were present in Class 3**
2. If the issue is **not solved**, then **connect with the instructors**

This order is important.

---

## Class 3 Final Goal (What You Must Achieve)
By the end of this guide, your project must meet **all** of these conditions:

- Player moves in **4 directions** (Up, Down, Left, Right)
- Movement speed is **constant** (no acceleration)
- Player **cannot leave the screen** (position is clamped)

---

## Open the Correct Project and Scene

1. Open **Unity Hub**
2. Open your existing project from earlier classes
3. From the Project window, open:
   - `Scenes → Starflight_Main`
4. Press ▶ **Play** once

If the game runs without red errors in the Console, continue.
If there are red errors, **fix them first**.

---

## Check the Player GameObject

1. In the **Hierarchy**, click on **Player**
2. In the **Inspector**, confirm:
   - Transform component exists
   - A visible sprite is attached
3. Reset Position:
   - Position X = `0`
   - Position Y = `0`
   - Position Z = `0`

---

## Create the Movement Script

### Step 3.1 — Create Script

1. In the **Project** window:
   - Right-click ont **Scripts** → Click **Create** → Click **Scripting** → Click **Empty C# Script**
2. Name it exactly:
   ```
   PlayerController
   ```

3. Double-click the script to open it

---

### Step 3.2 — Basic Movement Code

Replace **everything** inside the script with the following code:

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    [Header("Movement")]
    public float moveSpeed = 5f;

    private void Update()
    {
        float x = Input.GetAxisRaw("Horizontal");
        float y = Input.GetAxisRaw("Vertical");

        Vector3 move = new Vector3(x, y, 0f).normalized;
        transform.position += move * moveSpeed * Time.deltaTime;
    }
}
```

### What This Code Does (Simple Explanation)
- `Input.GetAxisRaw("Horizontal")`
  - Reads **A / D** or **Left / Right Arrow**
- `Input.GetAxisRaw("Vertical")`
  - Reads **W / S** or **Up / Down Arrow**
- `normalized`
  - Ensures **same speed in all directions**
- `Time.deltaTime`
  - Makes movement **frame-rate independent**

---

## Attach Script to Player

1. Select **Player** in Hierarchy
2. Drag **PlayerController** script onto the Player (or Click **Player** from Higherarchy then **Add Component** from Insperctor and **PlayerController** from dropdown list)

▶ Press **Play**

Player should now move in 4 directions  
Player can still leave the screen — this is expected

---

## Add Screen Clamp (Boundary Lock)

Now we will stop the player from leaving the screen.

### Step 5.1 — Replace Script with Clamp Version

Open **PlayerController.cs** again and replace the code with:

```csharp
using UnityEngine;

public class PlayerController : MonoBehaviour
{
    [Header("Movement")]
    public float moveSpeed = 5f;

    [Header("Clamp Bounds (World Units)")]
    public float minX = -8f;
    public float maxX =  8f;
    public float minY = -4f;
    public float maxY =  4f;

    private void Update()
    {
        // 1) Movement (constant speed)
        float x = Input.GetAxisRaw("Horizontal");
        float y = Input.GetAxisRaw("Vertical");

        Vector3 move = new Vector3(x, y, 0f).normalized;
        transform.position += move * moveSpeed * Time.deltaTime;

        // 2) Clamp (keep inside bounds)
        Vector3 p = transform.position;
        p.x = Mathf.Clamp(p.x, minX, maxX);
        p.y = Mathf.Clamp(p.y, minY, maxY);
        transform.position = p;
    }
}
```

---

### What Clamp Means (Very Important)
- `Mathf.Clamp(value, min, max)`
- It **forces a value to stay inside a range**

So:
- Player **cannot go left** of `minX`
- Player **cannot go right** of `maxX`
- Player **cannot go up** of `maxY`
- Player **cannot go down** of `minY`

---

## Test and Adjust Bounds

1. Press ▶ **Play**
2. Move player to screen edges
3. If player stops too early or too late:
   - Adjust values in Inspector:
     - `minX`, `maxX`, `minY`, `maxY`

Goal: Player stays fully visible inside Game view

---

## Final Checklist (Must Match Class 3)

✔ 4-direction movement
✔ Constant speed
✔ Player locked inside screen
✔ Clean, readable Inspector headers

---

### You Are Now Aligned with Class 3
If you have completed everything above successfully, **you are fully caught up with Class 3** of:

**MIDNIGHT LARK: Unity Game Development Foundations**

You are ready to continue with the next class.
