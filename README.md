# legendary-lore-rag

Corpus of lore for legendary, mythical and other notable Pokémon (one Markdown file per Pokémon,
grouped by generation under `documents/gen-N/`), intended as the knowledge base for a RAG pipeline that will
later be packaged and consumed by the [pokédex](https://github.com/edmataDotDev/agentic-pokedex) agent project.

## Document format

Every file is `documents/gen-<N>/<Pokemon>.md` and follows this structure:

```markdown
---
pokemon: Mewtwo
generation: 1
source: https://bulbapedia.bulbagarden.net/wiki/Mewtwo_%28Pok%C3%A9mon%29
license: CC BY-NC-SA 2.5
retrieved: 2026-10-26
---

# Mewtwo

## Biology

Prose describing the Pokémon...

### Forms

Optional subsections (forms, evolution, modes, etc.), one `###` per variant.

## Pokédex entries

- One bullet per Pokédex entry.

## Origin

Prose on the design inspiration.

### Name origin

Prose on the etymology of the name.
```

Frontmatter fields:

| Field | Description |
| --- | --- |
| `pokemon` | Pokémon name |
| `generation` | Generation number (1–9), matching the `gen-N` folder |
| `source` | URL of the Bulbapedia article |
| `license` | Always `CC BY-NC-SA 2.5` |
| `retrieved` | Date the article was retrieved (`YYYY-MM-DD`) |

Body conventions:

- A single `# Name` title, followed by `##` sections in this order: `Biology`, `Pokédex entries`, `Origin`.
- `Biology` may contain `###` subsections for forms, evolution, modes, etc.; `Origin` ends with `### Name origin`.
- `Pokédex entries` is a bulleted list; the other sections are plain paragraphs.

## License and attribution

The content is derived from [Bulbapedia](https://bulbapedia.bulbagarden.net/) and is licensed under
[CC BY-NC-SA 2.5](https://creativecommons.org/licenses/by-nc-sa/2.5/): attribution required,
non-commercial use only, and derivatives must be shared under the same license. Each file links to
its source article. Pokémon and related names are trademarks of Nintendo, Creatures Inc. and
GAME FREAK inc.; this project is unaffiliated.
