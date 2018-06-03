# openagua-documentation
This houses the OpenAgua documentation files. The docs aim to describe the project and how to use OpenAgua (pending a better system), not how to install it. Installation instructions will stay in the main repository.

This documentation is hosted on GitHub Pages (the gh-pages branch of this repository) and can be found at [docs.openagua.org](docs.openagua.org).

**Instructions for deploying**

The docs are built with [MkDocs](www.mkdocs.org), a documentation-centric static site generator written in Python. While the MkDocs website has clear instructions for creating and customizing the docs, instructions for deployment to GitHub Pages (gh-pages branch) are less clear. The following steps are critical:

1. Install MkDocs. E.g., `pip install mkdocs`.

2. Create (or don't delete) the CNAME file found in ./docs. This file tells GitHub that the documentation URL will point to the files in the gh-pages branch.

3. From the same directory as this readme file, run 'mkdocs gh-deploy'. **For Windows users:** This step should be from Git Shell, which is installed when you install GitHub desktop. This ensures that the appropriate git-related commands are available. After opening Git Shell, you will need to navigate to the root docs directory.

That's it! In practice, step 3 is the only command needed on a routine basis to update the documentation site.

Some additional points:
- In step 2, this works because *any* file or folder other than the markdown files (*.md) will be copied to the gh-pages branch.
- The MkDocs documentation on deployment (step 3) indicate that `gh-deploy` should be run from the primary development branch (i.e., `master`), but this doesn't seem to be the case; it may be run from any working branch.
