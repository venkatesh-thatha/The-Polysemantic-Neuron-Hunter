##  Research Insights & Results

By scanning all 3,072 neurons across 12 layers of GPT-2 Small, I mapped the model's internal "thought process."

### 1. The "U-Shaped" Activation Pattern 
The model's "brain activity" (activation strength) follows a distinct U-shape:
* **Start (L0-L2):** **Loud.** High activations for raw token recognition.
* **Middle (L3-L7):** **Quiet.** Low activations indicating distributed reasoning and dependency tracking.
* **End (L8-L11):** **Loud.** Massive energy spikes as the model finalizes its decision.

### 2. The Hierarchy of Abstraction 
I identified three distinct classes of neurons based on their depth:

| Layers | Role | Champion Neuron | Behavior |
| :--- | :--- | :--- | :--- |
| **0-2** | **The Librarians** | #1846 | **Syntax & Grammar.** Obsessed with specific rules (e.g., firing only on "by"). |
| **3-7** | **The Engineers** | #1395 | **Structure & Flow.** Tracks logic markers like periods (`.`) and conjunctions (`but`). |
| **8-11** | **The Philosophers** | #1253 | **Semantic Meaning.** Abstracts concepts like "Goal-Oriented Action" from both code and scripture. |

### 3. Conclusion
The "spikes" seen in later layers (e.g., Layer 8 firing for both "Gradient Descent" and "Karma Yoga") are not confusion. They represent **Semantic Abstraction**, where the model groups disparate topics under a single high-level concept.
