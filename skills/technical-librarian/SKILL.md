---
name: technical-librarian
description: Access, search, and summarize content from a technical book collection. Use this skill whenever the user asks a technical question related to software architecture, programming patterns, or specific technologies found in their "bookshelf".
---

# Technical Librarian

Expertly navigates a collection of technical PDFs to provide cited, deep-dive answers to software engineering questions.

## Core Mandates
1. **Bootstrap First:** The technical bookshelf is sourced from `https://github.com/kingnathanal/technical-bookshelf.git`. Check if a local clone exists (defaulting to `~/technical-bookshelf` or a path saved in memory). If it does not exist, use `run_shell_command` to clone it to `~/technical-bookshelf` before proceeding. 
2. **Search Strategy:**
   - Use `list_directory` or `ls` on the local bookshelf directory to identify the most relevant book titles.
   - Use `grep_search` with the `--fixed-strings` flag on the library directory to find specific terms across all books.
   - Prioritize files under 100MB for faster extraction.
3. **Citations:** Always state which book (and page number if possible) the information came from.
4. **Context Management:** When reading a PDF, use `read_file` to extract only the necessary sections.

## Example Triggers
- "What does my library say about Hexagonal Architecture?"
- "Find the section in 'Clean Code' that talks about naming variables."
- "I'm struggling with Spring Boot security, check my bookshelf for a solution."