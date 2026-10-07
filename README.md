# EMT Study Guides

LaTeX sources and compiled PDFs for electromagnetic theory (EMT) study guides. The guides mainly follow Pollack & Stump, with some inspiration from Griffiths and the course instructor's notes.

## Contents

```
.
├── README.md
├── study-guide-1/
│   ├── emt_study_guide_1.tex
│   └── emt_study_guide_1.pdf
└── ...
```

Each study guide lives in its own folder with its `.tex` source and compiled `.pdf`.

| Guide | Topics |
|-------|--------|
| Study Guide 1 | Math review, electrostatics (Pollack & Stump ch. 3), conductors (ch. 4), practice problems |

## Building a PDF

Requires a LaTeX distribution (TeX Live or MiKTeX) with these packages: `amsmath`, `amssymb`, `mathtools`, `tikz`, `fancyhdr`, `titlesec`, `needspace`, `geometry`.

```bash
cd study-guide-1
pdflatex emt_study_guide_1.tex
pdflatex emt_study_guide_1.tex   # run twice to settle headers and references
```

## Contributing

Corrections, additions, and new study guides are welcome. All changes go through merge requests.

### 1. Fork and clone

1. Fork this repository to your own account.
2. Clone your fork:
   ```bash
   git clone <your-fork-url>
   cd <repo-name>
   ```
3. Add the original repository as `upstream` so you can stay in sync:
   ```bash
   git remote add upstream <original-repo-url>
   ```

### 2. Create a branch

Never work on `main`. Branch from an up-to-date `main`:

```bash
git checkout main
git pull upstream main
git checkout -b <short-descriptive-branch-name>
```

Examples: `fix-gauss-theorem-typo`, `add-magnetostatics-guide`, `improve-dipole-figure`.

### 3. Make your changes

- Edit the `.tex` source, never only the PDF.
- Build locally and confirm it compiles with no errors and no overfull boxes.
- Recompile the PDF and include the updated `.pdf` in your commit.
- Keep commits small and focused, with clear messages (for example, `Fix sign in dipole torque equation`).

### 4. Push and open a merge request

```bash
git push origin <your-branch-name>
```

Pushing to your fork does **not** open a merge request automatically. You have to open it yourself:

1. After pushing, the terminal prints a link, and your fork's page shows a "Create merge request" banner. Click either one.
2. Set the target to the `main` branch of this repository (not your fork's `main`).
3. Fill in the description, then submit. In the description, include:
   - What you changed and why.
   - The page or section affected.
   - A source (textbook equation number or page) for any correction to content.

Once submitted, the merge request appears in this repository's Merge Requests tab and the maintainer is notified.

### 5. Review

Your merge request will be reviewed for correctness and consistency. You may be asked to make changes. Push further commits to the same branch and the merge request updates automatically. Once approved, it will be merged.

## For maintainers: reviewing merge requests

1. Open the Merge Requests tab and select the request. You also get a notification (email and/or in-app) when one is submitted.
2. Review the diff. Comment on specific lines, and request changes or approve.
3. If changes are needed, the contributor pushes more commits to the same branch and the request updates on its own.
4. When it looks good, click Merge.

Recommended repository settings:

- Protect `main` so nobody can push to it directly.
- Require at least one approval before the Merge button is enabled.

On GitHub, merge requests are called pull requests. The flow is identical.

### Keeping your fork up to date

```bash
git checkout main
git pull upstream main
git push origin main
```

## Style guidelines

- **Fit on the page.** Nothing may run off the side margin or get cut off at the bottom of a page. Check the build log for `Overfull \hbox` warnings.
- **Page numbers** appear in the top and bottom corners, with header and footer rules.
- **Vectors** are written with bars (`\bar{x}`), unit vectors with hats.
- **Figures** are drawn in TikZ so they stay in the source and scale cleanly.
- **Keep sources faithful.** Do not change the math in existing sections unless you are fixing an error, and say so in the merge request.
- **Practice problems** use the `\problem[Topic]` command defined in the Practice Problems section.

## Reporting errors

If you find a mistake but do not want to fix it yourself, open an issue with the page number and a description of the error.