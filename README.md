# Note Factor

Note Factor is an automated knowledge management system that processes Markdown notes, generates metadata, and organizes them into a structured hierarchy. The system uses local LLM models to extract key concepts, generate summaries, and create additional AI-generated content for incomplete notes.

## Features
- Automatic metadata extraction (concepts, tags, summary)
- AI content generation for missing or incomplete sections
- Folder-based hierarchy organization
- Map of Content (MOC) creation and merging
- Global knowledge index generation
- Custom YAML frontmatter with timestamps and AI generation flags

## Technologies Used
- Python
- Ollama API
- YAML
- Regular Expressions
- pathlib
- datetime

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/DeathSurfing/NoteFactor.git
   cd NoteFactor
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Start the Ollama service locally.

## Usage
1. Set your paths and model in the `__main__` section:
   ```python
   VAULT_ROOT = Path("/path/to/vault")
   NOTES_ROOT = VAULT_ROOT / "Notes"
   OUTPUT_DIR = VAULT_ROOT / "Structured_Notes"
   MODEL = "mistral-small:22b"
   ```
2. Run the pipeline:
   ```bash
   python note_factor.py
   ```
3. The processed notes will be stored in the `Structured_Notes` directory.

## Folder Structure
```
VAULT_ROOT
├── Notes              # Input notes
└── Structured_Notes   # Output structured notes
    ├── Topic1
    │   ├── Subtopic1
    │   └── Topic1 MOC.md
    └── _HIERARCHY.md   # Global index
```

## Metadata Example
```yaml
---
created: 2025-03-03T10:00:00
modified: 2025-03-03T10:10:00
source: [[Note Title]]
hierarchy:
  - Topic1
  - Subtopic1
tags:
  - concept
summary: This note discusses the core ideas of...
concepts:
  - MainConcept
  - RelatedConcept1
  - RelatedConcept2
ai_generated: true
---
```

## Contributing
Pull requests are welcome! If you'd like to contribute, please fork the repository and create a new branch.

## License
This project is licensed under the MIT License.
