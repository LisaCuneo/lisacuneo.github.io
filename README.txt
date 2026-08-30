Copy .quartoignore and .gitignore into the root of the Quarto project.

.quartoignore prevents old generated output directories from being treated
as project input/resources during another profile build.

.gitignore prevents Quarto build output from being committed to Git.

Then remove the current generated directories and rebuild:

rm -rf _site _site-public
quarto preview
# stop the preview, then:
quarto preview --profile public

Expected:
- _site/ contains projects.html
- _site-public/ does NOT contain projects.html
- _site-public/ should no longer contain a nested _site/ directory
