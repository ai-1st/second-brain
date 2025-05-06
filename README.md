
# Second Brain
## Problem statement
Right context is arguably the single most important factor in LLM performance. Yet overloading LLMs with too much context or irrelevant context dilutes the signal-to-noise ratio. 

## Solution
Here we propose an approach to manage context in a structured way:
- Convert raw information into pre-processed opinionated focused memos. Important: Second Brain is not a storage of everything (like many RAG knowledge bases), but a storage of curated, high-value memos.
- Users review all memos at the time of extractions and adjust the extraction rules immediately to make sure the second brain is not polluted with low-value content.
- Second Brain is used when users need to set the context for some AI tools, such as social post generator, PPT creator, or vibe coding assistant.
- Users may choose the whole Second Brain, a particular category, or a set of memos based on similarity search.
- Second Brain evolves as new memos are being added, but also during regular deduplication/cleanup sessions, which are called "sleep" sessions.

### Memo structure
Each memo has a title and body. Title is plain-text, body is markdown. Title is duplicated as the first header in the body.

### Memo storage

- Each memo is stored in a separate file, named by its title. Files can be edited using any text editor.
- Memo files are placed in a folders tree, where each folder is a category. The taxonomy is at the discretion of the user.
- Memos used for the system context are stored in the 'system' folder.

### Memo retrieval

- A local vector database is used to store the memo embeddings and perform similarity searches.
- The database contains embedding, and the file path.

## Implementation

see [docs/design.md](docs/design.md)

