# Ritchie Lab website

Source of the Ritchie Lab website (Jekyll, served by GitHub Pages).
Pages: About (`index.markdown`), Software (`software.markdown`), Datasets (`datasets.markdown`).

The Software and Datasets pages are generated from one small file per entry, so you
never edit the page layout to add something: you add a file (and an image) and commit.

## Add a software package

1. **Add the icon.** Put a square PNG (about 200x200 px or larger) in
   `assets/images/software/`, e.g. `assets/images/software/mytool.png`.
2. **Add the entry.** Create `_software/mytool.markdown` (any file name, `.markdown`):

   ```yaml
   ---
   name: MyTool
   github: https://github.com/mritchielab/MyTool
   bioconductor: https://bioconductor.org/packages/release/bioc/html/MyTool.html
   papers:
       -
           name: Title of the paper
           url: https://doi.org/10.xxxx/xxxxx
       -
           name: Title of a second paper
           url: https://www.biorxiv.org/content/10.1101/xxxx
   icon: mytool.png
   description: One-sentence description of what the software does
   ---
   ```

   - `name`, `github`, `icon` and `description` are needed.
   - `bioconductor` and `papers` are optional: delete those lines if not applicable
     (the Bioconductor button and the Publications list then do not appear).
   - `icon` is the file name inside `assets/images/software/`.
3. Commit and push. The package appears on the Software page and in the icon index at
   the top of it.

## Add a dataset

1. **Add the figure.** Put an image (PNG, JPEG or WebP; a landscape figure works best)
   in `assets/images/datasets/`, e.g. `assets/images/datasets/mydata.png`.
2. **Add the entry.** Create `_datasets/mydata.markdown`:

   ```yaml
   ---
   name: MyData
   datasets:
       -
           name: GSE000000
           url: https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE000000
       -
           name: Second accession
           url: https://example.org/second-dataset
   code: https://github.com/mritchielab/MyData_workflow
   papers:
       -
           name: Title of the paper
           url: https://doi.org/10.xxxx/xxxxx
   icon: mydata.png
   ---
   ```

   - `name` and `code` (link to the analysis code) are needed.
   - `datasets` (data accessions), `papers` and `icon` are optional: delete the lines
     you do not need.
   - `icon` is the file name inside `assets/images/datasets/`.
3. Commit and push. The dataset appears on the Datasets page.

## Notes

- **Order:** entries are listed alphabetically by file name. To move an entry, rename its file.
- **Colons in text:** a colon followed by a space inside a value breaks the YAML. Either
  put the value in double quotes (`name: "Glimma: interactive graphics"`) or write the
  colon as `&#58;`.
- **Indentation:** use spaces (not tabs) and keep the `-` list items lined up as in the
  examples above.
- **Preview locally (optional):** `bundle install` then `bundle exec jekyll serve`, and
  open http://localhost:4000. The generated `_site/` folder is git-ignored: do not commit it.
- **Hosting under a sub-path:** pages use relative links (see `_includes/rootpath.html`), so the
  site also works when served as a project page such as `username.github.io/repo-name/`.
