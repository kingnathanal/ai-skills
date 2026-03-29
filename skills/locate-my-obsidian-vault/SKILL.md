---
name: locate-my-obsidian-vault
description: Locate and confirm the user's main Obsidian vault without searching the whole computer. Use this skill whenever the user mentions finding their Obsidian vault, asks where the allnotes vault lives, wants to work inside their Obsidian notes, or when an agent is about to scan the filesystem for the user's vault path. Prefer this known location over broad search commands.
---

# Locate My Obsidian Vault

Use this skill to save time whenever an agent needs the user's primary Obsidian vault location.

## Known vault details

- Vault name: `allnotes`
- Filesystem path: `/Users/kingnathanal/Library/Mobile Documents/iCloud~md~obsidian/Documents/allnotes`
- Shell-safe path: `"/Users/kingnathanal/Library/Mobile Documents/iCloud~md~obsidian/Documents/allnotes"`

## Default behavior

1. Treat `allnotes` as the user's default Obsidian vault unless the user explicitly says they want a different vault.
2. Answer with the known vault name and path immediately instead of starting with `find`, `mdfind`, `rg`, or other broad filesystem searches.
3. If you need to run shell commands against the vault, use the quoted shell-safe path so spaces are handled correctly.
4. If verification is useful, limit checks to this exact path rather than searching the rest of the machine.

## Suggested command pattern

When a command needs the vault path, prefer forms like:

```bash
ls "/Users/kingnathanal/Library/Mobile Documents/iCloud~md~obsidian/Documents/allnotes"
```

## Response guidance

- When the user asks where their Obsidian vault is, provide the vault name and exact path up front.
- When another task depends on the vault path, reuse this location directly and move on to the real work.
- Only search for a different vault if the user explicitly indicates that `allnotes` is not the target.

## Example triggers

- "Locate my Obsidian vault."
- "Where is my allnotes vault on disk?"
- "Use my Obsidian vault to create a note about today's meeting."
- "Before you search for my vault, it's probably already known somewhere."
