# Coding Comfort Companion–1
## An Extensive, Code-Heavy Practice Companion for Building Real Coding Confidence

---

## Very important — how to EXECUTE this companion
Please read this section once before touching any code.

---

## Step 1 — Create a practice scene
1. Open Unity
2. Create a **new empty scene**
3. Save it with any name (for example: `PracticeScene`)

---

## Step 2 — Create a practice GameObject
1. Right-click in the Hierarchy
2. Create → **Empty GameObject**
3. Rename it to `CodePractice`

This object will be your **practice container**.

---

## Step 3 — Create one script only
1. Right-click in the Project window
2. Create → **C# Script**
3. Name it `CodePracticeScript`
4. Drag this script onto the `CodePractice` GameObject

👉 **All code examples in this companion go inside this one script**, unless stated otherwise.

---

## Step 4 — How to practice each section
For **every section below**, follow this exact routine:

1. Type the code exactly as shown
2. Save the script
3. Press **Play**
4. Watch the **Console** or the Scene
5. Change **one thing only** (number, text, condition)
6. Press **Play** again

Do not rush forward.
**Confidence comes from repetition.**

---

## Step 5 — Practice mindset (important)
Always imagine a **simple real-life situation** behind the code.

Example thinking:
> “If something happens, I check a condition, then I react.”

That is all programming is.

---

## Core Intention of This Companion
This companion exists for one reason only:

👉 **After sustained practice, you should feel confident opening a script, writing code, changing code, and fixing simple issues on your own.**

This is:
- not a summary
- not exam notes
- not quick tips

This is a **long-form practice companion** meant to be revisited.

---

## What You Are Learning (Clarified)
You are learning:
- how to express ideas using code
- how to store information
- how to make decisions
- how to repeat actions
- how to connect logic with visible behavior

You are **not** learning academic computer science.

---

# PART 1 — VARIABLES: FULL CONTROL OVER VALUES

## 1.1 Understanding Variables Deeply
A variable is a **named place in memory**.

Real-life parallels:
- Jar → sugar
- Wallet → money
- Notebook → notes

In code:
- the **name** gives meaning
- the **type** controls what kind of value it can hold

---

## 1.2 Integer Variables (`int`)
```csharp
int apples = 5;
apples = 10;
apples = apples + 2;   // 12
apples += 3;           // 15
apples -= 4;           // 11
```

Read each line in plain English.

**Extended practice**
- Start from `0`
- Increase to `100`
- Decrease back to `0`

---

## 1.3 Floating Point Variables (`float`)
```csharp
float distance = 1.5f;
distance = 2.75f;
distance += 0.25f;
distance *= 2f;
distance /= 2f;
```

### Why `f` is important
In C#:
- `1.5` → **double** (default, 64-bit)
- `1.5f` → **float** (32-bit)

Unity uses **float everywhere** (movement, time, transforms, physics).

> **If a variable is `float`, every number touching it must use `f`.**

This avoids type mismatch errors and confusion.

---

## 1.4 Boolean Variables (`bool`)
```csharp
bool isLightOn = false;
isLightOn = true;
```

```csharp
bool hasPermission = true;
bool isLocked = false;
```

Booleans are **decision flags**:
- yes / no
- true / false
- allowed / blocked

---

## 1.5 String Variables (Text)
```csharp
string firstName = "Rina";
string lastName = "Khan";
string fullName = firstName + " " + lastName;
Debug.Log(fullName);
```

```csharp
string message = "Score: ";
int score = 42;
Debug.Log(message + score);
```

Strings are commonly used for:
- UI text
- messages
- debugging output

---

## 1.6 Inspector-Editable Variables
```csharp
public int lives = 3;
public float speed = 5f;
```

These are:
- visible in Inspector
- editable during Play
- accessible from other scripts

---

```csharp
[SerializeField] private float gravity = 9.8f;
```

### What `[SerializeField]` means
`[SerializeField]` tells Unity:

> “Show this variable in the Inspector and save its value, even though it’s private.”

Best practice:
- `public` → other scripts need access
- `[SerializeField] private` → Inspector-only access

Practice:
- change values in Inspector
- press Play
- observe results

---

## 1.7 Printing as Debugging
```csharp
int value = 7;
Debug.Log("Value is: " + value);
```

```csharp
Debug.LogWarning("This is a warning");
Debug.LogError("This is an error");
```

Printing is your **primary debugging tool**.

Use:
- `Debug.Log()` → normal information
- `Debug.LogWarning()` → suspicious state
- `Debug.LogError()` → broken logic

⚠️ `Console.WriteLine()` does **not** work in Unity.

---

# PART 2 — OPERATORS & EXPRESSIONS

## 2.1 Arithmetic Operators
```csharp
int x = 8;
int y = 3;
Debug.Log(x + y);
Debug.Log(x - y);
Debug.Log(x * y);
Debug.Log(x / y);
```

```csharp
float a = 8f;
float b = 3f;
Debug.Log(a / b);
```

---

## 2.2 Modulo Operator (`%`)
```csharp
int n = 10;
Debug.Log(n % 2); // 0
```

```csharp
int m = 11;
Debug.Log(m % 2); // 1
```

Used for:
- even / odd
- cycles
- repeating patterns

---

