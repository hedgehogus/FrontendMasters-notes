## Structured output
- Get consistent formats every time
- Tell the model exactly how you want information
- Use examples, templates, or schemas to enforce format
- Test cases, documentation, data ectraction, code generation
```
Extract the meeting details from this email.

Format like this:
Date: [date]
Time: [time]
Location: [location]
Topic: [topic]

Email: "Let's meet tomorrow at 2 PM in Conference Room B to discuss the Q4 budget."
```
Structured output ensures consistent fromats every time, which is critical when connecting an LLM to other parts of an application. Without structured output, you might receive a paragraph, sentence, array or JSON object inconsistently, making it impossible to reliably process the data in subsequent application steps. It allows you to know exactly what format to expect and how to handle it/
```
Create a metadata tracking system for a prompt journal web application that is attached to our prompts in our prompt library.

FUNCTION SPECIFICATIONS:
1. trackModel(modelName: string, content: string): MetadataObject
   - Accept any non-empty string for modelName
   - Auto-generate createdAt timestamp
   - Estimate tokens from content
   
2. updateTimestamps(metadata: MetadataObject): MetadataObject
   - Update the updatedAt field
   - Validate updatedAt >= createdAt
   
3. estimateTokens(text: string, isCode: boolean): TokenEstimate
   - Base calculation: min = 0.75 * word_count, max = 0.25 * character_count  
   - If isCode=true, multiply both by 1.3
   - Confidence: 'high' if <1000 tokens, 'medium' if 1000-5000, 'low' if >5000

VALIDATION RULES:
- All dates must be valid ISO 8601 strings (YYYY-MM-DDTHH:mm:ss.sssZ)
- Model name must be non-empty string, max 100 characters
- Throw errors for invalid inputs with descriptive messages

OUTPUT SCHEMA:
{
  model: string,
  createdAt: string (ISO 8601),
  updatedAt: string (ISO 8601),
  tokenEstimate: {
    min: number,
    max: number,
    confidence: 'high' | 'medium' | 'low'
  }
}

VISUAL DISPLAY:
Create an HTML/CSS component that adds and displays metadata in the prompt card:
- Model name
- Timestamps in human-readable format
- Token estimate with color-coded confidence (green/yellow/red)
- Sort by createdAt descending

CONSTRAINTS:
- Pure JavaScript only (no external libraries)
- Must work in browser environment
- Include try/catch error handling
```

## Chain of thought (COT) prompting
- ask the model to show it's reasoning step-by-step
- Breaks complex problems into intermediate steps
- CoT (Zero-shot): "Let's think step by step"
- Few-shot: Include reasoning steps in your examples
```
Can penguins fly?
Think through this step by step.
```
