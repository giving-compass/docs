# Giving Compass Insights API Documentation

Official API documentation for the Giving Compass Insights API, built with Mintlify.

## Overview

This documentation provides comprehensive guides and auto-generated API reference for the Giving Compass Insights API, which grants access to nonprofit data, impact narratives, financial records, and AI-driven discovery capabilities.

## Documentation Structure

```
docs/
├── docs.json                # Navigation and Mintlify configuration
├── openapi.json            # OpenAPI specification (auto-generates API reference)
├── index.mdx               # Introduction and overview
├── authentication.mdx      # Authentication guide
├── quickstart.mdx          # Quickstart guide
└── api-reference.mdx       # API reference landing page
```

## Local Development

### Prerequisites

- [Node.js](https://nodejs.org/) (v14 or higher)
- npm or yarn

### Installation

Install the Mintlify CLI:

```bash
npm i -g mint
```

### Run Locally

Start the local development server:

```bash
mint dev
```

View your documentation at `http://localhost:3000`.

<Note>
The preview automatically updates as you edit files.
</Note>

## OpenAPI Integration

This documentation uses Mintlify's OpenAPI integration to auto-generate API reference pages from `openapi.json`.

### How It Works

1. **OpenAPI Spec**: The `openapi.json` file contains the complete API specification
2. **Configuration**: `docs.json` includes `"openapi": "openapi.json"` to enable auto-generation
3. **Auto-Generated Pages**: Mintlify creates interactive API reference pages for each endpoint
4. **Interactive Playground**: Users can test API calls directly in the browser

### Updating the API Reference

To update the API reference:

1. Download the latest OpenAPI spec:
   ```bash
   curl https://api.givingcompass.org/openapi.json -o openapi.json
   ```

2. The documentation will automatically regenerate on the next build

## Customization

### Branding

Edit `docs.json` to customize:

- **Colors**: Update `colors.primary`, `colors.light`, `colors.dark`
- **Logo**: Replace files in `/logo/` directory
- **Favicon**: Replace `/favicon.svg`

### Navigation

Modify the `navigation` section in `docs.json` to add or reorganize pages.

### Content

Edit MDX files to update guide content:

- `index.mdx` - Introduction page
- `authentication.mdx` - Authentication guide
- `quickstart.mdx` - Quickstart guide
- `api-reference.mdx` - API reference landing page

## Deployment

### Mintlify Hosting

1. Push changes to your GitHub repository
2. Install the Mintlify GitHub app from your [dashboard](https://dashboard.mintlify.com/settings/organization/github-app)
3. Changes are automatically deployed on push to the main branch

### Custom Hosting

Build the static site:

```bash
mint build
```

Deploy the `build/` directory to your hosting provider.

## Contributing

See `CLAUDE.md` for development guidelines and standards.

### Guidelines

- Use proper frontmatter on all MDX files
- Use relative paths for internal links
- Test all code examples before committing
- Match the style and formatting of existing pages
- Never skip pre-commit hooks

## Project Structure

This documentation includes:

- **Get Started Guide**: Introduction, authentication, and quickstart
- **API Reference**: Auto-generated from OpenAPI spec with interactive playground
- **OpenAPI Integration**: Complete endpoint documentation with request/response examples

## Resources

- [Mintlify Documentation](https://mintlify.com/docs)
- [Mintlify Components](https://mintlify.com/docs/content/components)
- [OpenAPI Integration Guide](https://mintlify.com/docs/api-playground/openapi)
- [Giving Compass API](https://api.givingcompass.org/insights)

## Support

### For API Support

- Email: [support@givingcompass.org](mailto:support@givingcompass.org)
- API Status: [status.givingcompass.org](https://status.givingcompass.org)

### For Documentation Issues

- Open an issue in this repository
- Check [Mintlify docs](https://mintlify.com/docs) for Mintlify-specific questions

## Troubleshooting

- **Dev environment not running**: Run `mint update` to ensure you have the latest CLI
- **Page loads as 404**: Make sure you're running in a folder with a valid `docs.json`
- **OpenAPI not generating**: Verify `openapi.json` is valid JSON and properly referenced in `docs.json`
