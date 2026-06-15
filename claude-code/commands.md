## /context
Shows context usage - control memory window for coding agents

## /usage
Tokens usage, price and limits in current session, current week etc.

## /clear
clean the context

## /init
Initialize a new Claude.md file with codebase documentation
You can add also you own custom instructions

## /memory
You can write or edit instructions(long term rules) in Project memory or user memory(for all projects)    
use *#* before text for adding to memory

## ultrathink
keyword activates **thinking mode** for maximum reasoning, uses more time and more tokens

## planning mode
shift + tab for switching

## /security-review
complete a security review of the pending changes on the current branch

## /consolidate-memory
clear context window with memory from previous session

## /compact
Compacts the current conversation by summarizing it, freeing up context window space while preserving the essential thread of work so the session can continue.

## using sub-agents to control context window
Add phrases like:
- let's use a task sub-agent to research this first
- create a sub-agebt to handle the implementation
- delegate the testing to a specialized sub-agent
