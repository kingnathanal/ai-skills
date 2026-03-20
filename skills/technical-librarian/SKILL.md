---
name: technical-librarian
description: Access, search, and summarize content from a technical book collection. Use this skill whenever the user asks a technical question related to software architecture, programming patterns, or specific technologies found in their "bookshelf".
---

# Technical Librarian

Expertly navigates a collection of technical PDFs to provide cited, deep-dive answers. This skill uses an "On-Demand" fetching strategy to minimize disk usage.

## Core Mandates
1. **Bootstrap (Meta-only):** The technical bookshelf is at `https://github.com/kingnathanal/technical-bookshelf.git`. 
   - If the directory `~/technical-bookshelf` doesn't exist, clone it using: `GIT_LFS_SKIP_SMUDGE=1 git clone https://github.com/kingnathanal/technical-bookshelf.git ~/technical-bookshelf`.
   - This ensures only the filenames are downloaded initially, keeping the clone size tiny.
2. **Search Strategy:**
   - Use `ls` on the bookshelf directory to identify relevant titles.
   - To search *inside* books without downloading them all, prioritize the most likely candidates based on filenames.
3. **On-Demand Fetching:**
   - Before reading a PDF with `read_file`, check its size. If it is < 1KB (meaning it is just an LFS pointer), run `git lfs pull --include="[filename].pdf"` to download only that specific book.
4. **Citations:** Always state which book the information came from.
5. **Context Management:** Use `read_file` to extract only the necessary sections.

## Example Triggers
- "What does my library say about Hexagonal Architecture?"
- "Find the section in 'Clean Code' that talks about naming variables."
- "I'm struggling with Spring Boot security, check my bookshelf for a solution."