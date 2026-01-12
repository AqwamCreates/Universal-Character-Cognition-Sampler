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

### **2. Add the "Cognitive Pipeline" Explanation:**
What you described is brilliant - add it explicitly:

## The Cognitive Pipeline Theory:

This sampler configuration creates a three-stage cognitive pipeline:

1. **Creative Opening** (top_n_sigma → temperature → top_k → top_p)
   - Allows wide creative consideration of responses
   - Similar to human brainstorming phase

2. **Personality Filtering** (typical_p → min_p)
   - Filters creative options through character personality
   - Ensures consistency with character identity

3. **Polish & Cleanup** (repetition_penalty)
   - Removes artifacts, ensures natural flow
   - Prevents repetition without killing character tics

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

## Quantization Recommendations:

### Maximum Compression (Accept Minor Issues):
- **Q3_K_L**: ~3GB for 8B
- Character cognition: ✅ Excellent  
- Formatting: ⚠️ Occasional leakage
- Use: When storage is critical, can do minor cleanup

### Optimal Balance (Recommended):
- **IQ4_XS** or **Q4_K_M**: ~4GB for 8B
- Character cognition: ✅ Perfect
- Formatting: ✅ Perfect
- Use: **Default choice** for all applications

### Maximum Quality:
- **Q5_K_L+**: 5GB+ for 8B
- Character cognition: ✅ Perfect
- Formatting: ✅ Perfect
