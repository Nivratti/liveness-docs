# liveness-docs
Documentation for the Face Liveness Verification project, built with MkDocs. Includes setup guides, API documentation, deployment steps, and development notes.

## Running the Documentation Locally
To view the documentation locally, you can use MkDocs' built-in development server:

1. **Install MkDocs** (if not already installed):
   ```bash
   pip install mkdocs-material
   ```

2. **Serve the documentation**:
   ```bash
   mkdocs serve
   ```

   This will start a local server, typically accessible at `http://127.0.0.1:8000`. The server will watch for changes and automatically rebuild the documentation.

## Deploying the Documentation
MkDocs makes it easy to deploy your documentation to a hosting platform, such as GitHub Pages. Follow these steps:

1. **Build the static site**:
   ```bash
   mkdocs build
   ```

   This generates a `site/` directory containing the static files.

2. **Deploy to GitHub Pages**:
   ```bash
   mkdocs gh-deploy
   ```

   This command will build the site (if not already built) and push the `site/` directory to the `gh-pages` branch of your repository.

Refer to the [MkDocs documentation](https://www.mkdocs.org/) for more details and advanced configuration options.
