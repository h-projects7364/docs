# Pockla Documentation

This repository contains the documentation for Pockla, built with [Mintlify](https://mintlify.com).

## Structure

```
pockla-docs/
├── docs.json                    # Mintlify configuration
├── index.mdx                    # Homepage
├── getting-started/             # Getting started guides
│   ├── setup.mdx
│   └── quickstart.mdx
├── contacts/                    # Contacts documentation
│   ├── adding-contacts.mdx
│   └── columns.mdx
├── lists/                       # Lists documentation
│   └── introduction.mdx
├── boards/                      # Boards documentation
│   ├── introduction.mdx
│   ├── panels.mdx
│   └── adding-email.mdx
├── links/                       # Links documentation
│   └── introduction.mdx
├── operations/                  # Operations documentation
│   ├── batch.mdx
│   └── workflow.mdx
├── data/                        # Data & AI documentation
│   ├── enriching-data.mdx
│   └── research-agent.mdx
├── integrations/                # Integrations documentation
│   ├── introduction.mdx
│   ├── hubspot/
│   │   ├── overview.mdx
│   │   └── installation.mdx
│   └── js-snippet/
│       └── installation.mdx
├── screenshots/                 # Screenshots for docs (generated)
├── logo/                        # Pockla logos
│   ├── light.svg
│   └── dark.svg
└── images/                      # Other images
```

## Local Development

### Prerequisites

- Node.js 18+
- npm or pnpm

### Setup

```bash
# Install Mintlify CLI
npm i -g mintlify

# Start local development server
mintlify dev
```

The docs will be available at http://localhost:3000

## Generating Screenshots

Screenshots are generated from the main Pockla app using Playwright.

```bash
# In the pockla-app-docs-source directory:
cd ../pockla-app-docs-source

# Set credentials
export E2E_EMAIL="your-test-email@example.com"
export E2E_PASSWORD="your-test-password"
export E2E_BASE_URL="http://localhost:3001"

# Run screenshot tests
npx playwright test docs-screenshots.spec.ts
```

Screenshots are saved to `screenshots/` directory.

## Placeholder Convention

Content that needs to be filled in is marked with HTML comments:

```markdown
<!-- TODO: Description of what's needed -->
```

To find all placeholders:
```bash
grep -r "<!-- TODO:" .
```

## Deployment

Docs are automatically deployed when pushed to the `main` branch via Mintlify's GitHub integration.

## Content Guidelines

1. **Screenshots**: Include screenshots for all major UI elements
2. **Placeholders**: Use `<!-- TODO: description -->` for missing content
3. **Code Examples**: Use fenced code blocks with language hints
4. **Links**: Use relative paths for internal links (e.g., `/contacts/adding-contacts`)
5. **Components**: Use Mintlify components like `<Card>`, `<Steps>`, `<Accordion>`

## Adding New Pages

1. Create the `.mdx` file in the appropriate directory
2. Add the page to `docs.json` navigation
3. Include frontmatter with title, description, and icon

```markdown
---
title: "Page Title"
description: "Brief description"
icon: "icon-name"
---
```

## Resources

- [Mintlify Documentation](https://mintlify.com/docs)
- [MDX Syntax](https://mdxjs.com/)
- [Font Awesome Icons](https://fontawesome.com/icons)
