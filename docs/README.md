# Research Framework GitHub Pages

This directory contains the GitHub Pages site for the Claude Code Framework Research project.

## Site Structure

```
docs/
├── _config.yml                 # Jekyll configuration
├── _includes/                  # Reusable components
│   ├── breadcrumbs.html       # Navigation breadcrumbs
│   ├── page-navigation.html   # Page footer navigation
│   ├── related-pages.html     # Related content links
│   └── search.html            # Lunr.js search functionality
├── assets/
│   └── css/
│       └── style.scss         # Custom theme styles
├── index.md                   # Homepage
├── frameworks.md              # Framework directory (21 frameworks)
├── comparisons.md             # Comparison hub
├── synthesis.md               # Cross-framework synthesis
├── super-hero.md              # Super-Hero framework vision
├── frameworks/                # Individual framework pages (21 total)
└── comparisons/               # Category comparisons
    ├── methodology.md         # 11 frameworks
    ├── orchestrator.md        # 6 frameworks
    └── domain-specific.md     # 2 frameworks
```

## Navigation Structure

```
Home
├── Frameworks (directory of all 21)
├── Comparisons
│   ├── Methodology (11 frameworks)
│   ├── Orchestrator (6 frameworks)
│   └── Domain-Specific (2 frameworks)
├── Synthesis (cross-framework analysis)
└── Super-Hero (ideal framework vision)
```

## Development

### Local Testing

```bash
# Install dependencies
bundle install

# Serve locally
bundle exec jekyll serve

# View at http://localhost:4000/claude-framework-research/
```

### Configuration

Key settings in `_config.yml`:
- `baseurl`: `/claude-framework-research`
- `url`: `https://regis-rcr.github.io`
- `theme`: `minima`
- `plugins`: jekyll-feed, jekyll-seo-tag

## Links Validation

All internal links use the pattern:
```markdown
[Link Text](/claude-framework-research/path/)
```

## License

Same as parent repository - see main LICENSE file.

---

*Last updated: 2025-11-28*
