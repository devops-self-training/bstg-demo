# GitHub Copilot Setup Guide

This document explains how to use GitHub Copilot with the Backstage Demo project.

## What's Been Configured

This project has been set up with GitHub Copilot support, including:

1. **VSCode Extension Recommendations** (`.vscode/extensions.json`)
   - GitHub Copilot extension
   - GitHub Copilot Chat extension

2. **VSCode Settings** (`.vscode/settings.json`)
   - Copilot enabled for various file types (TypeScript, JavaScript, YAML, Markdown)
   - Auto-completions enabled
   - Inline suggestions enabled

3. **Project-Specific Instructions** (`.github/copilot-instructions.md`)
   - Comprehensive project context for GitHub Copilot
   - Coding conventions and patterns
   - Project structure and technology stack
   - Backstage-specific patterns and best practices

## Getting Started

### Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/)
- [GitHub Copilot subscription](https://github.com/features/copilot) (individual, business, or enterprise)
- Access to this repository

### Installation Steps

1. **Open the project in VSCode**
   ```bash
   code /path/to/bstg-demo
   ```

2. **Install Recommended Extensions**
   - When you open the project, VSCode will prompt you to install recommended extensions
   - Click "Install All" or manually install:
     - `GitHub.copilot` - GitHub Copilot
     - `GitHub.copilot-chat` - GitHub Copilot Chat

3. **Sign in to GitHub Copilot**
   - Click on the GitHub Copilot icon in the status bar (bottom right)
   - Follow the prompts to sign in with your GitHub account
   - Authorize VSCode to access GitHub Copilot

4. **Verify Installation**
   - Open any TypeScript or JavaScript file
   - Start typing a function or comment
   - You should see inline suggestions from Copilot (shown in gray text)
   - Press `Tab` to accept suggestions

## Using GitHub Copilot

### Inline Suggestions

As you type code, Copilot will automatically suggest completions:
- **Accept suggestion**: Press `Tab`
- **Reject suggestion**: Press `Esc` or keep typing
- **See alternative suggestions**: Press `Alt+]` (next) or `Alt+[` (previous)

### Copilot Chat

Open the Copilot Chat panel:
- **Keyboard shortcut**: `Ctrl+Alt+I` (Windows/Linux) or `Cmd+Option+I` (Mac)
- **Or**: Click the chat icon in the Activity Bar

Use Copilot Chat to:
- Ask questions about the codebase
- Get explanations of existing code
- Request code refactoring suggestions
- Generate tests
- Debug issues

### Context-Aware Assistance

GitHub Copilot has access to the project-specific instructions in `.github/copilot-instructions.md`, which means it understands:
- This is a Backstage project
- The monorepo structure with Yarn workspaces
- TypeScript and React conventions used in the project
- Backstage-specific patterns (plugins, catalog, templates, etc.)
- Testing and linting requirements

### Example Prompts

Here are some example prompts you can use with Copilot Chat:

- "How do I create a new Backstage plugin in this project?"
- "Explain the structure of the catalog-info.yaml file"
- "Generate a test for the HomePage component"
- "How do I add a new software template?"
- "What's the difference between app and app-migrated packages?"
- "How do I configure a new backend module?"

## Project-Specific Tips

### When Working on Frontend Code

- Copilot understands Material-UI components used in Backstage
- It knows to use functional components with hooks
- It will suggest TypeScript types appropriately

### When Working on Backend Code

- Copilot knows about the new backend system
- It understands Backstage backend modules and plugins
- It will suggest proper configuration patterns

### When Working on Plugins

- Copilot understands Backstage plugin architecture
- It can help scaffold plugin components
- It knows the common patterns for catalog, scaffolder, and other plugins

## Troubleshooting

### Copilot Not Working

1. **Check Status**: Look at the GitHub Copilot icon in the status bar
   - If it shows "Copilot: Ready", it's working
   - If it shows an error, click it for details

2. **Verify Authentication**: 
   - Click on your account icon in the bottom left
   - Ensure you're signed in to GitHub
   - Check that Copilot is enabled for your account

3. **Check Extension**: 
   - Go to Extensions view (`Ctrl+Shift+X`)
   - Verify GitHub Copilot and Copilot Chat are installed and enabled

4. **Reload VSCode**: 
   - Run command: "Developer: Reload Window"
   - Or close and reopen VSCode

### Suggestions Not Appearing

1. Check that inline suggestions are enabled:
   - Open Settings (`Ctrl+,`)
   - Search for "inline suggest"
   - Ensure "Editor > Inline Suggest: Enabled" is checked

2. Verify file type support:
   - Copilot is enabled for `.ts`, `.tsx`, `.js`, `.jsx`, `.yaml`, `.md` files
   - Check `.vscode/settings.json` for enabled file types

### Getting Poor Suggestions

1. **Provide More Context**: 
   - Add descriptive comments above your code
   - Use meaningful variable and function names
   - Reference the project-specific instructions

2. **Use Copilot Chat**: 
   - For complex tasks, use Copilot Chat instead of inline suggestions
   - Provide detailed prompts with context

## Configuration Files

### `.vscode/extensions.json`
Recommends the GitHub Copilot extensions to all project contributors.

### `.vscode/settings.json`
Configures Copilot settings for the project, including which file types have Copilot enabled.

### `.github/copilot-instructions.md`
Provides project-specific context to GitHub Copilot, helping it understand:
- Project structure and conventions
- Technology stack
- Backstage-specific patterns
- Best practices for this codebase

You can update this file as the project evolves to keep Copilot's understanding current.

## Security and Privacy

- GitHub Copilot processes your code to provide suggestions
- Suggestions are based on public code and your context
- See [GitHub Copilot Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-copilot-privacy-statement) for details on data usage
- Review all suggestions before accepting them
- Don't commit sensitive information in comments that Copilot might learn from

## Best Practices

1. **Review Suggestions**: Always review Copilot's suggestions before accepting
2. **Write Good Comments**: Descriptive comments help Copilot understand intent
3. **Follow Project Conventions**: Copilot learns from existing patterns
4. **Test Generated Code**: Always test code suggested by Copilot
5. **Use Copilot Chat for Complex Tasks**: For architectural questions or complex refactoring
6. **Keep Instructions Updated**: Update `.github/copilot-instructions.md` as the project evolves

## Additional Resources

- [GitHub Copilot Documentation](https://docs.github.com/en/copilot)
- [GitHub Copilot in VSCode](https://code.visualstudio.com/docs/copilot/overview)
- [Backstage Documentation](https://backstage.io/docs)
- [Backstage Architecture](https://backstage.io/docs/overview/architecture-overview)

## Feedback

If you have suggestions for improving the GitHub Copilot configuration or instructions for this project, please open an issue or submit a pull request.
