# Setup Guide

## Prerequisites

- Python 3.10+
- pip or uv

## Installation

```bash
# Clone the repository
git clone https://github.com/vindicta-platform/mkdocs.git
cd mkdocs

# Install dependencies
pip install mkdocs mkdocs-material

# Or with uv
uv pip install mkdocs mkdocs-material
```

## Local Development

```bash
# Start development server
mkdocs serve

# Access at http://localhost:8000
```

## Building

```bash
# Build static site
mkdocs build

# Output in site/ directory
```

## Deployment

The site auto-deploys to GitHub Pages via GitHub Actions on push to `main`.

## Contributing

1. Create a branch for your changes
2. Add/modify documentation in `docs/`
3. Test locally with `mkdocs serve`
4. Submit a pull request
