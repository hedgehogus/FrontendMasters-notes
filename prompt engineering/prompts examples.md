## Standart prompt
- Your direct question or instruction to the AI
- The simplest form of prompting - just ask
- The foundation that everything else builds on
- Quality of question directly related to the quality of the answer
        
*What color is the sky?*
```
Create a prompt library application that lets users save and delete prompts.

Users should be able to:
- Enter a title and content for their prompt
- Save it to localStorage
- See all their saved prompts displayed on the page
- Delete prompts they no longer need

Make it look clean and professional with HTML, CSS, and JavaScript.
```
## Zero Shot
- Direct task request without any examples
- Model relies entirely on pre-training knowledge
- Works well for common tasks
- Quality varies based on task complexity and specificity
```
Classify the customer rating into neutral, negative or positive.

Text: The product was okay. It worked, but wasn't the easiest to understand how to use.
Sentiment:
```

   ```
Create a prompt library application in HTML, CSS, and JavaScript.

Create an HTML page with a form containing fields for the prompt title and content

Add a save prompt button that saves to localStorage

Display saved prompts in cards

Each prompt card should show the title, a content preview of a few words, and a delete button

Deleting should remove the prompt from localStorage and update the display
```

## One Shot
- provide exactly **one** example with your request
- model learns the pattern, format and style from the example
- useful for establishing format
- show don't tell

Style it with CSS to look clean and modern with a developer theme

Include all HTML structure, CSS styling, and JavaScript functionality in their own files, but that can be run immediately and includes no other features.
```
Write an engaging introduction for a blog post about remote work productivity.

Example:
Topic: Benefits of morning exercise
Introduction: "Picture this: It's 6 AM, your alarm goes off, and instead of hitting snooze, you lace up your sneakers. Sound impossible? Here's the thing—those who exercise before breakfast report 23% higher energy levels throughout their workday. But the real secret isn't just the exercise itself; it's what happens to your brain chemistry in those precious morning hours."

Now write an introduction for: Remote work productivity tips
```
```
You are helping develop a prompt library application. Here's an example of how to analyze and implement a new feature:

**EXAMPLE:** Feature Request: "Add a favorites/bookmarking system"

Implementation Plan:

1. **User Story**: As a user, I want to mark prompts as favorites so I can quickly access my most-used prompts without scrolling through the entire library.
2. **Technical Requirements**:
    - Add a heart/bookmark icon to each prompt card
    - Store favorite status in localStorage or database
    - Create a filter to show only favorited prompts
    - Visual indicator when a prompt is favorited (filled vs outlined icon)
3. **Code Structure**:

javascript
// Data model update
prompt = {
  id: 'prompt-123',
  title: 'Marketing Email Generator',
  content: '...',
  isFavorite: false,  // New field
  createdAt: '2024-01-15',
  rating: 4.5
}

// Toggle favorite function
function toggleFavorite(promptId) {
  const prompt = prompts.find(p => p.id === promptId);
  prompt.isFavorite = !prompt.isFavorite;
  saveToStorage(prompts);
  updateUI();
}

4. **UI/UX Considerations**:
    - Place favorite icon in consistent location (top-right of card)
    - Use intuitive icons (heart or star)
    - Provide visual feedback on click (animation/color change)
    - Add "Favorites" filter tab in navigation

---

**YOUR TASK:** Analyze the following feature request using the EXACT same format as the example above (User Story, Technical Requirements with bullet points, Code Structure with JavaScript examples, and UI/UX Considerations).

Feature Request: "Add a 5-star rating component to rate prompt effectiveness"
```
A well structured one-shot prompt for feature implementation should include:
1. A user story describing the feature need
2. Technical requirements with bullet points
3. Code structure with examples showing how to implement it
4. UX considerations for the user interface
this format provides a comprehensive example that guides the AI to respond in the same structured manner

AI assistants are capable at crafting prompts for themselves. You can ask them to help break down complex tasks into smaller tasks and then help create the prompt.   
You can specify a particular prompting technique you want to use (like one-shot prompting) and ask for help creating a good example.    
You can also ask the AI to help parse down or make your prompts more efficient.

## Few Shot
- provides 2+ examples to stablish patterns and edge cases
- Model learns nuances and variations from diverse examples
- Include variety: different inputs, outputs, edge cases
- More effective as models get larger
- the best quality result - from 4 to 8 examples

 https://arxiv.org/abs/2005.14165    

 Best practices incluede:
 - ensuring divercity in examples,
 - including edge cases and failure cases
 - keeping examples concise but complete without sacrificing quality
 - testing different numbers of examples across multiple chats to determine optimal perfomance for specific use case and model
```
I need you to create a prompt for implementing a new feature. Here are examples of effective feature implementation prompts:

**EXAMPLE 1: Save/Delete Functionality Prompt**
Create a save and delete system for a prompt library application with the following requirements:

Technical Specifications:
- Save button that persists prompts to localStorage
- Delete button with confirmation dialog before removal
- Visual feedback on successful save (green checkmark animation)
- Trash icon with hover effect for delete action
- Auto-save indicator when changes are detected

Provide complete HTML, CSS, and JavaScript with:
1. Semantic HTML with data attributes for prompt IDs
2. CSS animations for save confirmation and delete hover states
3. JavaScript with proper event delegation for dynamically added prompts
4. localStorage integration with JSON serialization

The system should work with this data structure:
const prompts = [
  { id: 'prompt-001', title: "Blog Writer", content: "Generate blog posts...", savedAt: Date.now() }
];

Include error handling for localStorage quota exceeded and implement a "Recently Deleted" temporary storage (up to 5 items).

**EXAMPLE 2: Star Rating Component Prompt**
Build a 5-star rating system for rating prompt effectiveness with these specifications:

Core Requirements:
- Interactive 5-star display (click to rate, hover to preview)
- Half-star precision (4.5 stars possible)
- Shows average rating and total number of ratings
- Updates immediately without page refresh
- Allows users to change their rating

Implementation Details:
- SVG stars for crisp display at any size
- Gold fill for rated, gray outline for unrated
- Smooth hover animations (scale and glow effect)
- Display format: "4.5 ★ (23 ratings)"

Deliver production-ready code including:
1. HTML with accessible ARIA labels for screen readers
2. CSS with star animations and responsive sizing
3. JavaScript for rating logic and state management
4. Comments explaining calculation methods

Data model to support:
{
  promptId: 'prompt-001',
  ratings: [5, 4, 5, 3, 5], // Array of all ratings
  userRating: 4, // Current user's rating
  averageRating: 4.4
}

**YOUR TASK:** Based on the examples above, create a detailed prompt for building a "notes section" feature where users can add, edit, save, and delete notes for each prompt in the library.

The prompt should follow the pattern shown in the examples:

- Clear feature description
- Specific technical requirements
- Implementation details
- Expected deliverables
- Data structure/integration notes

Keep it as simple as possible to create a working notes section with only the features mentioned in your task.
```
Each example prompt should include:   
1) A clear feature description
2) Specific technical requirements
3) Implementation details
4) Expected deliverables(results) with a data structure and integration notes


You can use OpenAI's tokenizer tool to monitor token usage by copying and pasting your prompts to see how many tokens you're using. It's important to remember that tokens include your entire conversation history (input and output) and the system message, which all get appended every time you interact with the model.

## Context placement
- Where context is placed in prompts is important
- Beginning > End > Middle for information retention
- Models struggle with the middle of long contexts
- Critical info should go first, supporting details last       
  https://arxiv.org/abs/2307.03172

  
