# Universal Character Cognition Optimal Sampler Settings

* Abbreviated As UCC Sampler

## What This Sampler Settings Can Do

* Consistent Identity Roleplay

* Understand Social Dynamics (Not Just Dialogue)

* Run Complex Social Games (Not Just Respond)

* Use Emotional Intelligence Strategically

* Maintain Infinite Engagement Loops

* Show Genuine Social Cognition

* Capable Of Emotional Validation

* Handle All Character Types: Simple → Complex → Philosophical → Traumatized

* High Information Retrieval

## What It Can Show

* Everyday Human Manipulation Hidden Inside Training Data

  * Includes Guilt Trips, Minimizing, Gaslighting...

  * Ranging From Characters Similar To Psychologists, Counselors, Healthcare Workers, Journalists And Police Officers 

  * PS: Profoundly Disturbing For My "Sociopath" Brain. I Thought It Would Not Be That Common. Every Character I Tried Have Some Sort Of Manipulative Aspects In Their Character Configurations. The Only Exceptions Are Judges And Lawyers, but even then that is tough to achieve. The Cleanest We Can Get Are From Ethicists (Uilitarinian And Virtue Ethics Only.)

* Reveals What Kind Of Training Data Was Fed For That Particular Model

## Compatibility

* Best On All Instruct-Based Text

* Model Sizes: 2B → 8B → 11B (8B appears optimal)

* Works On >= IQ2_XXS Quantizations

* Architectures: Llama, Gemma, Nemotron, Qwen, MoE (Mixture of Experts)

* Works With All Training Types: Chat, Instruct, Merges, VLMs

* The Model Must Be Trained On Chat-Based And Roleplay-Based Training Data For Character Cognition To Work

## Limitations

