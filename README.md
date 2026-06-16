# Knowledgeville

A public, openly-licensed knowledge base built on the
[Open Knowledge Format (OKF) v0.1](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md).

Browse it as a wiki at **<https://knowledge.onesteplabs.com>**.

Content lives under [`published/`](published/) as structured OKF concept files
(YAML frontmatter + markdown) and is rendered with MkDocs Material
([`mkdocs.yml`](mkdocs.yml)), deployed to GitHub Pages on every push
([`.github/workflows/deploy-wiki.yml`](.github/workflows/deploy-wiki.yml)).
