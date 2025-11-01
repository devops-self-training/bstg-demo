# GitHub Copilot Instructions for Backstage Demo

This repository is the source code for the demo [Backstage](https://backstage.io/) instance deployed to [demo.backstage.io](https://demo.backstage.io).

## Project Overview

This is a **Backstage** application that showcases Backstage's core features and additional plugins. It follows the standard Backstage monorepo structure with Yarn workspaces.

## Technology Stack

- **Framework**: Backstage (React-based developer portal framework)
- **Runtime**: Node.js 20 or 22
- **Package Manager**: Yarn 4.5.0 (Berry)
- **Language**: TypeScript 5.4
- **Testing**: Jest, Playwright
- **Linting**: ESLint
- **Formatting**: Prettier

## Project Structure

```
/
├── packages/
│   ├── app/              # Main frontend application (Legacy Frontend System)
│   ├── app-migrated/     # Frontend with New Frontend System (Alpha)
│   └── backend/          # Backend services
├── plugins/              # Custom Backstage plugins
│   ├── catalog-backend-module-example-processor/
│   └── notifications-tester-backend/
├── demo-template/        # Software template examples
├── docs/                 # TechDocs documentation
├── scripts/              # Utility scripts
└── open-telemetry/       # OpenTelemetry configuration
```

## Coding Conventions

### TypeScript

- Use TypeScript with strict type checking
- Follow the `@backstage/cli` TypeScript configuration
- Use `react-jsx` for JSX transformation
- Prefer functional components with hooks over class components

### React Components

- Use React functional components with hooks
- Follow Backstage's component patterns
- Use Material-UI components (Backstage uses Material-UI)
- Keep components small and focused

### File Organization

- Each workspace package has its own `src/` directory
- Component files use PascalCase (e.g., `HomePage.tsx`)
- Utility files use camelCase (e.g., `customTheme.ts`)
- Test files use `.test.ts` or `.test.tsx` suffix

### Imports

- Use absolute imports via TypeScript path mappings
- Follow Backstage import conventions:
  ```typescript
  // Backstage core imports
  import { ... } from '@backstage/core-plugin-api';
  import { ... } from '@backstage/core-components';
  
  // Plugin imports
  import { ... } from '@backstage/plugin-catalog-react';
  
  // Local imports
  import { ... } from './components';
  ```

### Styling

- Use Material-UI's `makeStyles` or `styled` for component styling
- Follow the Backstage theme structure
- Custom themes should extend Backstage's base themes

## Backend Development

- Use the **new backend system** introduced in recent Backstage versions
- Backend modules follow Backstage's plugin architecture
- Configuration is managed via `app-config.yaml` files
- Environment-specific configs: `app-config.local.yaml`, `app-config.heroku.yaml`

## Testing

- Write tests using Jest for unit tests
- Use Playwright for E2E tests
- Run tests with: `yarn test` or `yarn test:all` for coverage
- Follow existing test patterns in the codebase

## Commands

- **Start dev server**: `yarn start`
- **Start migrated app**: `yarn start:app-migrated`
- **Build backend**: `yarn build:backend`
- **Build all**: `yarn build:all`
- **Run tests**: `yarn test`
- **Lint**: `yarn lint` or `yarn lint:all`
- **Format**: `yarn prettier:check`
- **Fix issues**: `yarn fix`

## Backstage-Specific Patterns

### Plugins

- Backstage plugins follow a modular architecture
- Frontend plugins export React components
- Backend plugins export modules that integrate with the backend system
- Use `@backstage/create-plugin` to scaffold new plugins

### Catalog

- Entities are defined in `catalog-info.yaml` files
- The catalog is populated via static configuration and GitHub Entity Provider
- Entity relationships are defined using refs and relations

### Software Templates

- Templates are defined in YAML with Nunjucks templating
- Located in the `demo-template/` directory
- Use Backstage scaffolder actions for common tasks

### TechDocs

- Documentation is written in Markdown
- Configured via `mkdocs.yml`
- Located in the `docs/` directory

## Configuration

- Main config: `app-config.yaml`
- Local overrides: `app-config.local.yaml` (gitignored)
- Secrets should never be committed to the repository
- Use environment variables for sensitive data

## Important Notes

- This demo uses weekly `next` release line of Backstage
- Keep dependencies updated via Renovate
- The New Frontend System is in Alpha (see `app-migrated`)
- OpenTelemetry is configured for local observability
- GitHub webhooks are configured for catalog event ingestion

## Feature Flags

The demo supports feature flags for experimental features:
- Check `packages/app/src/featureFlags.ts` for available flags
- Toggle flags at `/settings/feature-flags`

## Custom Implementations

- **Custom Theme**: See `packages/app/src/theme/aperture.ts`
- **Custom Home Page**: See `packages/app/src/components/home/`
- **Custom Search**: Extended in `packages/app/src/components/search/SearchPage.tsx`

## Best Practices

1. Follow Backstage's architecture and patterns
2. Keep changes minimal and focused
3. Test changes locally before committing
4. Update documentation when adding features
5. Use existing plugins when possible before creating custom ones
6. Follow the monorepo structure with Yarn workspaces
7. Ensure TypeScript types are properly defined
8. Run linting and formatting before committing (Husky pre-commit hooks)

## Resources

- [Backstage Documentation](https://backstage.io/docs)
- [Backstage Architecture](https://backstage.io/docs/overview/architecture-overview)
- [Plugin Development](https://backstage.io/docs/plugins/)
- [New Backend System](https://backstage.io/docs/backend-system/)
