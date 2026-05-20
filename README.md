1. Project Overview
This repository demonstrates the domain-specific fine-tuning of Large Language Models to act as expert assistants in Electrical Engineering. By using a base foundation model, we adapted its broad linguistic capabilities to handle technical vocabulary and complex engineering reasoning.
2. Technical Stack & Optimization
We utilized several cutting-edge techniques to make training feasible on a single Google Colab T4 GPU (15GB VRAM):

    Unsloth: Used to accelerate training speeds and reduce VRAM usage by 50% to 80%.
    QLoRA (4-bit Quantization): Compressed the model weights to 4-bit precision, allowing 7B+ parameter models to fit into limited memory without losing significant accuracy.
    LoRA (Low-Rank Adaptation): Instead of full fine-tuning, we trained lightweight "adapters" (low-rank matrices), drastically reducing the number of trainable parameters and preventing catastrophic forgetting.

3. Dataset & Training

    Dataset: STEM-AI-mtl/Electrical-engineering from Hugging Face.
    Split: 80% Training / 20% Validation.
    Format: Instruction-tuning using custom prompt templates to ensure the model follows engineering commands accurately.

4. Results

    Quantitative: Training loss decreased from ~2.5 to ~0.6 over 60 steps, indicating successful mathematical convergence.
    Qualitative: The fine-tuned model transitioned from generating unstructured "next-word" gibberish to providing highly structured, accurate technical explanations of electrical components and circuit theory
