# Claude Context Library for Maloney's Geometry

Use these files to give Claude quick access to your geometry system:

- `axioms-reference.md` — All axioms, theorems, key definitions
- `notation-guide.md` — Symbol meanings and common abbreviations
- `style-guide.md` — How to write proofs and definitions in your style

Load all three at the start of each aider session for best results.

## Quick Session Setup
```bash
aider --model ollama_chat/phi4-extended
/add .claude-context/axioms-reference.md
/add .claude-context/notation-guide.md
/add .claude-context/style-guide.md
/add config/theorem-setup.tex
/add content/body/set-theory/angles.tex
/add content/body/set-theory/primatives.tex
```

Then paste your prompt.