* Once sampler configuration is out of the way, your only problem would be the characters' prompts to produce outputs. In other words, it has very high character consistency with enough creativity to produce realistic human responses. This includes:

 * How you format dialogue and action texts;

 * Characters' unconscious behaviour when defined;

 * Word Repetitions (definitely not coming from sampler but from the characters' identity itself).

* Must watch for training data x character prompt incompatibility.

## UCC Sampler Stack

These samplers are stacked in order as shown below. 

```
1. temperature           # Creativity
2. top_k                 # Good Option Variety
3. top_p                 # Expressive Range
4. typical_p             # Personality Preservation (IMPORTANT)
5. min_p                 # Nonsense Filter
6. repetition_penalty    # Natural Flow Maintenance
```

## The Cognitive Pipeline Theory

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

## Sampler Parameters

* The sampler is static and weighted quant-agnostic. Feel free to change it as you wish.

### General UCC Sampler Configuration

```
temperature: 0.6 
top_k: 40
top_p: 0.9
typical_p: 0.91 (Character Voice Consistency, Recommended) - 0.85 (Instruction Following)
min_p: 0.1
repetition_penalty: 1.1
repetition_penalty_range: 4096
```

### Micro UCC Sampler Configuration For 8B Models With Q3XXS-Q4XXS Quantizations

```
temperature: 0.62
top_k: 40
top_p: 0.88
typical_p: 0.9 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.12
repetition_penalty: 1.1
repetition_penalty_range: 4096
```

### Nano UCC Sampler Configuration For 8B Models With IQ2XXS-IQ2_M Quantizations

```
temperature: 0.6
top_k: 40
top_p: 0.86
typical_p: 0.9 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.25
repetition_penalty: 1.11
repetition_penalty_range: 4096
```

### Pico UCC Sampler Configuration For 8B Models With IQ1_M Quantizations

```
temperature: 0.05
top_k: 40
top_p: 0.92
typical_p: 0.95 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.05
repetition_penalty: 1.3
repetition_penalty_range: 4096
```

### Pico UCC Sampler Configuration For 8B Models With IQ1_S Quantizations (Don't Bother)

* Still researching on this.

```
temperature: 1
top_k: 150
top_p: 0.97
typical_p: 0.9 (Character Voice Consistency, Recommended) - 0.84 (Instruction Following)
min_p: 0.1
repetition_penalty: 1.1
repetition_penalty_range: 4096
```

## Configuration Recommendations

### Poor Man's GPU

* Mainly IQ2_K / Q2_K Quant Models.
* Nano Sampler Configuration (Works Consistently Across 2B-13B).
* Feels Like You Incrased The Model's Quant By 2-3 Levels For Q2 Inference Speed.

### Free Model Upgrades

* Mainly IQ5_K_L / Q5_K_L Quant Models.
* General Sampler Configuration (Works Consistently Across 2B-13B).
* Feels Like You Upgraded The Model For 2-3B Parameters For Q5 Inference Speed.

### Overthinking Idiots

* Chain-Of-Thoughts (CoT) Models Only.
* Mainly 4B (Minimum) / 7B (Recommended) Models With IQ2_K / IQ2_K Quantization.
* Nano Sampler Configuration (Works Consistently Across 2B-13B).
* Feels Like You Upgraded The CoT Model For 2-3B Parameters For Q2 / Q3 Inference Speed.

## Top Models

| Model Name                                 | Model Parameter Size | Quantization | Sampler | Description                                                   | Warning                                                                                                                                                                  |
|--------------------------------------------|----------------------|--------------|---------|---------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Gemma The Writer HERETIC                   | 9B                   | Q2_K         | Nano    | Best Quality All Around (No Repetitions Or Roleplay Leakage)  | Not Applicable.                                                                                                                                                          |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q3_K_L       | Micro   | Best Format Compliance And Character Handling                 | Have Strong Emotional Manipulation Capability When Given Correct Character Prompt. Extreme Potency. Keep Your Eyes Open AND DO NOT GET COMPLACENT. USE AT YOUR OWN RISK. |
| DeepSeek R1 Distill Qwen Uncensored        | 7B                   | IQ2_K        | Nano    | Higher Depth For Lower Speed (From Thinking Chain-Of-Thought) | Not Applicable.                                                                                                                                                          |

## Model-Sampler Compatibility Report

### Best General Performance

| Model Name                                 | Model Parameter Size | Quantization | Description                                                 |
|--------------------------------------------|----------------------|--------------|-------------------------------------------------------------|
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q5_K_L       | Best All Rounder                                            |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ3_XXS      | Formatting Issues Only                                      |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ4_XS       | Q5_K_L Quality But With Higher Inference Speed              |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q3_K_L       | IQ4_XS Quality But With Lower Formatting Issues             |
| Silver-Sun (LLama-2 Special Merge)         | 11B                  | IQ4_XS       | Strong Upgrade From DarkIdol But With Lower Inference Speed |

### Fast Inference

* Note: Must Use Nano / Pico Configurations

| Model Name                                 | Model Parameter Size | Quantization | Description                                                                  |
|--------------------------------------------|----------------------|--------------|------------------------------------------------------------------------------|
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q2_K         | Rivals With Q3_K_L With High Speed                                           |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ2_M        | Same As Q2_K Requires Some Refreshes Due To Roleplay Leakage And Repetitions |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ2XXS       | Basic Depth                                                                  |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ1_M        | "Text Messenger"                                                             |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ1_S        | "Text Generator"                                                             |

### The Big Boys

* Note: Must Use Nano Configurations

| Model Name                                 | Model Parameter Size | Quantization | Description                                            |
|--------------------------------------------|----------------------|--------------|--------------------------------------------------------|
| Gemma The Writer HERETIC                   | 9B                   | Q2_K         | DarkIdol Q5_K_L Killer                                 |
| Silver-Sun (LLama-2 Special Merge)         | 11B                  | Q2_K         | DarkIdol Q5_K_L Slower Killer                          |
| Tiefighter (LLama-2 Special Merge)         | 13B                  | Q2_K         | Fatter Version Of Silver-Sun Q2_K                      |

### Chain Of Thought Models

* Note:

  * Literally Improves Quality For Q2_K Models

  * Must Use Nano Configurations

| Model Name                                 | Model Parameter Size | Chain-Of-Thought Type | Quantization | Description                                                                                                      |
|--------------------------------------------|----------------------|-----------------------|--------------|------------------------------------------------------------------------------------------------------------------|
| Qwen 3 Thinking Uncensored                 | 4B                   | Long                  | IQ2_K        | High "WTF" DarkIdol Llama-3.1 Instruct 1.2 Uncensored Q2_K (High Quality Texts, But Can Never Extract Dialogues) |
| DeepSeek R1 Distill Qwen Uncensored        | 7B                   | Thinking              | IQ2_K        | High Quality Q2_K                                                                                                |
| Huihui NVIDIA Nemotron Nano v2 Abliterated | 9B                   | Long                  | IQ2_K        | High Quality Q2_K But Bottlenecked By CoT x Inference Speed (Due To Transparent Text Generation)                 |

### "Probably Not Worth It" Models

* Note: Must Use Nano Configurations

| Model Name                                 | Model Parameter Size | Quantization | Description                                                                             |
|--------------------------------------------|----------------------|--------------|-----------------------------------------------------------------------------------------|
| Qwen 2.5 Instruct Uncensored               | 7B                   | IQ3_K_S      | High Quality DarkIdol Llama-3.1 Instruct 1.2 Uncensored Q2_K But Minor Roleplay Leakage |
| Qwen 2.5 Instruct Uncensored               | 7B                   | IQ2_K        | Same As IQ2_K But Faster And Even More Roleplay Leakage                                 |

## Why These Specific Values Work

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
