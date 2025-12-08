# Giving Compass Insights API Documentation

## Project Overview

This Mintlify documentation project serves two distinct personas with different information needs:

### 1. Project Manager Persona → "Documentation" Tab
- **Location**: `/documentation/` directory
- **Purpose**: High-level product guides, use cases, and conceptual explanations
- **Content focus**: What the API can do, why it matters, business value
- **Tone**: Accessible, benefits-oriented, minimal technical jargon

### 2. Software Developer Persona → "API Reference" Tab
- **Location**: `/api-reference/` directory + auto-generated from `openapi.json`
- **Purpose**: Technical implementation details, endpoint specifications, code examples
- **Content focus**: How to integrate, request/response formats, authentication
- **Tone**: Technical, precise, code-heavy

## File Structure

```
/
├── docs.json           # Navigation, theme, API configuration
├── openapi.json        # OpenAPI 3.1 spec (auto-generates endpoint pages)
├── index.mdx           # Landing page
├── documentation/      # Project Manager-focused content
│   └── feed.mdx        # Nonprofit Feed product guide
└── api-reference/      # Developer-focused content
    ├── overview.mdx    # API reference introduction
    └── endpoints/      # Endpoint-specific pages
        └── feed-posts.mdx
```

## OpenAPI Integration

The `openapi.json` file defines all API endpoints. Mintlify auto-generates interactive API reference pages from this spec.

### Key API Capabilities (from openapi.json)

- **Nonprofit Search** (`/nonprofits/search`): Filter by location, revenue, NTEE codes, SDGs, ratings
- **Nonprofit Details** (`/nonprofits/details/{ein}`): Full profile by EIN
- **Feed Posts** (`/feed/posts`): Articles, events, videos, jobs from nonprofits
- **Impact Stories** (`/impact/stories`): Human transformation narratives from annual reports
- **Impact Metrics** (`/impact/metrics`): Quantitative measures (people served, etc.)

### Authentication
All endpoints require `X-API-Key` header authentication.

### Base URL
```
https://api.givingcompass.org/insights
```

## Writing Guidelines

### For Documentation Tab (Project Managers)
- Lead with user benefits and use cases
- Explain concepts before diving into details
- Use real-world scenarios and examples
- Avoid requiring API knowledge to understand value

### For API Reference Tab (Developers)
- Be precise about data types, formats, and constraints
- Include working code examples
- Document error responses and edge cases
- Reference the OpenAPI spec as the source of truth

## Configuration Reference

### docs.json Key Sections
- `navigation.tabs`: Defines the Documentation and API Reference tabs
- `openapi`: Points to `openapi.json` for auto-generation
- `api.baseUrl`: Sets the API playground base URL
- `api.auth`: Configures X-API-Key authentication

### Frontmatter Requirements
Every MDX file must include:
```yaml
---
title: "Page Title"
description: "Brief description for SEO and navigation"
---
```

## Common Tasks

### Adding a New Product Guide (Documentation Tab)
1. Create MDX file in `/documentation/`
2. Add frontmatter with title and description
3. Register in `docs.json` under `navigation.tabs[0].groups`

### Adding an Endpoint Page (API Reference Tab)
1. Endpoint pages auto-generate from `openapi.json`
2. For custom content, create MDX in `/api-reference/endpoints/`
3. Register in `docs.json` under `navigation.tabs[1].groups`

### Updating API Specification
1. Replace `openapi.json` with updated spec
2. Mintlify regenerates endpoint pages automatically
3. Verify changes with `mint dev`

## Do Not
- Skip frontmatter on any MDX file
- Use absolute URLs for internal links
- Make assumptions—ask for clarification
- Duplicate content between tabs without strategic reason
- Modify `openapi.json` manually (it's generated from the API)
