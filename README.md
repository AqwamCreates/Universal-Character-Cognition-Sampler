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

1. top_n_sigma
2. temperature
3. top_k
4. top_p
5. typical_p
6. min_p
7. repetition_penalty

```

The reason it works is because:

1. The LLM first listen to input which generates associated words and ideas relating to the input. (top_n_sigma + temperature + top_p + top_k)

2. The LLM then applies the personality aspect of the character and makes sure it is consistent with the character's identity. (typical_p + min_p)

3. It then fixes English mistakes and do a bit of polishing (repetition_penalty).

4. The output becomes character dialogues that feels "snappy" and responsive to users' reactions.

## Sample Parameters:

```
top_n_sigma: 0
temperature: 0.6
top_k: 40
top_p: 0.9
typical_p: 0.9
min_p: 0.1
repetition_penalty: 1.1
repetition_penalty_range: 1024
```

## Model-Sampler Compatibility Report:

All are Instruct models.

| Model Name                                 | Model Parameter Size | Quantization | Description                                                 |
|--------------------------------------------|----------------------|--------------|-------------------------------------------------------------|
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q5_K_L       | Best All Rounder                                            |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | IQ3_XXS      | Formatting Issues Only                                      |
| DarkIdol Llama-3.1 Instruct 1.2 Uncensored | 8B                   | Q3_K_L       | Q5_K_L Quality But With Higher Inference Speed              |
| Silver-Sun (LLama-2 Special Merge)         | 11B                  | IQ4_XS       | Strong Upgrade From DarkIdol But With Lower Inference Speed |
