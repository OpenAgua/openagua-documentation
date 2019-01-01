# OpenAgua documentation

For the pretty version of this documentation, see: https://docs.openagua.org.

This repository includes the OpenAgua documentation files. The docs aim to describe the project and how to use OpenAgua from a user perspective, not how to install it. Installation instructions will stay in the main repository, wherever that may be.

# Edit content

The documentation is written using [Markdown](https://help.github.com/articles/basic-writing-and-formatting-syntax/). So, the main content files are titled as *.md; use markdown when editing these files.

# Configuration & deployment

This documentation is built for use with [GitBook](https://www.gitbook.com). However, it was originally built for deployment with [MkDocs](https://www.mkdocs.org/). Configuration and deployment is described for both GitBook and MkDocs.

## Configure & deploy for [GitBook](https://docs.gitbook.com/)

To configure and deploy this documentation on GitBook, see: https://docs.gitbook.com/.

## Configure & deploy for [MkDocs](https://www.mkdocs.org/) (obsolete)

### Structure

See the [documentation for MkDocs](https://www.mkdocs.org/).

### Theme

See the [documentation for Material for MkDocs](https://squidfunk.github.io/mkdocs-material/). 

### Deploy to GitHub pages

The following instructions update the gh-pages branch of this repository, which is necessary to host on GitHub pages.

1. Install MkDocs. E.g., `pip install mkdocs`.

2. Create (or don't delete) the CNAME file found in ./docs. This file tells GitHub that the documentation URL will point to the files in the gh-pages branch.

3. From the same directory as this readme file, run 'mkdocs gh-deploy'. **For Windows users:** This step should be from Git Shell, which is installed when you install GitHub desktop. This ensures that the appropriate git-related commands are available. After opening Git Shell, you will need to navigate to the root docs directory.

That's it! In practice, step 3 is the only command needed on a routine basis to update the documentation site.

Some additional points:
- In step 2, this works because *any* file or folder other than the markdown files (*.md) will be copied to the gh-pages branch.
- The MkDocs documentation on deployment (step 3) indicate that `gh-deploy` should be run from the primary development branch (i.e., `master`), but this doesn't seem to be the case; it may be run from any working branch.