## 2.3 Comparison Operators
```csharp
int score = 55;
Debug.Log(score > 50);
Debug.Log(score >= 55);
Debug.Log(score < 100);
Debug.Log(score == 55);
Debug.Log(score != 10);
```

---

## 2.4 Logical Operators
```csharp
bool a1 = true;
bool a2 = false;

Debug.Log(a1 && a2);
Debug.Log(a1 || a2);
Debug.Log(!a1);
```

---

# PART 3 — CONDITIONS: DECISION MAKING

## 3.1 Basic `if`
```csharp
int temperature = 30;
if (temperature > 25)
{
    Debug.Log("Warm");
}
```

---

## 3.2 `if–else`
```csharp
int age = 16;
if (age >= 18)
{
    Debug.Log("Allowed");
}
else
{
    Debug.Log("Not allowed");
}
```

---

## 3.3 `else if` Chains
```csharp
int marks = 72;
if (marks >= 80)
{
    Debug.Log("Excellent");
}
else if (marks >= 60)
{
    Debug.Log("Good");
}
else
{
    Debug.Log("Needs improvement");
}
```

---

## 3.4 Nested Conditions
```csharp
int age = 20;
bool hasID = true;

if (age >= 18)
{
    if (hasID)
        Debug.Log("Access granted");
    else
        Debug.Log("ID required");
}
```

---

## 3.5 Switch Statements
```csharp
int option = 2;
switch (option)
{
    case 1:
        Debug.Log("Option 1");
        break;
    case 2:
        Debug.Log("Option 2");
        break;
    default:
        Debug.Log("Other option");
        break;
}
```

---

# PART 4 — LOOPS: CONTROLLED REPETITION

## 4.1 `for` Loop
```csharp
for (int i = 0; i < 5; i++)
{
    Debug.Log(i);
}
```

```csharp
for (int i = 10; i >= 1; i--)
{
    Debug.Log(i);
}
```

---

## 4.2 `while` Loop
```csharp
int i = 0;
while (i < 3)
{
    Debug.Log("Looping");
    i++;
}
```

---

## 4.3 `do–while` Loop
```csharp
int i = 0;
do
{
    Debug.Log(i);
    i++;
}
while (i < 3);
```

---

## 4.4 `break` and `continue`
```csharp
for (int i = 1; i <= 10; i++)
{
    if (i == 4) continue;
    if (i == 8) break;
    Debug.Log(i);
}
```

---

# PART 5 — FUNCTIONS: REUSABLE LOGIC

## 5.1 Functions Without Parameters
```csharp
void PrintLine()
{
    Debug.Log("----------------");
}
```

---

## 5.2 Functions With Parameters
```csharp
void PrintMessage(string msg)
{
    Debug.Log(msg);
}

PrintMessage("Hello");
PrintMessage("Welcome");
```

---

## 5.3 Functions With Return Values
```csharp
int Multiply(int a, int b)
{
    return a * b;
}
```

---

## 5.4 Combining Functions
```csharp
bool IsPositive(int n)
{
    return n > 0;
}
```

---

# PART 6 — ARRAYS & LISTS

## 6.1 Arrays
```csharp
int[] values = { 1, 3, 5, 7 };
```

```csharp
for (int i = 0; i < values.Length; i++)
{
    Debug.Log(values[i]);
}
```

---

## 6.2 Lists
```csharp
using System.Collections.Generic;

List<int> numbers = new List<int>();
numbers.Add(10);
numbers.Add(20);
numbers.Add(30);
numbers.Remove(20);
```

---

# PART 7 — UNITY SCRIPT PATTERNS (PRACTICAL)

## 7.1 Script Structure & MonoBehaviour
```csharp
using UnityEngine;

public class Sample : MonoBehaviour
{
    void Start() { }
    void Update() { }
}
```

`MonoBehaviour` allows a script to:
- attach to a GameObject
- appear in the Inspector
- receive Unity events like `Start()` and `Update()`

Without it, a class is just normal C#.

---

## 7.2 Transform Manipulation
```csharp
transform.position += Vector3.up * Time.deltaTime;
```

```csharp
transform.Rotate(Vector3.right, 45f * Time.deltaTime);
```

`transform` represents a GameObject’s:
- position
- rotation
- scale

You move objects by modifying their **Transform**.

---

## 7.3 Input Reading
```csharp
if (Input.GetKeyDown(KeyCode.Space))
{
    Debug.Log("Space pressed");
}
```

Used for:
- jump
- shoot
- confirm actions

---

## 7.4 GetComponent Pattern
```csharp
Rigidbody rb;

void Start()
{
    rb = GetComponent<Rigidbody>();
}
```

Gets a component from the **same GameObject** and stores it safely.

---

## 7.5 Instantiate & Destroy
```csharp
GameObject obj = Instantiate(prefab);
Destroy(obj, 3f);
```

Used for spawning and timed cleanup.

---

## 7.6 Coroutines
```csharp
IEnumerator WaitThenPrint()
{
    yield return new WaitForSeconds(1f);
    Debug.Log("One second passed");
}
```

Coroutines allow delayed and timed actions without blocking gameplay.

---

# HOW TO PRACTICE THIS COMPANION
- Pick a section
- Type every example
- Modify values
- Observe results
- Repeat

---

## Final Words
Confidence comes from **volume + repetition**.

This companion is intentionally long.
Return to it whenever you feel stuck.

— **MIDNIGHT LARK**

