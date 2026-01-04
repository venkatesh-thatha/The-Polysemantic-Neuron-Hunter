#  The Polysemantic Neuron Hunter
> *Deconstructing GPT-2 to find the "ghosts" in the machine.*

## What is this?
We often treat Large Language Models (LLMs) like "Black Boxes"—we feed them text, and they spit out answers. But what happens inside?

This project is a **Mechanistic Interpretability** experiment. I didn't just want to run a model; I wanted to perform brain surgery on it. My goal was to hunt for **Polysemantic Neurons**—single neurons that secretly hold multiple, unrelated meanings.

##  The Core Concepts
Before hunting, we must understand the prey:

### 1. Monosemantic Neurons (The Specialist)
A neuron that cares about **one specific thing**.
* *Example:* A neuron that only fires when it sees the word "dog" or "puppy."
* *My Finding:* In my analysis, I found a "Syntax Neuron" (Neuron 1846) that only cared about the word **"by"**. It was a grammar specialist.

### 2. Polysemantic Neurons (The Generalist)
A neuron that activates for **two completely different things**.
* *The Theory:* Because models have limited space (neurons) but infinite concepts to learn, they force neurons to multitask.
* *Example:* A single neuron firing for **"The GITA"** AND **"Linux Code"**. This is called **Superposition**.

##  How I Did It
I avoided high-level abstractions and went straight to the tensors.

* **The Subject:** GPT-2 Small (12 Layers, 768 Embedding Dim).
* **The Tool:** `TransformerLens` (for hooking into internal activations) and `PyTorch`.
* **The Process:**
    1.  **Feed Forward:** Input mixed text (Technical Jargon + Bhagavad Gita).
    2.  **Activation Caching:** Intercepted the data at `Layer 0`.
    3.  **The Hunt:** Wrote a custom algorithm to scan 3,072 neurons and find the "Global Champion"—the one that screamed the loudest.
    4.  **Verification:** Visualized the neuron's activation history using `Plotly` to check if it spiked for conflicting concepts.

##  Research Insights & Learnings
* **The "Sequence Starter" Trap:** My first attempt failed because I found a neuron that only fired at the start of the sentence (`<|endoftext|>`). I learned that models use specific neurons just to "wake up" or reset attention.
* **The Difficulty of Interpretation:** Most neurons are not cool concepts like "Love" or "Hate." They are boring functional workers handling syntax (commas, prepositions). Finding a true semantic neuron is like finding a needle in a haystack.
* **Matrix Math is Reality:** The concept of "meaning" in AI is literally just high-dimensional geometry. If two vectors point the same way, the meanings are the same.

##  Why This Matters (My Take)
Building RAG apps is fun, but understanding the *engine* is crucial. This project was my stepping stone from being an "AI User" to an "AI Researcher." It taught me that to trust AI, we need to be able to read its mind, mathematically.

##  Tech Stack
* **Python**
* **PyTorch (Tensors & Autograd)**
* **TransformerLens**
* **Plotly (Visualization)**
