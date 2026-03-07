# Prism Template Registry

Community-maintained research environment templates for [Prism](https://github.com/scttfrdmn/prism).

Templates here are fetched automatically the first time you run `prism templates list` or `prism launch`. They are cached locally and refreshed periodically.

## Available Templates

| Template | Description | Port(s) |
|----------|-------------|---------|
| `basic-research-apt` | Ubuntu 22.04 with essential research packages | 22 |
| `datasette` | Publish and explore datasets via browser | 8001 |
| `label-studio` | ML training data annotation | 8090 |
| `openrefine` | Browser-based data cleaning | 3333 |
| `python-ml-config` | Configurable Python ML environment | 8888 |
| `r-base-ubuntu24` | Minimal R 4.4+ on Ubuntu 24.04 | 22 |
| `r-rstudio-server` | R + RStudio Server web IDE | 8787 |
| `r-shiny` | R Shiny Server for interactive apps | 3838 |
| `r-research-full-stack` | Complete R environment with Quarto, LaTeX, Python | 8787, 8888 |
| `r-publishing-stack` | R stacked template with full publishing tools | 8787, 8888 |
| `streamlit` | Interactive Python data apps | 8501 |
| `ubuntu-datascience` | Desktop + Jupyter + RStudio | 8888, 8787 |
| `collaborative-workspace` | Multi-language team research environment | 8888, 8787, 8443 |
| `ultimate-workstation` | Everything: desktop, Jupyter, RStudio, Streamlit | 8888, 8787, 8501 |

## Using Templates

```bash
# List all available templates (fetches registry automatically)
prism templates list

# Launch a community template
prism launch datasette my-data-explorer
prism launch r-rstudio-server my-r-project

# Force refresh the template cache
prism templates sync

# Get details about a template
prism templates info datasette
```

## Contributing

Have a template that would help other researchers? [Open an issue](https://github.com/scttfrdmn/prism-template-registry/issues/new/choose) using the **Submit Template** form, or submit a pull request directly against `templates/`.

### Pull Request Guidelines

1. Add your template YAML to `templates/`
2. Follow naming: `tool-name.yml` or `purpose-tool.yml`
3. Include all required fields: `name`, `slug`, `description`, `base`, `post_install`
4. Test locally: `prism launch my-template test-instance --dry-run`
5. Set `validation_status: "community"` in your template

### Required Template Fields

```yaml
name: "Human-readable name"
slug: "url-safe-identifier"          # used in: prism launch <slug>
description: "One-line description"
long_description: |                   # shown in: prism templates info
  Multi-line detailed description.
author: "Your Name"
version: "1.0.0"
base: "ubuntu-24.04"                 # or ubuntu-22.04
connection_type: "ssh"               # ssh | web | both
validation_status: "community"       # community | validated | testing
```

See [template.schema.json](template.schema.json) for the full field reference.

## License

Templates contributed under [CC0 1.0 Universal](LICENSE) — contributors waive all copyright, allowing Prism to distribute them freely to all users.
