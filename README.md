# deep-dives

Personal study notes on real-world software architecture, written by reading company engineering blogs closely enough to explain the mechanics back to myself. Not a curated reference for other people, though anyone's welcome to read it.

**Live site:** https://rahulkaushal04.github.io/deep-dives/

## Structure

- `docs/companies/` — one page per system at one company.
- `docs/assets/diagrams/<company>/` — rendered PNGs embedded in the pages, plus the `.drawio` source files they were generated from.
- `docs/index.md` — the home page and company index.

## Local development

```bash
python -m venv .venv && source .venv/bin/activate && pip install -r requirements.txt
```

```bash
mkdocs serve
```

Then open <http://127.0.0.1:8000>.

## Diagrams

Diagrams are built as `.drawio` files and exported to PNG with the draw.io desktop CLI, not Mermaid. The source `.drawio` file sits next to its exported PNG in `docs/assets/diagrams/<company>/`, so any diagram can be reopened and edited in draw.io later.

To re-export a diagram after editing it:

```bash
drawio -x -f png -e -s 2 -b 30 -o path/to/diagram.png path/to/diagram.drawio
```

## Deployment

`.github/workflows/deploy.yml` builds on every push to `main` and deploys to GitHub Pages.

One-time setup:

1. Push the repo to GitHub.
2. **Settings → Pages → Build and deployment → Source: GitHub Actions.**
