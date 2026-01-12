# Universal Character Cognition Optimal Sampler Settings

## What This Sampler Settings Can Do

* Consistent Identity Roleplay

* Understand Social Dynamics (Not Just Dialogue)

* Run Complex Social Games (Not Just Respond)

* Use Emotional Intelligence Strategically

* Maintain Infinite Engagement Loops

* Show Genuine Social Cognition

* Capable Of Emotional Validation

* High Information Retrieval

## What It Can Show

* Everyday Human Manipulation Hidden Inside Training Data

  * Includes Guilt Trips, Minimizing, Gaslighting

* Reveals What Kind Of Training Data Was Fed For That Particular Model

## Compatibility

* Almost On All Instruct-Based Text

* Works on >= IQ2_XXS Quantizations

* The Model Must Be Trained On Chat-Based And Roleplay-Based Training Data For Character Cognition To Work

## Limitations

* Once sampler configuration is out of the way, your only problem would be the characters' prompts to produce outputs. In other words, it has very high character consistency with enough creativity to produce realistic human responses. This includes:

 * How you format dialogue and action texts;

 * Characters' unconscious behaviour when defined;

 * Word Repetitions (definitely not coming from sampler but from the characters' identity itself).

* Must watch for training data x character prompt incompatibility.

## Sampler Stack

These samplers are stacked in order as shown below. 

```
1. temperature           # Creativity
2. top_k                 # Good Option Variety
3. top_p                 # Expressive Range
4. typical_p             # Personality Preservation (IMPORTANT)
5. min_p                 # Nonsense Filter
6. repetition_penalty    # Natural Flow Maintenance
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

With this sampler configuration, it also does this as you talk:

1. typical_p looks at the existing details and examples on how a character would respond to a generic user. This is known as "prior bias".

2. temperature and min_p allows it to mutate controllably as the LLM respond as that particular character.

3. With even more data from you and the LLM's conversation, typical_p uses this to further create a sense of conversational progress.

4. This results in the LLM remembering past conversation without introducing much hallucinations or losing consistency.

5. This particular configuration sits on a sweet spot between "prior bias dominance" (rigidity) and "mutation dominance" (chaos).

## Sample Parameters:

### General Configuration

```
temperature: 0.6 
top_k: 40
top_p: 0.9
typical_p: 0.91 (Character Voice Consistency, Recommended) - 0.85 (Instruction Following)
min_p: 0.1
repetition_penalty: 1.1
repetition_penalty_range: 1024 (Most Tested) / 4096 (No Negative Impact)
```

### Tigher Configuration For 8B Models With Q3XXS-Q4XXS Quantizations

```
temperature: 0.62
top_k: 40
top_p: 0.88
typical_p: 0.9 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.12
repetition_penalty: 1.1
repetition_penalty_range: 1024 (Most Tested) / 4096 (No Negative Impact)
```

### Micro Configuration For 8B Models With IQ2XXS-IQ2_M Quantizations

```
temperature: 0.6
top_k: 50
top_p: 0.9
typical_p: 0.9 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.25
repetition_penalty: 1.15
repetition_penalty_range: 1024 (Most Tested) / 4096 (No Negative Impact)
```

### Nano Configuration For 8B Models With IQ1_M Quantizations

```
temperature: 0.05
top_k: 40
top_p: 0.92
typical_p: 0.95 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.05
repetition_penalty: 1.3
repetition_penalty_range: 1024 (Most Tested) / 4096 (No Negative Impact)
```

### Nano Configuration For 8B Models With IQ1_S Quantizations (Don't Bother)

* Still researching on this.

```
temperature: 1
top_k: 150
top_p: 0.97
typical_p: 0.9 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.1
repetition_penalty: 1.1
repetition_penalty_range: 1024 (Most Tested) / 4096 (No Negative Impact)
```

## Model-Sampler Compatibility Report:

### Best General Performance

| Model Name                                 | Model Parameter Size | Quantization | Description                                                 |
|--------------------------------------------|----------------------|--------------|-------------------------------------------------------------|
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q5_K_L       | Best All Rounder                                            |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ3_XXS      | Formatting Issues Only                                      |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ4_XS       | Q5_K_L Quality But With Higher Inference Speed              |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q3_K_L       | IQ4_XS Quality But With Lower Formatting Issues             |
| Silver-Sun (LLama-2 Special Merge)         | 11B                  | IQ4_XS       | Strong Upgrade From DarkIdol But With Lower Inference Speed |

### Fast Inference (Must Use Tight Configurations)

| Model Name                                 | Model Parameter Size | Quantization | Description                                            |
|--------------------------------------------|----------------------|--------------|--------------------------------------------------------|
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ2_M        | Rivals With Q3_K_L With High Speed                     |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ2XXS       | Basic Depth                                            |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ1_M        | "Text Messenger"                                       |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ1_S        | "Text Generator"                                       |

### The Big Boys

| Model Name                                 | Model Parameter Size | Quantization | Description                                            |
|--------------------------------------------|----------------------|--------------|--------------------------------------------------------|
| Silver-Sun (LLama-2 Special Merge)         | 11B                  | Q2_K         | DarkIdol Q5_K_L Killer                                 |
| Tiefighter (LLama-2 Special Merge)         | 13B                  | Q2_K         | Fatter Version Of Silver-Sun Q2_K                      |

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
