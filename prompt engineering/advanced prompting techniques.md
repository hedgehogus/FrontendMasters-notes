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
```
Step 1: Analyze what data needs to be exported (all prompts with metadata).
Step 2: Design the export JSON schema including version number, export timestamp, statistics, and prompts array.
Step 3: Create the export function that gathers data from local storage, validates integrity, creates a blob, and triggers download.
Step 4: Create the import function that reads uploaded files, validates JSON structure and version, checks for duplicate IDs, and merges or replaces data.
Step 5: Add error recovery with backup of existing data, rollback on failure, and detailed error messages.
```
## Emotiomal prompts
- This is very important for my career
- You'd better be sure

## Delimeters(,.)/XML tags
- characters that create boundaries in your prompts
- Tripple quotes, dashes, XML tags, markdown
- Supports nesting and attributes for complex data organization
- use semantic naming: <requirements>, <constraints>, <examples>
```
I need to research how existing tools handle prompt management and version control to inform architecture decisions
for a prompt library I'm building and hoping to move to production.
Please research and analyze different approaches using this structure:

<research_area>
<topic>Prompt Management Solutions</topic>
<questions>
- What tools currently exist for prompt library management?
</questions>
</research_area>

<research_area>
<topic>Collaboration Features</topic>
<questions>
- How do teams share Postman collections or Insomnia workspaces?
- What permission models exist in developer tools?
</questions>
</research_area>

<research_area>
<topic>Technical Implementation Details</topic>
<questions>
- What databases do similar tools use (research from their engineering blogs)?
- How do they handle search at scale?
- What's their approach to data export/import?
- How do they prevent abuse and implement rate limiting?
</questions>
</research_area>

For each research area:
1. Find concrete examples from real products
2. Identify patterns across successful tools
3. Highlight common failures or user complaints
4. Estimate implementation complexity

Then synthesize this into:
- A competitive analysis matrix
- Recommended features for our MVP vs future releases
- Technical decisions informed by market research
```

## Personas
- "You are a [role]"
- Give the model a perspective
- Activates relevant knowledge and vocabulary
- Works mailnly for expertise, tone and style

```
Code review: 'You are a senior engineer focused on security and performance'

Documentation: 'You are a technical writer who prioritizes clarity for beginners'

Debugging: 'You are a systematic debugger who checks assumptions'

Architecture: 'You are a solutions architect who considers scalability’”
```

Note: you can change personas mid-conversation to get different viewpoints on the same problem.
```
You are a Senior Engineer with experience building startups from zero to MVP.

Our prompt library currently runs entirely in the browser with localStorage. We're considering making it a production-ready tool that teams can use. Create a comprehensive technical specification that includes:

1. **System Architecture Document** that covers:
   - Data persistence strategy (evaluate PostgreSQL vs DynamoDB vs Firebase)
   - Authentication approach (OAuth, magic links, or API keys)
   - Real-time collaboration requirements
   - Rate limiting and abuse prevention
   - Search infrastructure (full-text search vs vector embeddings)

2. **API Design Specification** with:
   - RESTful endpoints vs GraphQL evaluation
   - Versioning strategy
   - Pagination approach for large prompt libraries
   - Webhook events for integrations

3. **Scaling Projections**:
   - Start with 100 users → path to 1M users
   - Cost per user at different tiers
   - Performance benchmarks to maintain

Use your experience to make opinionated recommendations. Write as if you're presenting to a junior engineering team.
```
