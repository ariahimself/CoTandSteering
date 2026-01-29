# Chain-of-Thought Steering

This project explores **steering and controlling chain-of-thought (CoT) behavior** in large language models, with a focus on **short vs. long chains of thought**.

## Overview

A wide range of methods have been proposed to influence how language models reason.  
In this project, we investigate how easily **chain-of-thought length can be controlled through representation steering**.

The core idea is to identify internal model representations that exhibit **linear separability between short and long reasoning traces**, and then use these representations to steer the model’s behavior.

## Method

The project follows three main steps:

### 1. Few-Shot Prompting
We construct few-shot examples designed to encourage either:
- **Short chain-of-thought**
- **Long chain-of-thought**

These examples serve as labeled signals for different reasoning styles.

### 2. Representation Analysis
- Forward hooks are used to capture internal activations.
- Linear classifiers are trained to distinguish between short and long chain-of-thought representations.
- Layers or components with strong linear discrimination are identified.

### 3. Steering
- Steering vectors are derived from discriminative representations.
- These vectors are injected back into the model during inference.
- The effect on reasoning length and structure is evaluated.

## Goal

The goal of this project is simple:

> Determine whether the length and depth of chain-of-thought reasoning can be reliably controlled by steering internal model representations.

This repository is intended as an experimental framework for studying **interpretability, controllability, and reasoning behavior** in large language models.

## Notes

- This project is exploratory and research-oriented.
- It is not intended to enforce or expose hidden chain-of-thought, but to study **internal reasoning dynamics** through representation-level interventions.

## Future Work

Potential extensions include:
- Multi-class reasoning styles
- Token-level or attention-based steering
- Evaluation across different model families
- Stability and robustness analysis of steering directions

---

