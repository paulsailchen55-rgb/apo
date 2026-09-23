# Architecture

## Conceptual Layers

### 1. Creation Layer

Free or low-cost tools create HTML, CSS, JavaScript, documents, landing pages, and simple web applications. Tools may include manual editors, downloadable generators, open-source software, and AI-assisted builders.

### 2. Publishing Layer

Independent hosting providers publish the resulting material. Candidate categories include static hosting, personal web hosts, repository-backed hosting, and community-hosted services.

### 3. Routing Layer

A redirect or link-management service maps readable public paths to destination URLs. Example:

`https://example-domain.org/projects` → `https://username.github.io/project/`

The routing layer should ideally support destination updates, transparent documentation, exportability, and minimal tracking.

### 4. Identity Layer

A central homepage or domain can provide continuity across multiple hosts. The system should avoid implying that all content is hosted in one place when it is actually distributed.

### 5. Documentation Layer

Guides explain how to create, publish, link, migrate, back up, and recover a personal site.

## Important Distinction

A custom redirect can make multiple services feel like one coherent website, but it does not remove the technical or policy dependence on the underlying providers. The project must identify each dependency.

## Candidate Deployment Patterns

- No custom domain: provider subdomains plus a central landing page.
- One custom domain: DNS and redirect routing to multiple free hosts.
- Self-controlled redirect layer: open-source redirect software hosted on an available free platform.
- Static link directory: a simple HTML page listing and explaining destinations.
