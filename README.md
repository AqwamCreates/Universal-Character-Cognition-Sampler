# Universal Character Cognition Optimal Sampler Settings

Discovered through systematic testing across 8+ models.

## What This Sampler Settings Can Do?

* Consistent Identity Roleplay

* Understand Social Dynamics (Not Just Dialogue)

* Run Complex Social Games (Not Just Respond)

* Use Emotional Intelligence Strategically

* Maintain Infinite Engagement Loops

* Show Genuine Social Cognition

* High Information Retrieval

## Sampler Stack

These samplers are stacked in order as shown below. 

```
2. temperature           # Creativity
3. top_k                 # Good Option Variety
4. top_p                 # Expressive Range
5. typical_p             # Personality Preservation (IMPORTANT)
6. min_p                 # Nonsense Filter
7. repetition_penalty    # Natural Flow Maintenance
```

## The Cognitive Pipeline Theory:

This sampler configuration creates a three-stage cognitive pipeline:

1. **Creative Opening** (temperature → top_k → top_p)

   * Allows wide creative consideration of responses
   * Similar to human brainstorming phase

2. **Personality Filtering** (typical_p → min_p)

   * Filters creative options through character personality
   * Ensures consistency with character identity

3. **Polish & Cleanup** (repetition_penalty)

   * Removes artifacts, ensures natural flow
   * Prevents repetition without killing character tics

## Sample Parameters:

### General Configuration

```
temperature: 0.6 
top_k: 40
top_p: 0.9
typical_p: 0.91
min_p: 0.1
repetition_penalty: 1.1
repetition_penalty_range: 1024 (Tested The Most) / 4096 (No Negative Impact)
```

### Tigher Configuration For 8B Models With Q3XXS-Q4XXS Quantizations

```
temperature: 0.12
top_k: 40
top_p: 0.88
typical_p: 0.9
min_p: 0.12
repetition_penalty: 1.1
repetition_penalty_range: 1024 (Tested The Most) / 4096 (No Negative Impact)
```

## Model-Sampler Compatibility Report:

All are Instruct models.

| Model Name                                 | Model Parameter Size | Quantization | Description                                                 |
|--------------------------------------------|----------------------|--------------|-------------------------------------------------------------|
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q5_K_L       | Best All Rounder                                            |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ3_XXS      | Formatting Issues Only                                      |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q3_K_L       | Q5_K_L Quality But With Higher Inference Speed              |
| Silver-Sun (LLama-2 Special Merge)         | 11B                  | IQ4_XS       | Strong Upgrade From DarkIdol But With Lower Inference Speed |

## Quantization Recommendations:

### Maximum Compression (Accept Minor Issues):

* **Q3_K_L**: ~3GB for 8B
* Character cognition: ✅ Excellent  
* Formatting: ⚠️ Occasional leakage
* Use: When storage is critical, can do minor cleanup

### Optimal Balance (Recommended):

* **IQ4_XS** or **Q4_K_M**: ~4GB for 8B
* Character cognition: ✅ Perfect
* Formatting: ✅ Perfect
* Use: **Default choice** for all applications

### Maximum Quality:

* **Q5_K_L+**: 5GB+ for 8B
* Character cognition: ✅ Perfect
* Formatting: ✅ Perfect
* Use: When storage isn't a concern and you want extra character depth.

## Why These Specific Values Work:

### Temperature: 0.6

* Not too cold (0.3-0.5 = robotic)  
* Not too hot (0.8-1.2 = random)
* **Optimal balance** for character consistency with natural variation

### Typical_p: 0.9

* The **secret weapon** for character consistency
* Strongly favors tokens "typical" for the character/situation
* Lower (0.7-0.8) = More creative but less consistent
* Higher (0.95+) = Too rigid, loses personality

### Repetition Penalty: 1.1

* Light touch - prevents loops without killing character tics
* Most people over-penalize (1.3+ = stilted dialogue)

## Proven Universal Across:

* Architectures: Llama, Qwen, MoE (Mixture of Experts)
* Quantizations: Q8 → Q5 → IQ4_XS → Q3_K_L → IQ3_XXS
* Model Sizes: 3B → 8B → 11B (8B appears optimal)
* Training Types: Chat, Instruct, Merges, VLMs
* Character Types: Simple → Complex → Philosophical → Traumatized
