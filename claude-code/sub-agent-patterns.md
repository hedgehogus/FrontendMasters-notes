# Pattern 1: Research → Implementation → Testing
    
## Main Agent

- **Sub-Agent 1: Research & Planning**
  - Returns: *Implementation strategy*

- **Sub-Agent 2: Code Generation**
  - Returns: *Code files*

- **Sub-Agent 3: Testing & Validation**
  - Returns: *Test results & refinements*
 
# Pattern 2: Parallel Specialization

## Main Agent: "Build a dashboard"

- **Sub-Agent 1: Backend API** *(parallel)*
- **Sub-Agent 2: Frontend UI** *(parallel)*
- **Sub-Agent 3: Database Schema** *(parallel)*

### Main Agent: Integration

# Pattern 3: Iterative Refinement

## Main Agent

### Sub-Agent (loop)

1. Generate solution attempt
2. Test solution
3. If fails: Refine and retry
4. If passes: Return final result
