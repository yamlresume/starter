# YAMLResume Starter

A starter template for creating professional resumes with [YAMLResume](https://yamlresume.dev).

[![Build Resumes](https://github.com/yamlresume/starter/actions/workflows/build.yml/badge.svg)](https://github.com/yamlresume/starter/actions/workflows/build.yml)
[![pages-build-deployment](https://github.com/yamlresume/starter/actions/workflows/pages.yml/badge.svg)](https://github.com/yamlresume/starter/actions/workflows/pages.yml)

## Features

- **Multiple Languages**: Includes sample resumes in English and Chinese (Simplified)
- **Automated Builds**: GitHub Actions automatically builds your resumes on every push
- **PDF Generation**: Generates professional PDF resumes
- **HTML Output**: Creates web-friendly HTML versions
- **GitHub Pages**: Automatically deploys HTML resumes to GitHub Pages
- **Release Artifacts**: Create releases with downloadable PDFs by pushing tags

## Quick Start

### 1. Use This Template

Click the "Use this template" button above to create your own repository.

### 2. Customize Your Resumes

Edit the files in the `resumes/` directory:

- `resumes/resume-en.yml` - English resume
- `resumes/resume-zh-hans.yml` - Chinese (Simplified) resume

### 3. Enable GitHub Pages

1. Go to **Settings** → **Pages** in your repository
2. Under "Build and deployment", select **GitHub Actions** as the source
3. Your resumes will be published at `https://yourusername.github.io/your-repo-name`

### 4. Build and Download

The GitHub Actions workflow will automatically:
- Build your resumes on every push to `main`
- Upload PDF, HTML, and Markdown artifacts
- Deploy HTML versions to GitHub Pages

To download your resumes:
1. Go to the **Actions** tab
2. Click on the latest workflow run
3. Download the artifacts from the bottom of the page

### 5. Create a Release

To create a release with downloadable PDFs:

```bash
git tag v1.0.0
git push origin v1.0.0
```

This will trigger the release workflow and create a GitHub Release with your resume files attached.

## Resume Structure

Your resume is defined in YAML format. Here's a basic structure:

```yaml
---
content:
  basics:
    name: Your Name
    headline: Your Title
    email: your@email.com
    phone: "(123) 456-7890"
    summary: |
      A brief summary of your professional background

  work:
    - name: Company Name
      position: Job Title
      startDate: Jan 2020
      endDate: Dec 2023
      summary: |
        - Key achievement 1
        - Key achievement 2

  education:
    - institution: University Name
      degree: Bachelor
      area: Computer Science
      startDate: Sep 2016
      endDate: May 2020

  skills:
    - name: Programming
      level: Expert
      keywords:
        - Python
        - JavaScript
        - TypeScript

locale:
  language: en

layouts:
  - engine: latex
    template: moderncv-banking
    typography:
      fontSize: 11pt
  - engine: html
    template: calm
    typography:
      fontSize: 16px
```

## Available Templates

### LaTeX Templates
- `moderncv-banking` - Professional banking style
- `moderncv-casual` - Casual style
- `moderncv-classic` - Classic style
- `moderncv-oldstyle` - Old style

### HTML Templates
- `calm` - Clean and minimal design

## Customization

### Changing Templates

Edit the `layouts` section in your resume YAML:

```yaml
layouts:
  - engine: latex
    template: moderncv-casual  # Change template here
    typography:
      fontSize: 12pt
```

### Multiple Output Formats

You can generate multiple formats simultaneously:

```yaml
layouts:
  - engine: latex    # PDF output
  - engine: html     # Web page
  - engine: markdown # Markdown file
```

### Localization

Set the language for your resume:

```yaml
locale:
  language: en  # or zh-hans, zh-hant, ja, etc.
```

## Schema Validation

This template includes a schema reference at the top of each resume file:

```yaml
# yaml-language-server: $schema=https://yamlresume.dev/schema.json
```

If you use an editor with YAML language server support (like VS Code with the YAML extension), you'll get:
- Auto-completion
- Real-time validation
- Inline documentation

## GitHub Actions Workflows

### Build Workflow (`.github/workflows/build.yml`)

Runs on every push and pull request:
- Builds all resumes
- Uploads PDF, HTML, and Markdown artifacts

### Release Workflow (`.github/workflows/release.yml`)

Runs when you push a tag starting with `v`:
- Builds all resumes
- Creates a GitHub Release
- Attaches PDF, HTML, and Markdown files

### Pages Workflow (`.github/workflows/pages.yml`)

Runs on every push to `main`:
- Builds all resumes
- Deploys HTML versions to GitHub Pages

## Local Development

If you want to build resumes locally, install the [YAMLResume CLI](https://yamlresume.dev):

```bash
npm install -g @yamlresume/cli

# Build a resume
yamlresume build resumes/resume-en.yml

# List available templates
yamlresume templates list

# List supported languages
yamlresume languages list
```

## Documentation

- [YAMLResume Documentation](https://yamlresume.dev/docs)
- [Schema Reference](https://yamlresume.dev/docs/compiler/schema)
- [Available Templates](https://yamlresume.dev/docs/templates)

## License

MIT License - see [LICENSE](LICENSE) for details.

## Support

- [GitHub Issues](https://github.com/yamlresume/starter/issues)
- [YAMLResume Discord](https://discord.gg/yamlresume)
